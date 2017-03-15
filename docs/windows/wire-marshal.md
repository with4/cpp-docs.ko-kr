---
title: "wire_marshal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.wire_marshal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wire_marshal attribute"
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# wire_marshal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전송 하는 응용 프로그램 특정 데이터 형식 대신 사용할 수 있는 데이터 형식을 지정 합니다.  
  
## 구문  
  
```  
  
[wire_marshal]  
  
```  
  
## 설명  
 **Wire\_marshal** C\+\+ 특성을 동일한 기능을가지고 있는  [wire\_marshal](http://msdn.microsoft.com/library/windows/desktop/aa367309) MIDL 속성입니다.  
  
## 예제  
 다음 코드는 사용을 보여 줍니다.  **wire\_marshal**:  
  
```  
// cpp_attr_ref_wire_marshal.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[export, public] typedef unsigned long _FOUR_BYTE_DATA;  
  
[export] typedef struct _TWO_X_TWO_BYTE_DATA {  
   unsigned short low;  
   unsigned short high;  
} TWO_X_TWO_BYTE_DATA ;  
  
[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;  
```  
  
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
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)