---
title: "switch_type | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.switch_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "switch_type attribute"
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# switch_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

통합 분석할으로 사용 되는 변수를 식별 합니다.  
  
## 구문  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### 매개 변수  
 `type`  
 스위치 형식, 정수, 문자, 부울 또는 열거형 형식이 될 수 있습니다.  
  
## 설명  
 **Switch\_type** C\+\+ 특성을 동일한 기능을가지고 있는  [switch\_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) MIDL 속성입니다.  
  
 C \+ \+ 특성을 지원 하지 않습니다  [공용 구조체를 캡슐화 된](http://msdn.microsoft.com/library/windows/desktop/aa366811).  [공용 구조체를 nonencapsulated](http://msdn.microsoft.com/library/windows/desktop/aa367119) 는 다음 형식으로 지원 됩니다.  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## 예제  
 참조는  [경우](../windows/case-cpp.md) 샘플 사용을 예를 들어  **switch\_type**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`typedef`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)