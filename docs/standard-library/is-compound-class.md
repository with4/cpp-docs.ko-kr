---
title: "is_compound 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_compound"
  - "is_compound"
  - "std.tr1.is_compound"
  - "std.is_compound"
  - "std::is_compound"
  - "type_traits/std::is_compound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_compound 클래스[TR1]"
  - "is_compound"
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# is_compound 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 형식이 기본 형식이 아닌지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_compound;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자 인스턴스는 `Ty` 형식이 기본 형식인 경우\(즉, [is\_fundamental](../standard-library/is-fundamental-class.md)`<``Ty``>`이 `true`인 경우\) `false` 이고, 그렇지 않으면 `true`입니다.  따라서 `Ty`가 배열 형식, 함수 형식이거나, `void`, 개체 또는 함수에 대한 포인터이거나, 비정적 클래스 멤버에 대한 참조, 클래스, 집합체, 열거형 또는 포인터이거나, 이들 중 하나의 *cv 한정* 형식이면 조건자는 `true`입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_compound\<trivial\> \=\= true**  
**is\_compound\<int\[\]\> \=\= true**  
**is\_compound\<int\(\)\> \=\= true**  
**is\_compound\<int&\> \=\= true**  
**is\_compound\<void \*\> \=\= true**  
**is\_compound\<int\> \=\= false**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_class 클래스](../standard-library/is-class-class.md)