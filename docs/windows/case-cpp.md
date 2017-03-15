---
title: "case (C++) | Microsoft Docs"
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
  - "vc-attr.case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case attribute"
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# case (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함께 사용 되는  [switch\_type](../windows/switch-type.md) 특성에  **공용 구조체**.  
  
## 구문  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### 매개 변수  
 *value*  
 처리를 위해 적용할는 가능한 입력된 값입니다.  종류를  **값** 는 다음 형식 중 하나가 될 수 있습니다.  
  
-   `int`  
  
-   `char`  
  
-   **boolean**  
  
-   `enum`  
  
 또는 이러한 종류의 식별자입니다.  
  
## 설명  
 **케이스** C\+\+ 특성을 동일한 기능을 가진의  **경우** MIDL 속성.  이 특성에만 사용 됩니다 있는  [switch\_type](../windows/switch-type.md) 특성입니다.  
  
## 예제  
 사용 하는 다음 코드를 보여 줍니다 있는  **경우** 특성:  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|멤버는  **클래스** 또는`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)