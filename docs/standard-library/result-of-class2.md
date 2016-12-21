---
title: "result_of 클래스 | Microsoft Docs"
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
  - "functional/std::tr1::result_of"
  - "std::tr1::result_of"
  - "result_of"
  - "std.tr1.result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of 클래스[TR1]"
ms.assetid: 14ec0040-07f1-45a5-80b5-d0c9f9b00c8f
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# result_of 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The return type of a wrapped callable object.  
  
## 구문  
  
```  
template<class Ty>  
    struct result_of {  
    typedef T0 type;  
    };  
```  
  
#### 매개 변수  
 `Ty`  
 A description of a function call \(see Remarks section\).  
  
## 설명  
 The template class defines its member `type` as a synonym for the return type of a function call described by its template argument `Ty`.  The template argument must be of the form `Fty(T1, T2, ..., TN)`, where `Fty` is a callable type.  The template determines the return type according to the first of the following rules that applies:  
  
-   if `Fty` is a pointer to function type `R(*)(U1, U2, ..., UN)` the return type is `R`;  
  
-   if `Fty` is a reference to function type `R(&)(U1, U2, ..., UN)` the return type is `R`;  
  
-   if `Fty` is a pointer to member function type `R(U1::*)(U2, ..., UN)` the return type is `R`;  
  
-   if `Fty` is a pointer to data member type `R U1::*` the return type is `R`;  
  
-   if `Fty` is a class with a member typedef `result_type` the return type is `Fty::result_type`;  
  
-   if `N` is 0 \(that is, `Ty` is of the form `Fty()`\) the return type is `void`;  
  
-   if `Fty` is a class with a member template named `result` the return type is `Fty::result<T1, T2, ..., TN>::type`;  
  
-   in all other cases it is an error.  
  
## 예제  
  
```  
// std_tr1__functional__result_of.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
template<class Fun,   
    class Arg>   
    void test_result(const Fun& fun, Arg arg)   
    {   
    typename std::result_of<Fun(Arg)>::type val = fun(arg);   
    std::cout << "val == " << val << std::endl;   
    }   
  
int main()   
    {   
    test_result(&square, 3.0);   
  
    return (0);   
    }  
  
```  
  
  **val \=\= 9**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std