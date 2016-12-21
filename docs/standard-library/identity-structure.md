---
title: "identity 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::identity"
  - "utility/std::identity"
  - "identity"
  - "std.identity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "identity 클래스"
  - "identity 구조체"
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# identity 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A struct that provides a type definition as the template parameter.  
  
## 구문  
  
```  
template<class Type>  
   struct identity {  
      typedef Type type;  
      Type operator()(const Type& _Left) const;  
   };  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`_Left`|The value to identify.|  
  
## 설명  
 The class contains the public type definition `type`, which is the same as the template parameter Type.  It is used in conjunction with template function [forward](../Topic/forward.md) to ensure that a function parameter has the desired type.  
  
 For compatibility with older code, the class also defines the identity function `operator()` which returns its argument `_Left`.  
  
## 요구 사항  
 **Header:** \<utility\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<utility\>](../standard-library/utility.md)