---
title: "is_member_pointer 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_member_pointer"
  - "is_member_pointer"
  - "std.tr1.is_member_pointer"
  - "std.is_member_pointer"
  - "std::is_member_pointer"
  - "type_traits/std::is_member_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_member_pointer 클래스[TR1]"
  - "is_member_pointer"
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_member_pointer 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tests if type is a pointer to member.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_member_pointer;  
```  
  
#### 매개 변수  
 `Ty`  
 The type to query.  
  
## 설명  
 An instance of the type predicate holds true if the type `Ty` is a pointer to member function or a pointer to member object, or a `cv-qualified` form of one of them, otherwise it holds false.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_member_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_member\_pointer\<trivial \*\> \=\= false**  
**is\_member\_pointer\<int trivial::\*\> \=\= true**  
**is\_member\_pointer\<int \(functional::\*\)\(\)\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_member\_function\_pointer 클래스](../standard-library/is-member-function-pointer-class.md)   
 [is\_member\_object\_pointer 클래스](../standard-library/is-member-object-pointer-class.md)   
 [is\_pointer 클래스](../standard-library/is-pointer-class.md)