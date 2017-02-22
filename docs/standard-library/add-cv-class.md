---
title: "add_cv 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.add_cv"
  - "add_cv"
  - "std::tr1::add_cv"
  - "std.add_cv"
  - "std::add_cv"
  - "type_traits/std::add_cv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_cv 클래스[TR1]"
  - "add_cv"
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# add_cv 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에서 const\/volatile 형식을 만듭니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct add_cv;  
  
template<class T>  
using add_cv_t = typename add_cv<T>::type;  
```  
  
#### 매개 변수  
 `Ty`  
 수정할 형식입니다.  
  
## 설명  
 형식 수정자의 인스턴스는 수정된 형식인 [add\_volatile 클래스](../standard-library/add-volatile-class.md)`<` [add\_const 클래스](../standard-library/add-const-class.md)`<Ty> >`를 보관합니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_cv_t<int> *p = (const volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_cv<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_cv\_t\<int\> \=\= int**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_const 클래스](../standard-library/remove-const-class.md)   
 [remove\_volatile 클래스](../standard-library/remove-volatile-class.md)