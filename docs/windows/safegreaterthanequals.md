---
title: "SafeGreaterThanEquals | Microsoft Docs"
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
  - "SafeGreaterThanEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeGreaterThanEquals 함수"
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
caps.latest.revision: 6
caps.handback.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeGreaterThanEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Compares two numbers.  
  
## 구문  
  
```  
template <typename T, typename U>  
inline bool SafeGreaterThanEquals (  
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
 `true` if `t` is greater than or equal to `u`; otherwise `false`.  
  
## 설명  
 `SafeGreaterThanEquals` enhances the standard comparison operator because it enables you to compare two different types of numbers.  
  
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
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeLessThan](../windows/safelessthan.md)