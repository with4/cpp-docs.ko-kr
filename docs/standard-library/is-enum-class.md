---
title: "is_enum 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_enum"
  - "std.tr1.is_enum"
  - "std::tr1::is_enum"
  - "std.is_enum"
  - "std::is_enum"
  - "type_traits/std::is_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_enum 클래스[TR1]"
  - "is_enum"
ms.assetid: df3b00b7-4f98-4b3a-96ce-10ad958ee69c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_enum 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 열거형인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_enum;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 열거형 형식이거나 열거형 형식의 `cv-qualified` 형태인 경우 true이고 그렇지 않은 경우 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_enum.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
enum color {   
    red, greed, blue};   
  
int main()   
    {   
    std::cout << "is_enum<trivial> == " << std::boolalpha   
        << std::is_enum<trivial>::value << std::endl;   
    std::cout << "is_enum<color> == " << std::boolalpha   
        << std::is_enum<color>::value << std::endl;   
    std::cout << "is_enum<int> == " << std::boolalpha   
        << std::is_enum<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_enum\<trivial\> \=\= false**  
**is\_enum\<color\> \=\= true**  
**is\_enum\<int\> \=\= false**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_integral 클래스](../standard-library/is-integral-class.md)