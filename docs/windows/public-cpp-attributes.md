---
title: "public (C++ Attributes) | Microsoft Docs"
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
  - "vc-attr.public"
  - "vc-attr.public_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "public attribute"
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# public (C++ Attributes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typedef가에서.idl 파일에서 참조 되지 않는 경우에 형식 라이브러리에 진행 될 수 있습니다.  
  
## 구문  
  
```  
  
[public]  
  
```  
  
## 설명  
 **공용** C\+\+ 특성을 동일한 기능을가지고 있는  [공용](http://msdn.microsoft.com/library/windows/desktop/aa367150) MIDL 속성.  
  
## 예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 있는  **public** 특성:  
  
```  
// cpp_attr_ref_public.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, public] typedef long MEMBERID;  
  
[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(2)] long procedure ([in, optional] VARIANT i);  
};  
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