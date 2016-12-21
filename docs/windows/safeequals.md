---
title: "SafeEquals | Microsoft Docs"
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
  - "SafeEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeEquals 함수"
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Compares two numbers to determine whether they are equal.  
  
## 구문  
  
```  
template<typename T, typename U>  
inline bool SafeEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### 매개 변수  
 \[in\] `t`  
 비교할 첫 번째 숫자입니다.  This must be of type T.  
  
 \[in\] `u`  
 비교할 두 번째 숫자입니다.  This must be of type U.  
  
## 반환 값  
 `t`와 `u`가 같으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 The method enhances `==` because `SafeEquals` enables you to compare two different types of numbers.  
  
 This method is part of [SafeInt 라이브러리](../windows/safeint-library.md) and is designed for a single comparison operation without creating an instance of the [SafeInt 클래스](../windows/safeint-class.md).  
  
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
 [SafeNotEquals](../windows/safenotequals.md)