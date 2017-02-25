---
title: "aggregatable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.aggregatable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregatable attribute"
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# aggregatable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스가 집계를 지원함을 나타냅니다.  
  
## 구문  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### 매개 변수  
 *값*  \(옵션\)  
 COM 개체가 집계 된 수를 나타내는 매개 변수:  
  
-   **절대로** 는 COM 개체를 집계할 수 없습니다.  
  
-   **허용** 는 COM 개체를 직접 만들 수 있습니다 또는 집계할 수 있습니다.  이 값이 기본값입니다.  
  
-   **항상** 는 COM 개체를 직접 만들 수 없습니다 및만 집계할 수 있습니다.  호출 하면 `CoCreateInstance` 이 개체에는 집계 개체를 지정 해야  **IUnknown** 인터페이스 \(제어 하는  **IUnknown**\).  
  
## 설명  
 **집계 가능한** C\+\+ 특성을 동일한 기능을가지고 있는  [집계 가능한](http://msdn.microsoft.com/library/windows/desktop/aa366721) MIDL 속성입니다.  컴파일러에 전달 됨을 의미 있는  **집계 가능한** 생성 된.idl 파일에 특성을 통해.  
  
 필요로 하는이 특성에  [coclass](../windows/coclass.md),  [progid](../windows/progid.md), 또는  [vi\_progid](../windows/vi-progid.md) 특성 \(또는이 중 하나를 의미 하는 다른 특성\)도 적용 될 같은 요소를 합니다.  다른 두 가지는 단일 특성을 사용 하는 경우에 자동으로 적용 됩니다.  예를 들어, 경우  **progid** 적용 된  **vi\_progid** 및  **coclass** 적용 됩니다.  
  
 **ATL 프로젝트**  
  
 ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하는 경우 특성의 동작을 변경 합니다.  앞에서 설명한 문제 외에 특성 또한 다음 매크로 중 하나를 대상 클래스에 추가 합니다.  
  
|매개 변수 값|매크로 삽입된|  
|-------------|-------------|  
|**절대 지원되지 않음**|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|  
|**허용**|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|  
|**항상**|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|  
  
## 예제  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|하나 이상의 다음:  **coclass**,  **progid**, 또는  **vi\_progid**.|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)