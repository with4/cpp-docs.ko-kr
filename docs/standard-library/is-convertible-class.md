---
title: "is_convertible 클래스 | Microsoft Docs"
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
  - "is_convertible"
  - "std.tr1.is_convertible"
  - "std::tr1::is_convertible"
  - "std.is_convertible"
  - "std::is_convertible"
  - "type_traits/std::is_convertible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_convertible 클래스[TR1]"
  - "is_convertible"
ms.assetid: 75614008-1894-42ea-bd57-974399628536
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_convertible 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

한 가지 형식을 다른 형식으로 변환할 수 있는지 여부를 테스트합니다.  
  
## 구문  
  
```  
template<class From, class To>  
    struct is_convertible;  
```  
  
#### 매개 변수  
 `From`  
 변환할 원본 형식입니다.  
  
 `Ty`  
 변환할 대상 형식입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 식 `To to = from;`이 올바른 형식인 경우 true입니다\(여기서 `from`은 `From` 형식의 개체임\).  
  
## 예제  
  
```  
// std_tr1__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_convertible\<trivial, int\> \=\= false**  
**is\_convertible\<trivial, trivial\> \=\= true**  
**is\_convertible\<char, int\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_base\_of 클래스](../standard-library/is-base-of-class.md)