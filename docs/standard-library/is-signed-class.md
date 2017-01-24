---
title: "is_signed 클래스 | Microsoft Docs"
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
  - "is_signed"
  - "std.tr1.is_signed"
  - "std::tr1::is_signed"
  - "std.is_signed"
  - "std::is_signed"
  - "type_traits/std::is_signed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_signed 클래스[TR1]"
  - "is_signed"
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_signed 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 부호 있는 정수인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_signed;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 부호 있는 정수계열 형식 또는 `cv-qualified` 부호 있는 정수 계열 형식인 경우 true이고, 그렇지 않은 경우 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_signed.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_signed<trivial> == " << std::boolalpha   
        << std::is_signed<trivial>::value << std::endl;   
    std::cout << "is_signed<int> == " << std::boolalpha   
        << std::is_signed<int>::value << std::endl;   
    std::cout << "is_signed<unsigned int> == " << std::boolalpha   
        << std::is_signed<unsigned int>::value << std::endl;   
    std::cout << "is_signed<float> == " << std::boolalpha   
        << std::is_signed<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_signed\<trivial\> \=\= false**  
**is\_signed\<int\> \=\= true**  
**is\_signed\<unsigned int\> \=\= false**  
**is\_signed\<float\> \=\= false**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_unsigned 클래스](../standard-library/is-unsigned-class.md)