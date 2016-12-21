---
title: "is_placeholder 클래스 | Microsoft Docs"
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
  - "is_placeholder"
  - "std.tr1.is_placeholder"
  - "functional/std::tr1::is_placeholder"
  - "std::tr1::is_placeholder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_placeholder 클래스[TR1]"
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_placeholder 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tests if type is a placeholder.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_placeholder {  
    static const int value;  
    };  
```  
  
## 설명  
 The constant value `value` is 0 if the type `Ty` is not a placeholder; otherwise, its value is the position of the function call argument that it binds to.  You use it to determine the value `N` for the Nth placeholder `_N`.  
  
## 예제  
  
```  
// std_tr1__functional__is_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
using namespace std::placeholders;   
  
template<class Expr>   
    void test_for_placeholder(const Expr&)   
    {   
    std::cout << std::is_placeholder<Expr>::value << std::endl;   
    }   
  
int main()   
    {   
    test_for_placeholder(3.0);   
    test_for_placeholder(_3);   
  
    return (0);   
    }  
  
```  
  
  **0**  
**3**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\_1 개체](../standard-library/1-object.md)