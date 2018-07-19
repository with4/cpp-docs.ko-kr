---
title: 단순 소비자 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 841d982090503a1e72b1d6798a5f0eecdb543fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112565"
---
# <a name="implementing-a-simple-consumer"></a>단순 소비자 구현
다음 항목에는 단순 소비자를 만드는 MFC 응용 프로그램 마법사 및 ATL OLE DB 소비자 마법사에서 생성 된 파일을 편집 하는 방법을 보여 줍니다. 이 예제에는 다음과 같은 부분이 있습니다.  
  
-   "소비자를 사용 하 여 데이터 검색" 데이터베이스 테이블에서 모든 데이터를 행 단위로 읽는 소비자의 코드를 구현 하는 방법을 보여 줍니다.  
  
-   "책갈피 지원을 소비자에 게 추가" 소비자에 게 책갈피 지원을 추가 하는 방법을 보여 줍니다.  
  
-   "소비자에 게 XML 지원을 추가" 소비자 코드 출력 XML 데이터 형식으로 검색 된 행 집합 데이터를 수정 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  MyProv 및 공급자 샘플 공급자를 테스트 하려면이 섹션에서 설명 하는 소비자 응용 프로그램을 사용할 수 있습니다.  
  
> [!NOTE]
>  테스트할 MyProv 소비자 응용 프로그램을 빌드하 (에 설명 된 동일한 공급자 [단순한 읽기 전용 공급자 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)), 책갈피 지원을 추가"소비자에 게."에 설명 된 대로 책갈피 지원을 포함 해야 합니다  
  
> [!NOTE]
>  공급자를 테스트 하는 소비자 응용 프로그램을 빌드하려면 "책갈피 지원 소비자에 추가"에 설명 된 책갈피 지원 건너뛰고 지원을 추가"로 XML 소비자에 게."  
  
## <a name="retrieving-data-with-the-consumer"></a>소비자를 사용 하 여 데이터를 검색합니다.  
  
#### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>OLE DB 소비자를 사용 하는 콘솔 응용 프로그램을 수정 하려면  
  
1.  MyCons.cpp에서 같이 굵은 텍스트를 삽입 하 여 주 코드를 변경 합니다.  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);   // Instantiate rowset   CProducts rs;   hr = rs.OpenAll();   ATLASSERT(SUCCEEDED(hr ) );   hr = rs.MoveFirst();   // Iterate through the rowset   while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row      printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",             rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );      hr = rs.MoveNext();   }   rs.Close();   rs.ReleaseCommand();   CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="adding-bookmark-support-to-the-consumer"></a>소비자에 책갈피 지원 추가  
 책갈피는 테이블의 행을 고유 하 게 식별 하는 열입니다. 일반적으로 키 열을는 되는 경우가 있습니다. 것은 공급자별으로 다릅니다. 이 섹션 책갈피 지원을 추가 하는 방법을 보여 줍니다. 이렇게 하려면 사용자 레코드 클래스에 다음 실행:  
  
-   책갈피를 인스턴스화하십시오. 형식의 개체 [CBookmark](../../data/oledb/cbookmark-class.md)합니다.  
  
-   책갈피 열을 설정 하 여 공급자 로부터 요청는 **DBPROP_IRowsetLocate** 속성입니다.  
  
-   책갈피 항목을 사용 하 여 열 지도에 추가 된 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) 매크로입니다.  
  
 이전 단계에는 작업할 책갈피 개체 및 지원을 제공 합니다. 이 코드 예제에서는 책갈피를 다음과 같이 보여 줍니다.  
  
-   쓰기 위해 파일을 엽니다.  
  
-   행 집합 파일의 데이터를 행을 출력 합니다.  
  
-   행 집합 커서를 호출 하 여 책갈피로 이동 [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)합니다.  
  
-   파일의 끝에 추가 하 여 책갈피가 표시 된 행을 출력 합니다.  
  
> [!NOTE]
>  이 소비자 응용 프로그램을 사용 하 여 공급자 샘플 공급자 응용 프로그램을 테스트 하는 경우에이 섹션에 설명 된 책갈피 지원은 둡니다.  
  
#### <a name="to-instantiate-the-bookmark"></a>책갈피를 인스턴스화  
  
1.  형식의 개체를 포함 해야 하는 접근자 [CBookmark](../../data/oledb/cbookmark-class.md)합니다. `nSize` 매개 변수 (일반적으로 32 비트 플랫폼에 대 한 4) 및 64 비트 플랫폼에 대 한 8 바이트에는 책갈피 버퍼의 크기를 지정 합니다. 사용자 레코드 클래스의 열 데이터 멤버에 다음 선언을 추가 합니다.  
  
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
  
#### <a name="to-request-a-bookmark-column-from-the-provider"></a>책갈피 열은 공급자를 요청 하려면  
  
1.  다음 코드에 추가 `GetRowsetProperties` 사용자 레코드 클래스에 메서드:  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>책갈피 항목 열 지도에 추가 하려면  
  
1.  사용자 레코드 클래스에 열 지도에 다음 항목을 추가 합니다.  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### <a name="to-use-a-bookmark-in-your-main-code"></a>주 코드에 책갈피를 사용 하려면  
  
1.  이전에 만든 콘솔 응용 프로그램에서 MyCons.cpp 파일에서 다음과 같이 주 코드를 변경 합니다. 책갈피를 사용 하려면 주 코드 자체 책갈피 개체를 인스턴스화할 해야 (`myBookmark`);이 접근자의 것과에서 다른 책갈피 (`m_bookmark`).  
  
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
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if(nCounter == 5 )  
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
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
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
  
 책갈피에 대 한 자세한 내용은 참조 [책갈피를 사용 하 여](../../data/oledb/using-bookmarks.md)합니다. 책갈피의 예에 표시 됩니다 [행 집합 업데이트](../../data/oledb/updating-rowsets.md)합니다.  
  
## <a name="adding-xml-support-to-the-consumer"></a>소비자에 게 XML 지원 추가  
 에 설명 된 대로 [XML 데이터 액세스](../../data/oledb/accessing-xml-data.md), 데이터 원본에서 XML 데이터를 검색 하는 방법은 두 가지가:를 사용 하 여 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 또는 사용 하 여 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)합니다. 이 예에서는 `CStreamRowset`, 더 효율적인 되지만이 샘플 응용 프로그램 실행 컴퓨터에서 실행 되는 SQL Server 2000을 사용할 수 있습니다.  
  
#### <a name="to-modify-the-command-class-to-inherit-from-cstreamrowset"></a>CStreamRowset 상속할 명령 클래스를 수정 하려면  
  
1.  이전에 만든 소비자 응용 프로그램에서 변경 하면 `CCommand` 지정 하려면 선언을 `CStreamRowset` 행 집합으로 클래스를 다음과 같이:  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### <a name="to-modify-the-main-code-to-retrieve-and-output-the-xml-data"></a>검색 하 고 XML 데이터를 출력 하는 기본 코드를 수정 하려면  
  
1.  이전에 만든 콘솔 응용 프로그램에서 MyCons.cpp 파일에서 기본 코드를 다음과 같이 변경 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)