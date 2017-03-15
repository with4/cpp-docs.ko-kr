---
title: "registration_script | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.registration_script"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registration_script attribute"
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# registration_script
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 사용자 정의 등록 스크립트를 실행합니다.  
  
## 구문  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### 매개 변수  
 *script*  
 사용자 정의 등록 스크립트 \(.rgs\) 파일의 전체 경로입니다.  값이  **없음**, 같은 `script = "none"`에 coclass 등록 요구 되었다는 것을 나타냅니다.  
  
## 설명  
 해당  **registration\_script** C\+\+ 특성에 지정 된 사용자 정의 등록 스크립트 실행  **스크립트**.  이 특성을 지정 하지 않으면 표준.rgs 파일 \(포함 하는 구성 요소 등록에 대 한 정보\)가 사용 됩니다.  .Rgs 파일에 대 한 자세한 내용은  [는 ATL 레지스트리 구성 요소 \(등록자\)](../atl/atl-registry-component-registrar.md).  
  
 필요로 하는이 특성에  [coclass](../windows/coclass.md),  [progid](../windows/progid.md), 또는  [vi\_progid](../windows/vi-progid.md) 특성 \(또는이 중 하나를 의미 하는 다른 특성\)도 적용 될 같은 요소를 합니다.  
  
## 예제  
 다음 코드는 구성 요소가 cpp\_attr\_ref\_registration\_script.rgs 라는 레지스트리 스크립트 지정 합니다.  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
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
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)