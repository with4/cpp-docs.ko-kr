---
title: "is_arithmetic 클래스 | Microsoft Docs"
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
  - "is_arithmetic"
  - "std.tr1.is_arithmetic"
  - "std::tr1::is_arithmetic"
  - "std.is_arithmetic"
  - "std::is_arithmetic"
  - "type_traits/std::is_arithmetic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_arithmetic 클래스[TR1]"
  - "is_arithmetic"
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_arithmetic 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

산술 형식인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_arithmetic;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 산술 형식, 즉 정수 형식이나 부동 소수점 형식 또는 이러한 형식 중 하나의 `cv-qualified` 형태인 경우 true이고 그렇지 않은 경우 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_arithmetic.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha   
        << std::is_arithmetic<trivial>::value << std::endl;   
    std::cout << "is_arithmetic<int> == " << std::boolalpha   
        << std::is_arithmetic<int>::value << std::endl;   
    std::cout << "is_arithmetic<float> == " << std::boolalpha   
        << std::is_arithmetic<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_arithmetic\<trivial\> \=\= false**  
**is\_arithmetic\<int\> \=\= true**  
**is\_arithmetic\<float\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_floating\_point 클래스](../standard-library/is-floating-point-class.md)   
 [is\_integral 클래스](../standard-library/is-integral-class.md)