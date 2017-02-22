---
title: "is_reference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_reference"
  - "std::tr1::is_reference"
  - "is_reference"
  - "std.is_reference"
  - "std::is_reference"
  - "type_traits/std::is_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_reference 클래스[TR1]"
  - "is_reference"
ms.assetid: 3d9e631f-3092-430c-843e-e914ab58c257
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# is_reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 참조인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_reference;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 형식 `Ty`가 개체 또는 함수에 대한 참조일 경우 true이고, 그렇지 않으면 false입니다.  
  
## 예제  
  
```  
// std__type_traits__is_reference.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_reference<trivial> == " << std::boolalpha   
        << std::is_reference<trivial>::value << std::endl;   
    std::cout << "is_reference<trivial&> == " << std::boolalpha   
        << std::is_reference<trivial&>::value << std::endl;   
    std::cout << "is_reference<int()> == " << std::boolalpha   
        << std::is_reference<int()>::value << std::endl;   
    std::cout << "is_reference<int(&)()> == " << std::boolalpha   
        << std::is_reference<int(&)()>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_reference\<trivial\> \=\= false**  
**is\_reference\<trivial&\> \=\= true**  
**is\_reference\<int\(\)\> \=\= false**  
**is\_reference\<int\(&\)\(\)\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_pointer 클래스](../standard-library/is-pointer-class.md)