---
title: "add_volatile 클래스 | Microsoft Docs"
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
  - "std::tr1::add_volatile"
  - "add_volatile"
  - "std.tr1.add_volatile"
  - "std.add_volatile"
  - "std::add_volatile"
  - "type_traits/std::add_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_volatile 클래스[TR1]"
  - "add_volatile"
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# add_volatile 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 형식에서 휘발성 형식을 만듭니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct add_volatile;  
  
template<class T>  
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
#### 매개 변수  
 `Ty`  
 수정할 형식입니다.  
  
## 설명  
 `Ty`가 참조, 함수 또는 휘발성 한정 형식인 경우 형식 한정자 인스턴스는 수정된 형식인 `Ty`를 보관합니다. 그렇지 않은 경우 `volatile Ty`입니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_volatile\<int\> \=\= int**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_volatile 클래스](../standard-library/remove-volatile-class.md)