---
title: "add_const 클래스 | Microsoft Docs"
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
  - "std::tr1::add_const"
  - "add_const"
  - "std.tr1.add_const"
  - "std.add_const"
  - "std::add_const"
  - "type_traits/std::add_const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_const 클래스[TR1]"
  - "add_const"
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# add_const 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에서 const 형식을 만듭니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct add_const;  
```  
  
#### 매개 변수  
 `Ty`  
 수정할 형식입니다.  
  
## 설명  
 `Ty`가 참조, 함수 또는 const 한정 형식인 경우 형식 한정자 인스턴스는 수정된 형식인 `Ty`이고, 그렇지 않은 경우 `const Ty`입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__add_const.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_const<int>::type *p = (const int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_const<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_const\<int\> \=\= int**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_const 클래스](../standard-library/remove-const-class.md)