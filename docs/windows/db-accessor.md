---
title: db_accessor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_accessor
dev_langs:
- C++
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5faa84773fbf1fe15fd0223c97f0361f1215b149
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dbaccessor"></a>db_accessor
그룹 **db_column** 에 참여 하는 특성 `IAccessor`-바인딩을 기반으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *num*  
 접근자 번호 (0부터 시작 하는 정수 인덱스)를 지정합니다. 이 증가 접근자 숫자 순서를 정수 또는 정의 된 값을 지정 해야 합니다.  
  
 *auto*  
 접근자는 자동으로 검색 여부를 지정 하는 부울 값 (**TRUE**) 없거나 검색 되지 (**FALSE**).  
  
## <a name="remarks"></a>설명  
 **db_accessor** 에 대 한 기본 OLE DB 접근자를 정의 합니다. 후속 **db_column** 및 **db_param** 동일한 클래스 또는 함수 내에서 특성입니다. **db_accessor** 멤버 수준에서 사용할 수는 이며 사용자 그룹에 **db_column** OLE DB에 참여 하는 특성 `IAccessor`-바인딩을 기반으로 합니다. 하거나 함께에서 사용 되는 **db_table** 또는 **db_command** 특성입니다. 이 특성을 호출 하는 것이 호출과 비슷하지만 [BEGIN_ACCESSOR](../data/oledb/begin-accessor.md) 및 [END_ACCESSOR](../data/oledb/end-accessor.md) 매크로입니다.  
  
 **db_accessor** 행 집합을 생성 하 고 해당 접근자 maps에 바인딩합니다. 호출 하지 않으면 **db_accessor**접근자 0이 자동으로 생성, 및 모든 열 바인딩이 접근자 블록에 매핑됩니다.  
  
 **db_accessor** 그룹 데이터베이스에 하나 이상의 접근자 열 바인딩. 여러 접근자를 사용 해야 하는 시나리오의 논의 알려면 [행 집합에서 여러 접근자 사용](../data/oledb/using-multiple-accessors-on-a-rowset.md)합니다. 또한 "사용자 레코드 지원에 대 한 여러 접근자"에서 참조 [사용자 레코드](../data/oledb/user-records.md)합니다.  
  
 컴파일러는 클래스를 이름을 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 \_ *YourClassName*접근자 여기서 *YourClassName* 제공한 이름인는 클래스 및 컴파일러 라는 클래스를 만들 수도 됩니다 *YourClassName*에서 파생 되는 \_ *YourClassName*접근자입니다.  클래스 뷰에 두 클래스 모두 표시됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 **db_accessor** 두 접근자에 Northwind 데이터베이스의 Orders 테이블의 열을 그룹화 하려면. 접근자 0 자동는 접근자 이므로 접근자 1 없습니다.  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|특성 블록|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md)   
