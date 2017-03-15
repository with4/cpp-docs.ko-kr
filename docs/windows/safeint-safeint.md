---
title: "SafeInt::SafeInt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt::SafeInt"
  - "SafeInt"
  - "SafeInt.SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt 클래스, 생성자"
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# SafeInt::SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`SafeInt` 개체를 생성합니다.  
  
## 구문  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### 매개 변수  
 \[in\] `i`  
 The value for the new `SafeInt` object.  This must be a parameter of type T or U, depending on the constructor.  
  
 \[in\] `b`  
 The Boolean value for the new `SafeInt` object.  
  
 \[in\] `u`  
 A `SafeInt` of type U.  The new `SafeInt` object will have the same value as `u`, but will be of type T.  
  
 U  
 The type of data stored in the `SafeInt`.  This can be either a Boolean, character, or integer type.  If it is an integer type, it can be signed or unsigned and be between 8 and 64 bits.  
  
## 설명  
 For more information about the template types `T` and `E`, see [SafeInt 클래스](../windows/safeint-class.md).  
  
 The input parameter for the constructor, `i` or `u`, must be a Boolean, character, or integer type.  If it is another type of parameter, the `SafeInt` class calls [static\_assert](../cpp/static-assert.md) to indicate an invalid input parameter.  
  
 The constructors that use the template type `U` automatically convert the input parameter to the type specified by `T`.  The `SafeInt` class converts the data without any loss of data.  It reports to the error handler `E` if it cannot convert the data to type `T` without data loss.  
  
 If you create a `SafeInt` from a Boolean parameter, you need to initialize the value immediately.  You cannot construct a `SafeInt` using the code `SafeInt<bool> sb;`.  This will generate a compile error.  
  
## 요구 사항  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## 참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)