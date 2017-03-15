---
title: "db_accessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_accessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_accessor attribute"
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_accessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

그룹  **db\_column** 참여 특성 `IAccessor`\-바인딩을 기반으로 합니다.  
  
## 구문  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### 매개 변수  
 *num*  
 접근자 번호 \(0부터 시작 하는 정수 인덱스\)를 지정합니다.  접근자 증가 숫자 정수를 사용 하 여 주문 또는 정의 된 값을 지정 해야 합니다.  
  
 *자동*  
 접근자를 자동으로 검색 하는지 여부를 지정 하는 부울 값 \(**TRUE**\) 또는 검색 \(**FALSE**\).  
  
## 설명  
 **db\_accessor** 기본 OLE DB 접근자에 대 한 정의 후속  **db\_column** 및  **db\_param** 같은 클래스 또는 함수 내에서 특성.  **db\_accessor** 멤버 수준에서 사용할 수 있으며 사용 그룹  **db\_column** OLE DB에서 참여 특성 `IAccessor`\-바인딩을 기반으로 합니다.  하나 하 나와 함께에서 사용 되는  **db\_table** 또는  **db\_command** 특성입니다.  이 특성 호출 하는 호출 하기 것은  [BEGIN\_ACCESSOR](../data/oledb/begin-accessor.md) 및  [END\_ACCESSOR](../data/oledb/end-accessor.md) 매크로.  
  
 **db\_accessor** 행 집합을 생성 하 고 해당 접근자 지도에 바인딩합니다.  호출 하지 않아야 하는 경우  **db\_accessor**0 접근자 생성 됩니다 자동으로 하 고 모든 열 바인딩이이 접근자 블록에 매핑됩니다.  
  
 **db\_accessor** 데이터베이스에 하나 이상의 접근자 열 바인딩 그룹입니다.  에 필요한 여러 접근자를 사용 하는 시나리오에 대 한 설명은 참조 하십시오.  [행 집합에서 여러 접근자를 사용 하 여](../data/oledb/using-multiple-accessors-on-a-rowset.md).  또한 "사용자 레코드 지원에 대 한 여러 접근자"을 참조 하십시오  [사용자 레코드](../data/oledb/user-records.md).  
  
 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 컴파일러는 클래스 이름을 \_ 하*YourClassName*접근자를 위치  *YourClassName* 클래스를 제공한 이름입니다 및 컴파일러도 라는 클래스를 만듭니다  *YourClassName,*  \_에서 파생 되는*YourClassName*접근자입니다.  클래스 뷰에서 클래스 모두에 표시 됩니다.  
  
## 예제  
 다음 예제를 사용 하 여  **db\_accessor** 두 접근자에는 Northwind 데이터베이스에서 Orders 테이블에 있는 그룹 열 수 있습니다.  접근자 0은 자동 접근자입니다 및 접근자 1 아닙니다.  
  
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
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|특성 블록|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)