---
title: "remove_reference 클래스 | Microsoft Docs"
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
  - "std.tr1.remove_reference"
  - "std::tr1::remove_reference"
  - "remove_reference"
  - "std.remove_reference"
  - "std::remove_reference"
  - "type_traits/std::remove_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_reference 클래스[TR1]"
  - "remove_reference"
ms.assetid: 294e1965-3ae3-46ee-bc42-4fdf60c24717
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove_reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에서 비참조 형식을 만듭니다.  
  
## 구문  
  
```  
template<class T>  
    struct remove_reference;  
  
template<class T>  using remove_reference_t = typename remove_reference<T>::type;  
```  
  
#### 매개 변수  
 `T`  
 수정할 형식입니다.  
  
## 설명  
 `remove_reference<T>`의 인스턴스는 `T1`가 `T` 형식인 경우 수정된 형식인 `T1&`을 보관하고, 그렇지 않은 경우 `T`를 보관합니다.  
  
## 예제  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_reference_t<int&> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_reference_t<int&> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
remove_reference_t<int&> == int  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_lvalue\_reference 클래스](../standard-library/add-lvalue-reference-class.md)