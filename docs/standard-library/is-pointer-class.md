---
title: "is_pointer 클래스 | Microsoft Docs"
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
  - "std.tr1.is_pointer"
  - "is_pointer"
  - "std::tr1::is_pointer"
  - "std.is_pointer"
  - "std::is_pointer"
  - "type_traits/std::is_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pointer 클래스[TR1]"
  - "is_pointer"
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_pointer 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 포인터인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_pointer;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 `void`에 대한 포인터, 개체에 대한 포인터 또는 함수에 대한 포인터이거나 이러한 포인터 중 하나의 `cv-qualified` 형식인 경우 true이고, 그렇지 않은 경우 false입니다.  `Ty`가 멤버에 대한 포인터 또는 멤버 함수에 대한 포인터인 경우 `is_pointer`는 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pointer<trivial> == " << std::boolalpha   
        << std::is_pointer<trivial>::value << std::endl;   
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha   
        << std::is_pointer<int trivial::*>::value << std::endl;   
    std::cout << "is_pointer<trivial *> == " << std::boolalpha   
        << std::is_pointer<trivial *>::value << std::endl;   
    std::cout << "is_pointer<int> == " << std::boolalpha   
        << std::is_pointer<int>::value << std::endl;   
    std::cout << "is_pointer<int *> == " << std::boolalpha   
        << std::is_pointer<int *>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pointer\<trivial\> \=\= false**  
**is\_pointer\<int trivial::\*\> \=\= false**  
**is\_pointer\<trivial \*\> \=\= true**  
**is\_pointer\<int\> \=\= false**  
**is\_pointer\<int \*\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_member\_pointer 클래스](../standard-library/is-member-pointer-class.md)   
 [is\_reference 클래스](../standard-library/is-reference-class.md)