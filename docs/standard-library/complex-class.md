---
title: "complex 클래스 | Microsoft Docs"
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
  - "complex"
  - "std::complex"
  - "std.complex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex 클래스"
  - "복소수"
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
caps.latest.revision: 18
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# complex 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that stores two objects of type **Type**, one that represents the real part of a complex number and one that represents the imaginary part.  
  
## 구문  
  
```  
  
   template<class   
   Type  
   >  
class complex  
```  
  
## 설명  
 An object of class **Type**:  
  
-   Has a public default constructor, destructor, copy constructor, and assignment operator with conventional behavior.  
  
-   Can be assigned integer or floating\-point values, or type cast to such values with conventional behavior.  
  
-   Defines the arithmetic operators and math functions, as needed, that are defined for the floating\-point types with conventional behavior.  
  
 In particular, no subtle differences may exist between copy construction and default construction followed by assignment.  None of the operations on objects of class **Type** may throw exceptions.  
  
 Explicit specializations of template class complex exist for the three floating\-point types.  In this implementation, a value of any other type **Type** is typecast to **double** for actual calculations, with the **double** result assigned back to the stored object of type **Type**`.`  
  
### 생성자  
  
|||  
|-|-|  
|[복합](../Topic/complex::complex.md)|Constructs a complex number with specified real and imaginary parts or as a copy of some other complex number.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[value\_type](../Topic/complex::value_type.md)|A type that represents the data type used to represent the real and imaginary parts of a complex number.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[imag](../Topic/complex::imag.md)|Extracts the imaginary component of a complex number.|  
|[real](../Topic/complex::real.md)|Extracts the real component of a complex number.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*\=](../Topic/complex::operator*=.md)|Multiplies a target complex number by a factor, which may be complex or be the same type as are the real and imaginary parts of the complex number.|  
|[연산자\+\=](../Topic/complex::operator+=.md)|Adds a number to a target complex number, where the number added may be complex or of the same type as are the real and imaginary parts of the complex number to which it is added.|  
|[operator\-\=](../Topic/complex::operator-=1.md)|Subtracts a number from a target complex number, where the number subtracted may be complex or of the same type as are the real and imaginary parts of the complex number to which it is added.|  
|[operator\/\=](../Topic/complex::operator-=2.md)|Divides a target complex number by a divisor, which may be complex or be the same type as are the real and imaginary parts of the complex number.|  
|[operator\=](../Topic/complex::operator=.md)|Assigns a number to a target complex number, where the number assigned may be complex or of the same type as are the real and imaginary parts of the complex number to which it is being assigned.|  
  
## 요구 사항  
 **Header**: \<complex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [complex Members](http://msdn.microsoft.com/ko-kr/d5c4466c-43a0-4817-aca1-9a5d492dae28)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)