---
title: "is_scalar 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_scalar"
  - "std::tr1::is_scalar"
  - "is_scalar"
  - "std.is_scalar"
  - "std::is_scalar"
  - "type_traits/std::is_scalar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_scalar 클래스[TR1]"
  - "is_scalar"
ms.assetid: a0cdfc9a-f27e-4808-890f-6ed7942db60c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_scalar 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 스칼라인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_scalar;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 정수 형식, 부동 소수점 형식, 열거형 형식, 포인터 형식 또는 멤버 포인터 형식이거나 이들 형식 중 하나의 `cv-qualified` 형식이면 true를 포함하고, 그렇지 않으면 false를 포함합니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_scalar.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_scalar<trivial> == " << std::boolalpha   
        << std::is_scalar<trivial>::value << std::endl;   
    std::cout << "is_scalar<trivial *> == " << std::boolalpha   
        << std::is_scalar<trivial *>::value << std::endl;   
    std::cout << "is_scalar<int> == " << std::boolalpha   
        << std::is_scalar<int>::value << std::endl;   
    std::cout << "is_scalar<float> == " << std::boolalpha   
        << std::is_scalar<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_scalar\<trivial\> \=\= false**  
**is\_scalar\<trivial \*\> \=\= true**  
**is\_scalar\<int\> \=\= true**  
**is\_scalar\<float\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound 클래스](../standard-library/is-compound-class.md)