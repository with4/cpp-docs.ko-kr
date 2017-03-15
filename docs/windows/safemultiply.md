---
title: "SafeMultiply | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeMultiply"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeMultiply 함수"
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# SafeMultiply
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Multiplies two numbers together in a way that protects against overflow.  
  
## 구문  
  
```  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### 매개 변수  
 \[in\] `t`  
 곱할 첫 번째 숫자입니다.  This must be of type T.  
  
 \[in\] `u`  
 곱할 두 번째 숫자입니다.  This must be of type U.  
  
 \[out\] `result`  
 The parameter where `SafeMultiply` stores the result.  
  
## 반환 값  
 `true` if no error occurs; `false` if an error occurs.  
  
## 설명  
 This method is part of [SafeInt 라이브러리](../windows/safeint-library.md) and is designed for a single multiplication operation without creating an instance of the [SafeInt 클래스](../windows/safeint-class.md).  
  
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