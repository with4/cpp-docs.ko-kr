---
title: "restricted | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.restricted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "restricted attribute"
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# restricted
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

멤버는 모듈, 인터페이스 또는 dispinterface를 임의로 호출할 수 없습니다 지정 합니다.  
  
## 구문  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### 매개 변수  
 `interfaces`  
 COM 개체에 대해 임의로 호출할 수 없습니다 하나 이상의 인터페이스.  이 매개 변수는 클래스에 적용 하는 경우에 유효 합니다.  
  
## 설명  
 **제한 된** C\+\+ 특성을 동일한 기능을가지고 있는  [제한 된](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL 속성.  
  
## 예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 있는  **제한 된** 특성:  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드를 `interface`,  **클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass** \(적용 될 때  **클래스** 또는 `struct`\)|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)