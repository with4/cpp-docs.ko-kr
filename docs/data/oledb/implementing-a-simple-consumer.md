---
title: "단순 소비자 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클라이언트., 만들기"
  - "OLE DB 소비자, 구현"
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 단순 소비자 구현
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 항목에서는 MFC 응용 프로그램 마법사 및 ATL OLE DB 소비자 마법사가 만든 파일을 편집하여 간단한 소비자를 만드는 방법을 보여 줍니다.  이 예제는 다음과 같은 부분으로 이루어집니다.  
  
-   "소비자로 데이터 검색"에서는 데이터베이스 테이블에서 행 단위로 모든 데이터를 읽는 소비자에서 코드를 구현하는 방법을 보여 줍니다.  
  
-   "책갈피 지원을 소비자에 추가"에서는 책갈피 지원을 소비자에 추가하는 방법을 설명합니다.  
  
-   "XML 지원을 소비자에 추가"에서는 소비자 코드를 수정하여 조회한 행 집합을 XML 데이터로 출력하는 방법을 설명합니다.  
  
> [!NOTE]
>  이 단원에서 설명하는 소비자 응용 프로그램을 사용하여 MyProv 및 Provider 샘플 공급자를 테스트할 수 있습니다.  
  
> [!NOTE]
>  [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)에 설명된 것과 동일한 공급자인 MyProv를 테스트하기 위해 소비자 응용 프로그램을 작성하려면, "책갈피 지원을 소비자에 추가"에 설명된 것과 같이 책갈피 지원을 포함해야 합니다.  
  
> [!NOTE]
>  공급자를 테스트하는 소비자 응용 프로그램을 작성하려면 "책갈피 지원을 소비자에 추가"에 설명된 책갈피 지원은 건너뛰고 "XML 지원을 소비자에 추가"로 가십시오.  
  
## 소비자로 데이터 검색  
  
#### OLE DB 소비자를 사용하여 콘솔 응용 프로그램을 수정하려면  
  
1.  MyCons.cpp에서 다음과 같이 굵은 텍스트를 삽입하여 main 코드를 변경합니다.  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);        // Instantiate rowset    CProducts rs;        hr = rs.OpenAll();    ATLASSERT( SUCCEEDED( hr ) );    hr = rs.MoveFirst();        // Iterate through the rowset    while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )    {       // Print out the column information for each row       printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",              rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );       hr = rs.MoveNext();    }        rs.Close();    rs.ReleaseCommand();        CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## 책갈피 지원을 소비자에 추가  
 책갈피는 테이블의 행을 고유하게 구별하는 열입니다.  일반적으로 키 열이 책갈피가 되지만 항상 그런 것은 아니고 공급자에 따라 다릅니다.  이 단원에서는 책갈피 지원을 추가하는 방법을 보여 줍니다.  이를 위해 사용자 레코드 클래스에서 다음 작업을 수행해야 합니다.  
  
-   책갈피를 인스턴스화합니다.  [CBookmark](../../data/oledb/cbookmark-class.md) 형식의 개체입니다.  
  
-   **DBPROP\_IRowsetLocate** 속성을 설정하여 공급자에서 책갈피 열을 요청합니다.  
  
-   [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md) 매크로를 사용하여 열 맵에 책갈피 엔트리를 추가합니다.  
  
 위의 단계는 작업할 책갈피 개체 및 책갈피 지원을 제공합니다.  이 코드 예제는 다음과 같이 책갈피를 설명합니다.  
  
-   쓰기 위해 파일을 엽니다.  
  
-   행 단위로 행 집합 데이터를 파일에 출력합니다.  
  
-   [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)를 호출하여 행 집합 커서를 책갈피로 이동합니다.  
  
-   책갈피가 있는 행을 파일의 끝에 추가하면서 출력합니다.  
  
> [!NOTE]
>  이 소비자 응용 프로그램을 사용하여 Provider 샘플 공급자 응용 프로그램을 테스트하려면 이 단원에서 설명한 책갈피 지원을 건너뛰십시오.  
  
#### 책갈피를 인스턴스화하려면  
  
1.  접근자는 [CBookmark](../../data/oledb/cbookmark-class.md) 형식의 개체를 포함해야 합니다.  `nSize` 매개 변수는 책갈피 버퍼의 크기를 바이트 단위로 지정합니다. 일반적으로 32비트 플랫폼에서는 4바이트이고, 64비트 플랫폼에서는 8바이트입니다.  다음 선언을 사용자 레코드 클래스의 열 데이터 멤버에 추가합니다.  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### 공급자에게 책갈피 열을 요청하려면  
  
1.  다음 코드를 사용자 레코드 클래스의 `GetRowsetProperties` 메서드에 추가합니다.  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks    pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### 책갈피 엔트리를 열 맵에 추가하려면  
  
1.  다음 엔트리를 사용자 레코드 클래스의 열 맵에 추가합니다.  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### main 코드에서 책갈피를 사용하려면  
  
1.  앞에서 만든 콘솔 응용 프로그램의 mycons.cpp 파일에서 다음과 같이 main 코드를 변경합니다.  책갈피를 사용하려면 main 코드에서 해당 책갈피 개체\(`myBookmark`\)를 인스턴스화해야 합니다. 이 개체는 접근자에 있는 책갈피 개체\(`m_bookmark`\)와는 다릅니다.  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       hr = rs.OpenAll();  
       hr = rs.MoveFirst();  
  
       // Cast CURRENCY m_UnitPrice to a long value  
       LONGLONG lPrice = rs.m_UnitPrice.int64;  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // Instantiate a bookmark object myBookmark for the main code  
       CBookmark<4> myBookmark;  
       int nCounter = 0;  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "initial row dump" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if( nCounter == 5 )  
             myBookmark = rs.bookmark;  
          // Output the column information for each row:  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       // Move cursor to bookmark  
       hr = rs.MoveToBookmark(myBookmark);  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "row dump starting from bookmarked row" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          // Output the column information for each row  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
 책갈피에 대한 자세한 내용은 [책갈피 사용](../../data/oledb/using-bookmarks.md)을 참조하십시오.  책갈피에 대한 다른 예제를 보려면 [행 집합 업데이트](../../data/oledb/updating-rowsets.md)를 참고하십시오.  
  
## XML 지원을 소비자에 추가  
 [XML 데이터 액세스](../../data/oledb/accessing-xml-data.md)에서 설명한 것처럼 데이터 소스에서 XML 데이터를 검색하는 방법에는 두 가지가 있습니다. [CStreamRowset](../../data/oledb/cstreamrowset-class.md)을 사용하거나 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)를 사용하는 것입니다.  이 예제에서는 `CStreamRowset`을 사용하는데, 이 방법이 더 효율적이지만 이 샘플 응용 프로그램을 실행할 컴퓨터에 SQL Server 2000이 실행되고 있어야 합니다.  
  
#### CStreamRowset에서 상속된 명령 클래스를 수정하려면  
  
1.  이전에 만든 소비자 응용 프로그램에서 `CCommand` 선언 부분을 변경하여 `CStreamRowset`을 다음과 같이 행 집합 클래스로 지정합니다.  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### XML 데이터를 검색하고 출력하도록 main 코드를 수정하려면  
  
1.  앞에서 만든 콘솔 응용 프로그램의 MyCons.cpp 파일에서 다음과 같이 main 코드를 변경합니다.  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
          HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## 참고 항목  
 [마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)