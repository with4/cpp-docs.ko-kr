---
title: "is_fundamental 클래스 | Microsoft Docs"
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
  - "is_fundamental"
  - "std.tr1.is_fundamental"
  - "std::tr1::is_fundamental"
  - "std.is_fundamental"
  - "std::is_fundamental"
  - "type_traits/std::is_fundamental"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_fundamental 클래스[TR1]"
  - "is_fundamental"
ms.assetid: b84eee84-2fb2-4611-beaf-b384074d8b6a
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_fundamental 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 void 또는 산술형인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_fundamental;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 `void`, 정수 형식, 부동 소수점 형식 또는 이들 형식 중 하나의 `cv-qualified` 형식이면 true이고, 그렇지 않으면 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_fundamental.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_fundamental<trivial> == " << std::boolalpha   
        << std::is_fundamental<trivial>::value << std::endl;   
    std::cout << "is_fundamental<int> == " << std::boolalpha   
        << std::is_fundamental<int>::value << std::endl;   
    std::cout << "is_fundamental<const float> == " << std::boolalpha   
        << std::is_fundamental<const float>::value << std::endl;   
    std::cout << "is_fundamental<void> == " << std::boolalpha   
        << std::is_fundamental<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_fundamental\<trivial\> \=\= false**  
**is\_fundamental\<int\> \=\= true**  
**is\_fundamental\<const float\> \=\= true**  
**is\_fundamental\<void\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound 클래스](../standard-library/is-compound-class.md)