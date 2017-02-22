---
title: "remove_const 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.remove_const"
  - "std::tr1::remove_const"
  - "remove_const"
  - "std.remove_const"
  - "std::remove_const"
  - "type_traits/std::remove_const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_const 클래스[TR1]"
  - "remove_const"
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# remove_const 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에서 비const 형식을 만듭니다.  
  
## 구문  
  
```  
template<class T>  
    struct remove_const;  
```  
  
```  
template<class T>  
  using remove_const_t = typename remove_const<T>::type;  
```  
  
#### 매개 변수  
 `T`  
 수정할 형식입니다.  
  
## 설명  
 `remove_const<T>`의 인스턴스는 `T1`가 `T` 형식인 경우 수정된 형식인 `const T1`을 보관하고, 그렇지 않은 경우 `T`를 보관합니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_const_t<const int>*)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_const_t<const int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_const\_t\<const int\> \=\= int**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_const 클래스](../standard-library/add-const-class.md)   
 [remove\_cv 클래스](../standard-library/remove-cv-class.md)