---
title: "add_pointer 클래스 | Microsoft Docs"
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
  - "std::tr1::add_pointer"
  - "std.tr1.add_pointer"
  - "add_pointer"
  - "std.add_pointer"
  - "std::add_pointer"
  - "type_traits/std::add_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_pointer 클래스[TR1]"
  - "add_pointer"
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# add_pointer 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 형식에서 포인터\-형식을 만듭니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct add_pointer;  
  
template<class T>  
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### 매개 변수  
 `Ty`  
 수정할 형식입니다.  
  
## 설명  
 `remove_reference<T>::type*`과 동일한 멤버 typedef 형식 이름입니다.  
  
 참조에서 포인터를 만드는 것은 잘못이기 때문에 `add_pointer`가 포인터\-형식을 만들기 전에 지정된 형식에서 참조\(있는 경우\)를 제거합니다.  결과적으로, 형식이 참조인지 걱정하지 않고도 `add_pointer`를 포함하여 형식을 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `add_pointer` 형식이 해당 형식의 포인터와 같은 경우를 보여 줍니다.  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_pointer\_t\<int\> \=\= int \***   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_pointer 클래스](../standard-library/remove-pointer-class.md)