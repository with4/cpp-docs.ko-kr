---
title: "add_lvalue_reference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::add_lvalue_reference"
  - "add_lvalue_reference"
  - "type_traits/std::add_lvalue_reference"
  - "std.add_lvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_lvalue_reference"
ms.assetid: 9933afc2-ad0d-465d-98fe-7d547fa3efe2
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# add_lvalue_reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에서 형식에 대한 참조를 만듭니다.  
  
## 구문  
  
```  
template<class T>  
    struct add_lvalue_reference;  
  
template<class T>  
    using add_lvalue_reference_t = typename add_lvalue_reference<T>::type;  
```  
  
#### 매개 변수  
 `T`  
 수정할 형식입니다.  
  
## 설명  
 형식 한정자의 인스턴스는 `T`가 lvalue 참조인 경우 `T`인 수정된 형식이고 그렇지 않은 경우 `T&`입니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
using namespace std;  
int main()  
{  
    int val = 0;  
    add_lvalue_reference_t<int> p = (int&)val;  
    p = p;  // to quiet "unused" warning   
    cout << "add_lvalue_reference_t<int> == "  
        << typeid(p).name() << endl;  
  
    return (0);  
}  
```  
  
  **add\_lvalue\_reference\_t\<int\> \=\= int**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_reference 클래스](../standard-library/remove-reference-class.md)