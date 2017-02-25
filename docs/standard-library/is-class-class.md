---
title: "is_class 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_class"
  - "std::tr1::is_class"
  - "std.tr1.is_class"
  - "std.is_class"
  - "std::is_class"
  - "type_traits/std::is_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_class 클래스[TR1]"
  - "is_class"
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_class 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 클래스인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_class;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 `class`, `struct` 또는 두 형식 중 하나의 `cv-qualified` 형태로 정의된 형식인 경우 true이고 그렇지 않은 경우 false입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_class.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_class<trivial> == " << std::boolalpha   
        << std::is_class<trivial>::value << std::endl;   
    std::cout << "is_class<int> == " << std::boolalpha   
        << std::is_class<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_class\<trivial\> \=\= true**  
**is\_class\<int\> \=\= false**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound 클래스](../standard-library/is-compound-class.md)   
 [is\_union 클래스](../standard-library/is-union-class.md)