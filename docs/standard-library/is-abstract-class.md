---
title: "is_abstract 클래스 | Microsoft Docs"
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
  - "std.tr1.is_abstract"
  - "std::tr1::is_abstract"
  - "is_abstract"
  - "std.is_abstract"
  - "std::is_abstract"
  - "type_traits/std::is_abstract"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_abstract 클래스[TR1]"
  - "is_abstract"
ms.assetid: 8867f660-3434-404c-ba90-c26607a5e0d2
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_abstract 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 추상 클래스인지 여부를 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_abstract;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 형식 `Ty`가 하나 이상의 순수 가상 함수를 가진 클래스인 경우 true이고 그렇지 않은 경우 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_abstract.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct abstract   
    {   
    virtual int val() = 0;   
    };   
  
int main()   
    {   
    std::cout << "is_abstract<trivial> == " << std::boolalpha   
        << std::is_abstract<trivial>::value << std::endl;   
    std::cout << "is_abstract<abstract> == " << std::boolalpha   
        << std::is_abstract<abstract>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_abstract < trivial > false is_abstract < 추상 > = = = = true  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_polymorphic 클래스](../standard-library/is-polymorphic-class.md)