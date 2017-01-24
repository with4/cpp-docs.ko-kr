---
title: "소비자 마법사 생성 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "특성 삽입 클래스 및 메서드"
  - "CloseAll 메서드"
  - "CloseDataSource 메서드"
  - "소비자의 마법사 생성 클래스 및 메서드"
  - "GetRowsetProperties 메서드"
  - "메서드[C++], OLE DB 소비자 마법사 생성"
  - "OLE DB 소비자, 마법사 생성 클래스 및 메서드"
  - "OpenAll 메서드"
  - "OpenDataSource 메서드"
  - "OpenRowset 메서드"
  - "마법사 생성 클래스 및 메서드"
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 소비자 마법사 생성 메서드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL OLE DB 소비자 마법사 및 MFC 응용 프로그램 마법사는 다음과 같은 특정 함수를 생성하는데, 이에 대해 알고 있어야 합니다.  일부 메서드는 특성을 사용하는 프로젝트에서 다르게 구현될 수 있으므로 주의해야 합니다. 각 경우에 대해서는 아래에서 설명합니다.  삽입된 코드를 보는 방법은 [삽입한 코드 디버깅](../Topic/How%20to:%20Debug%20Injected%20Code.md)을 참조하십시오.  
  
-   `OpenAll` 데이터 소스, 행 집합을 열고, 책갈피가 제공되는 경우 이를 설정합니다.  
  
-   `CloseAll` 열려진 모든 행 집합을 닫고 모든 명령 실행을 해제합니다.  
  
-   `OpenRowset` OpenAll에 의해 호출되어 소비자 행 집합을 엽니다.  
  
-   `GetRowsetProperties` 속성을 설정할 수 있는 행 집합의 속성 집합을 가리키는 포인터를 검색합니다.  
  
-   `OpenDataSource` **데이터 연결 속성** 대화 상자에서 지정한 초기화 문자열을 사용하여 데이터 소스를 엽니다.  
  
-   `CloseDataSource` 적절한 방법으로 데이터 소스를 닫습니다.  
  
## OpenAll 및 CloseAll  
  
```  
HRESULT OpenAll();   
void CloseAll();  
```  
  
 다음 예제는 같은 명령을 반복적으로 실행할 때 `OpenAll` 및 `CloseAll` 을 호출하는 방법을 보여 줍니다.  `CloseAll` 대신 **Close** 및 `ReleaseCommand`를 호출하는 [CCommand::Close](../../data/oledb/ccommand-close.md)의 코드 예제와 비교해 보십시오.  
  
```  
int main(int argc, char* argv[])  
{  
   HRESULT hr;  
  
   hr = CoInitialize(NULL);  
  
   CCustOrdersDetail rs;      // Your CCommand-derived class  
   rs.m_OrderID = 10248;      // Open order 10248  
   hr = rs.OpenAll();         // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the first command execution  
   rs.Close();  
  
   rs.m_OrderID = 10249;      // Open order 10249 (a new order)  
   hr = rs.Open();            // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the second command execution;  
   // Instead of rs.CloseAll() you could call  
   // rs.Close() and rs.ReleaseCommand():  
   rs.CloseAll();  
  
   CoUninitialize();  
   return 0;  
}  
```  
  
## 설명  
 `HasBookmark` 메서드를 정의하면 `OpenAll`  코드에서는 DBPROP\_IRowsetLocate 속성을 설정합니다. 공급자에서 해당 속성을 지원하는 경우에만 이 메서드를 정의하십시오.  
  
## OpenRowset  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll**은 이 메서드를 호출하여 소비자에서 행집합을 엽니다.  여러 데이터 소스\/세션\/행 집합을 사용하여 작업하려는 경우가 아니면 일반적으로 `OpenRowset`을 호출할 필요가 없습니다.  `OpenRowset`은 명령 또는 테이블 클래스 헤더 파일에 선언됩니다.  
  
```  
// OLE DB Template version:  
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
{  
   HRESULT hr = Open(m_session, NULL, pPropSet);  
   #ifdef _DEBUG  
   if(FAILED(hr))  
      AtlTraceErrorRecords(hr);  
   #endif  
   return hr;  
}  
```  
  
 이 특성은 이 메서드를 다르게 구현합니다.  이 버전에서는 사용자가 다른 매개 변수를 전달해도, db\_command에 지정된 명령 문자열을 기본으로 하는 명령 문자열과 세션 개체를 받아들입니다.  `HasBookmark` 메서드를 정의하면 `OpenRowset` 코드에서 DBPROP\_IRowsetLocate 속성을 설정합니다. 공급자가 해당 속성을 지원하는 경우에만 이 메서드를 정의하십시오.  
  
```  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)  
{  
  
   DBPROPSET *pPropSet = NULL;  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   __if_exists(HasBookmark)  
  
   {  
      propset.AddProperty(DBPROP_IRowsetLocate, true);  
      pPropSet= &propset;  
      }  
...  
}  
```  
  
## GetRowsetProperties  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 이 메서드는 행 집합의 속성 집합을 가리키는 포인터를 검색합니다. 이 포인터를 사용하여 DBPROP\_IRowsetChange 등의 속성을 설정할 수 있습니다.  다음과 같이 사용자 레코드 클래스에 `GetRowsetProperties`를 사용할 수 있습니다.  이 코드를 수정하여 추가 행 집합 속성을 설정할 수 있습니다.  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## 설명  
 전역 `GetRowsetProperties` 메서드를 사용자가 정의하면 마법사가 정의하는 메서드와 충돌될 수 있으므로 사용자가 정의하면 안 됩니다.  이 메서드는 특성을 사용하는 템플릿 기반 프로젝트에서 가져온 마법사 생성 메서드이므로 특성이 이 코드에 삽입되지 않습니다.  
  
## OpenDataSource 및 CloseDataSource  
  
```  
HRESULT OpenDataSource();   
void CloseDataSource();  
```  
  
## 설명  
 마법사는 `OpenDataSource` 및 `CloseDataSource`메서드를 정의합니다. `OpenDataSource`는 [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)을 호출합니다.  
  
## 참고 항목  
 [마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)