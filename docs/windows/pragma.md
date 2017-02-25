---
title: "pragma | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.pragma"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pragma attribute"
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# pragma
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 문자열을에 따옴표를 사용 하지 않고 생성 된.idl 파일을 내보냅니다.  .  
  
## 구문  
  
```  
  
      [ pragma(  
   pragma_statement  
) ];  
```  
  
#### 매개 변수  
 *pragma\_statement*  
 이 pragma 생성 된.idl 파일로 이동 합니다.  
  
## 설명  
 **Pragma** C\+\+ 특성을 동일한 기능을가지고 있는  [pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL 속성입니다.  
  
## 예제  
  
```  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)