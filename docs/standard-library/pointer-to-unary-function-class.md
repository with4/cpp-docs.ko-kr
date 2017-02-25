---
title: "pointer_to_unary_function 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::pointer_to_unary_function"
  - "pointer_to_unary_function"
  - "std.pointer_to_unary_function"
  - "std::pointer_to_unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_unary_function 클래스"
  - "pointer_to_unary_function 함수"
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# pointer_to_unary_function 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

적응 가능한 단항 함수는 단항 함수 포인터로 변환합니다.  
  
## 구문  
  
```  
template<class Arg, class Result>  
class pointer_to_unary_function  
    : public unary_function<Arg, Result>   
    {  
    public:  
        explicit pointer_to_unary_function(  
            Result (*_pfunc)(Arg)  
        );  
        Result operator()(  
            Arg _Left  
        ) const;  
    };  
```  
  
#### 매개 변수  
 `_pfunc`  
 The binary function to be converted.  
  
 `_Left`  
 The object that the *\*\_pfunc* is called on.  
  
## 반환 값  
 The template class stores a copy of **\_pfunc**.  It defines its member function `operator()` as returning \(\***\_pfunc**\)\(\_*Left*\).  
  
## 설명  
 A unary function pointer is a function object and may be passed to any Standard Template Library algorithm that is expecting a unary function as a parameter, but it is not adaptable.  To use it with an adaptor, such as binding a value to it or using it with a negator, it must be supplied with the nested types **argument\_type** and **result\_type** that make such an adaptation possible.  The conversion by `pointer_to_unary_function` allows the function adaptors to work with binary function pointers.  
  
## 예제  
 The constructor of `pointer_to_unary_function` is rarely used directly.  See the helper function [ptr\_fun](../Topic/ptr_fun%20Function.md) for an example of how to declare and use the `pointer_to_unary_function` adaptor predicate.  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)