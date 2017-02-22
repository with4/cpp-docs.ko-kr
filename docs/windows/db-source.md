---
title: "db_source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_source attribute"
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# db_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 원본에 연결을 만듭니다.  
  
## 구문  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### 매개 변수  
 *db\_source*  
 데이터 원본에 연결 하는 데 사용 되는 연결 문자열입니다.  연결 문자열의 형식에 대 한 참조 하십시오.  [연결 문자열 및 데이터 링크](https://msdn.microsoft.com/en-us/library/ms718376.aspx) 에서 Microsoft 데이터 액세스 구성 요소 \(MDAC\) SDK입니다.  
  
 *이름*  \(옵션\)  
 사용 하는 경우 `db_source` 클래스에  *이름* 가 데이터 소스 개체의 인스턴스는 `db_source` \(예제 1 참조\)를 적용 하는 특성입니다.  사용 하는 경우 `db_source` 인라인 메서드 구현에서  *이름* 데이터에 액세스 하는 데 사용할 수 있습니다 변수 \(로컬 메서드\)는 소스 \(예제 2 참조\).  이 전달  *이름* 에 `source_name` 매개 변수를  **db\_command** 명령을 사용 하 여 데이터 소스를 연결 합니다.  
  
 `hresult`\(선택적 요소\)  
 받을 수 있는 변수를 식별의 `HRESULT` 이 데이터베이스 명령을.  변수는 존재 하지 않는 경우 특성으로 자동으로 추가 됩니다.  
  
## 설명  
 `db_source`만듭니다는  [CDataSource](../data/oledb/cdatasource-class.md) a  [CSession](../data/oledb/csession-class.md) 함께 OLE DB 소비자 데이터 소스와의 연결을 나타내는 개체입니다.  
  
 사용 하는 경우 `db_source` 클래스에 `CSession` 개체는 클래스의 멤버가 됩니다.  
  
 사용 하는 경우 `db_source` 메서드 범위 내에서 삽입 된 코드에서 메서드를 실행 됩니다 및 `CSession` 개체가 로컬 변수 이름으로 만들어집니다.  
  
 `db_source`클래스 또는 메서드 내에서 데이터 원본 속성을 추가합니다.  와 함께에서 사용 되는  **db\_command** \(어떤 라인의 `db_source`*이름* 매개 변수로 해당 `source_name` 매개 변수\).  
  
 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 컴파일러는 클래스 이름을 \_ 하*YourClassName*접근자를 위치  *YourClassName* 클래스를 제공한 이름입니다 및 컴파일러도 라는 클래스를 만듭니다  *YourClassName,*  \_에서 파생 되는*YourClassName*접근자입니다.  클래스 뷰에서 클래스 모두에 표시 됩니다.  
  
 샘플 응용 프로그램에서 사용 되는이 특성의 예를 참조 하십시오  [AtlAgent](http://msdn.microsoft.com/ko-kr/52bef5da-c1a0-4223-b4e6-9e464b6db409) 및  [MultiRead](http://msdn.microsoft.com/ko-kr/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## 예제  
 이 샘플에서는 호출 `db_source` 데이터 원본에 연결 하는 클래스에서 `ds` 는 Northwind 데이터베이스를 사용 하 여.  `ds`내부적으로 사용할 수 있는 데이터 원본에 대 한 핸들입니다 있는 `CMyCommand` 클래스입니다.  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, 멤버, 메서드, 현지|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)