---
title: "SafeModulus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeModulus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeModulus 함수"
ms.assetid: ae5c81eb-5dcf-45a5-aa76-465fdfe68654
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeModulus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Performs the modulus operation on two numbers.  
  
## 구문  
  
```  
template<typename T, typename U>  
inline bool SafeModulus (  
   const T t,  
   const U u,  
   T& result  
) throw ();  
```  
  
#### 매개 변수  
 \[in\] `t`  
 제수입니다.  This must be of type T.  
  
 \[in\] `u`  
 피제수입니다.  This must be of type U.  
  
 \[out\] `result`  
 The parameter where `SafeModulus` stores the result.  
  
## 반환 값  
 `true` if no error occurs; `false` if an error occurs.  
  
## 설명  
 This method is part of [SafeInt 라이브러리](../windows/safeint-library.md) and is designed for a single modulus operation without creating an instance of the [SafeInt 클래스](../windows/safeint-class.md).  
  
> [!NOTE]
>  This method should only be used when a single mathematical operation must be protected.  If there are multiple operations, you should use the `SafeInt` class instead of calling the individual stand\-alone functions.  
  
 For more information about the template types T and U, see [SafeInt 함수](../windows/safeint-functions.md).  
  
## 요구 사항  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## 참고 항목  
 [SafeInt 함수](../windows/safeint-functions.md)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeDivide](../windows/safedivide.md)