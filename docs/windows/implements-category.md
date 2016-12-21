---
title: "implements_category | Microsoft Docs"
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
  - "vc-attr.implements_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "implements_category attribute"
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# implements_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대상 클래스에 의해 구현 되는 구성 요소 범주를 지정 합니다.  
  
## 구문  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### 매개 변수  
 **implements\_category**  
 구현 된 범주 ID입니다.  
  
## 설명  
 해당  **implements\_category** C\+\+ 특성은 대상 클래스에 의해 구현 된 구성 요소 범주를 지정 합니다.  카테고리 맵 만들기에서 지정한 별도 항목을 추가 하 여 이렇게 되는  **implements\_category** 특성.  자세한 내용은  [구성 요소 범주와 방법을 수행 하는 작업은 무엇입니까?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 필요로 하는이 특성에  [coclass](../windows/coclass.md),  [progid](../windows/progid.md), 또는  [vi\_progid](../windows/vi-progid.md) 특성 \(또는이 중 하나를 의미 하는 다른 특성\)도 적용 될 같은 요소를 합니다.  다른 두 가지는 단일 특성을 사용 하는 경우에 자동으로 적용 됩니다.  예를 들어, 경우  **progid** 적용 된  **vi\_progid** 및  **coclass** 적용 됩니다.  
  
## 예제  
 다음과 같은 개체의 컨트롤 범주를 구현 다음 코드를 지정 합니다.  
  
```  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|예|  
|**필수 특성**|다음:  **coclass**,  **progid**, 또는  **vi\_progid**|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)