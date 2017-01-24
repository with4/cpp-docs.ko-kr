---
title: "db_table | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_table"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_table attribute"
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_table
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE DB 테이블을 엽니다.  
  
## 구문  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### 매개 변수  
 *db\_table*  
 데이터베이스 테이블 \(예: "제품"\)의 이름을 지정 하는 문자열입니다.  
  
 *이름*  \(옵션\)  
 이름 사용이 포함 된 테이블을 사용 하 여에 대 한 핸들입니다.  결과에 둘 이상의 행을 반환 하려면이 매개 변수를 지정 해야 합니다.  **db\_table** 으로 지정 된 변수를 생성  *이름* 행 집합을 통과 하거나 여러 개의 실행 쿼리를 실행 하는 수 있습니다.  
  
 *source\_name*  \(옵션\)  
 `CSession` 변수 또는 클래스의 인스턴스는 `db_source` 에 있는 명령을 실행 합니다. 적용 되는 특성입니다.  참조 하십시오  [db\_source](../windows/db-source.md).  
  
 `hresult`\(선택적 요소\)  
 받을 수 있는 변수를 식별의 `HRESULT` 이 데이터베이스 명령을.  변수는 존재 하지 않는 경우 특성으로 자동으로 추가 됩니다.  
  
## 설명  
 **db\_table** 생성 한  [CTable](../data/oledb/ctable-class.md) 테이블을 사용 하 여 OLE DB 소비자 개체를 합니다.  이 특성은 클래스 수준 에서만 사용할 수 있습니다. 인라인으로 사용할 수 없습니다.  사용  **db\_column** 변수에; 테이블 열을 바인딩하려면 사용 하 여  **db\_param** 구분 \(되므로 매개 변수 형식에서 매개 변수를 설정\).  
  
 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 컴파일러는 클래스 이름을 \_ 하*YourClassName*접근자를 위치  *YourClassName* 클래스를 제공한 이름입니다 및 컴파일러도 라는 클래스를 만듭니다  *YourClassName,*  \_에서 파생 되는*YourClassName*접근자입니다.  클래스 뷰에서 클래스 모두에 표시 됩니다.  
  
## 예제  
 다음은 Products 테이블에서 열립니다 `CProducts`.  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 샘플 응용 프로그램에서 사용 되는이 특성의 예를 참조 하십시오  [AtlAgent](http://msdn.microsoft.com/ko-kr/52bef5da-c1a0-4223-b4e6-9e464b6db409) 및  [MultiRead](http://msdn.microsoft.com/ko-kr/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)