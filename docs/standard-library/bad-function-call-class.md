---
title: "bad_function_call 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::bad_function_call"
  - "functional/std::tr1::bad_function_call"
  - "std.tr1.bad_function_call"
  - "bad_function_call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_function_call 클래스[TR1]"
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# bad_function_call 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Reports a bad function call.  
  
## 구문  
  
```  
class bad_function_call  
    : public std::exception {  
    };  
```  
  
## 설명  
 The class describes an exception thrown to indicate that a call to `operator()` on a [function 클래스](../standard-library/function-class.md) object failed because the object was empty.  
  
## 예제  
  
```  
// std_tr1__functional__bad_function_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
typedef double (Fd)(double);   
typedef std::function<Fd> Myfunc;   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
int main()   
    {   
    Myfunc fd0(square);   
    std::cout << "x * x == " << fd0(3) << std::endl;   
  
    try   
        {   
        Myfunc fd1;   
        std::cout << fd1(3) << std::endl;   
        }   
    catch (const std::bad_function_call&)   
        {   
        std::cout << "bad function call" << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
  **x \* x \=\= 9**  
**bad function call**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std