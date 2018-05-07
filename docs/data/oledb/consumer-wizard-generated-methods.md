---
title: 소비자 마법사 생성 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OpenAll method
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- methods [C++], OLE DB Consumer Wizard-generated
- CloseDataSource method
- consumer wizard-generated classes and methods
- OpenDataSource method
- CloseAll method
- OpenRowset method
- GetRowsetProperties method
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0e03d24f61b3eba1ff4c6fa1e4d888a0252a21b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="consumer-wizard-generated-methods"></a>소비자 마법사 생성 메서드
ATL OLE DB 소비자 마법사 및 MFC 응용 프로그램 마법사는 알고 있어야 하는 특정 기능을 생성 합니다. 참고는 몇 가지 방법을 다르게 구현 됩니다 특성 사용된 프로젝트에 있으므로 더 몇 가지 주의 해야 합니다. 각 사례는 아래에 자세히 설명 합니다. 삽입된 코드를 보는 방법에 대한 자세한 내용은 [삽입된 코드 디버그](/visualstudio/debugger/how-to-debug-injected-code)를 참조하세요.  
  
-   `OpenAll` 데이터 원본의 행 집합을 열고 사용할 수 있는 책갈피 설정 합니다.  
  
-   `CloseAll` 열려 있는 모든 행 집합을 닫고 모든 명령 실행을 해제 합니다.  
  
-   `OpenRowset` OpenAll 소비자의 행 집합 또는 행 집합 열에 의해 호출 됩니다.  
  
-   `GetRowsetProperties` 행 집합의 속성을 설정할 수 있는 속성이 있는 설정에 대 한 포인터를 검색 합니다.  
  
-   `OpenDataSource` 에 지정 된 초기화 문자열을 사용 하 여 데이터 원본이 열립니다는 **데이터 연결 속성** 대화 상자.  
  
-   `CloseDataSource` 적절 한 방식으로 데이터 소스를 닫습니다.  
  
## <a name="openall-and-closeall"></a>OpenAll 및 CloseAll  
  
```  
HRESULT OpenAll();   

void CloseAll();  
```  
  
 다음 예제에서는 호출 하는 방법을 보여 줍니다. `OpenAll` 및 `CloseAll` 반복 해 서 동일한 명령을 실행할 때. 코드 예제에서는 비교 [ccommand:: Close](../../data/oledb/ccommand-close.md)를 호출 하는 변형을 보여 주는 **닫기** 및 `ReleaseCommand` 대신 `CloseAll`합니다.  
  
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
  
## <a name="remarks"></a>설명  
 정의 하는 경우 유의 `HasBookmark` 메서드는 `OpenAll` DBPROP_IRowsetLocate 속성을 설정 하는 코드; 지만이 공급자에서 지원할 경우 해당 속성을 확인 합니다.  
  
## <a name="openrowset"></a>OpenRowset  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll** 소비자에서 행 집합 열에이 메서드를 호출 합니다. 호출할 필요가 없습니다 일반적으로 `OpenRowset` 여러 데이터 원본/세션/행 집합으로 작업 하는 경우가 있습니다. `OpenRowset` 명령 또는 테이블 클래스 헤더 파일에 선언 됩니다.  
  
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
  
 특성이이 메서드를 다르게 구현 합니다. 이 버전에서는 세션 개체를 명령 문자열 db_command에 지정 된 명령 문자열을 다른 전달할 수 있지만 기본으로 합니다. 정의 하는 경우 유의 `HasBookmark` 메서드는 `OpenRowset` DBPROP_IRowsetLocate 속성을 설정 하는 코드; 지만이 공급자에서 지원할 경우 해당 속성을 확인 합니다.  
  
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
  
## <a name="getrowsetproperties"></a>GetRowsetProperties  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 이 메서드는 행 집합의 속성 집합에 대 한 포인터를 검색합니다. DBPROP_IRowsetChange 등의 속성을 설정 하려면이 포인터를 사용할 수 있습니다. `GetRowsetProperties` 사용자 레코드 클래스에 다음과 같이 사용 됩니다. 추가 행 집합 속성을 설정 하는이 코드를 수정할 수 있습니다.  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## <a name="remarks"></a>설명  
 정의 하면 안 전역 `GetRowsetProperties` 마법사에 의해 정의 한 경우에 충돌할 수 있으므로 메서드. 이 템플릿으로 만들고 특성 사용 프로젝트; 얻을 수 있는 하는 마법사에서 생성 된 방법 note 이 코드를 삽입 하지 않습니다.  
  
## <a name="opendatasource-and-closedatasource"></a>OpenDataSource 및 CloseDataSource  
  
```  
HRESULT OpenDataSource();   

void CloseDataSource();  
```  
  
## <a name="remarks"></a>설명  
 메서드를 정의 하는 마법사 `OpenDataSource` 및 `CloseDataSource`; `OpenDataSource` 호출 [cdatasource:: Openfrominitializationstring](../../data/oledb/cdatasource-openfrominitializationstring.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)