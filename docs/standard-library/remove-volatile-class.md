---
title: "remove_volatile 클래스 | Microsoft Docs"
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
  - "std::tr1::remove_volatile"
  - "std.tr1.remove_volatile"
  - "remove_volatile"
  - "std.remove_volatile"
  - "std::remove_volatile"
  - "type_traits/std::remove_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_volatile 클래스[TR1]"
  - "remove_volatile"
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove_volatile 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에서 비휘발성 형식을 만듭니다.  
  
## 구문  
  
```  
template<class T>  
    struct remove_volatile;  
  
template<class T>  
  using remove_volatile_t = typename remove_volatile<T>::type;  
```  
  
#### 매개 변수  
 `T`  
 수정할 형식입니다.  
  
## 설명  
 `remove_volatile<T>`의 인스턴스는 `T1`가 `T` 형식인 경우 수정된 형식인 `volatile T1`을 보관하고, 그렇지 않은 경우 `T`를 보관합니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_volatile_t<volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << " remove_volatile_t<volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_volatile\_t\<volatile int\> \=\= int**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_volatile 클래스](../standard-library/add-volatile-class.md)