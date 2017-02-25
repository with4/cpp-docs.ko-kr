---
title: "is_function 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_function"
  - "std.tr1.is_function"
  - "is_function"
  - "std.is_function"
  - "std::is_function"
  - "type_traits/std::is_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_function 클래스[TR1]"
  - "is_function"
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_function 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 함수 형식인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_function;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 함수 형식인 경우 true이고 그렇지 않은 경우 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_function.cpp   
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
    std::cout << "is_function<trivial> == " << std::boolalpha   
        << std::is_function<trivial>::value << std::endl;   
    std::cout << "is_function<functional> == " << std::boolalpha   
        << std::is_function<functional>::value << std::endl;   
    std::cout << "is_function<float()> == " << std::boolalpha   
        << std::is_function<float()>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_function\<trivial\> \=\= false**  
**is\_function\<functional\> \=\= false**  
**is\_function\<float\(\)\> \=\= true**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_object 클래스](../standard-library/is-object-class.md)