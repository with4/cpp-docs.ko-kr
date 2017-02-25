---
title: "_1 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1._1"
  - "_1"
  - "std::tr1::_1"
  - "functional/std::tr1::_1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_1 개체[TR1]"
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _1 개체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대체 가능한 인수 자리 표시자  
  
## 구문  
  
```  
namespace placeholders {  
  extern unspecified _1, _2, ... _M  
  } // namespace placeholders (within std)  
```  
  
## 설명  
 개체 `_1, _2, ... _M`은 함수 호출에서 각각 첫 번째, 두 번째, ..., M번째 인수를 [bind 함수](../Topic/bind%20Function.md)가 반환한 개체에 지정하는 자리 표시자입니다.  바인딩 식을 계산하는 경우 `_N`을 사용하여 N번째 인수가 삽입될 위치를 지정할 수 있습니다.  
  
 이 구현에서 `M`의 값은 20입니다.  
  
## 예제  
  
```cpp  
// std__functional_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <algorithm>   
#include <iostream>   
  
using namespace std::placeholders;   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
void product(double x, double y)   
    {   
    std::cout << x << "*" << y << " == " << x * y << std::endl;   
    }   
  
int main()   
    {   
    double arg[] = {1, 2, 3};   
  
    std::for_each(&arg[0], &arg[3], square);   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(square, _1));   
  
    return (0);   
    }  
  
```  
  
  **1^2 \=\= 1**  
**2^2 \=\= 4**  
**3^2 \=\= 9**  
**1\*2 \=\= 2**  
**2\*2 \=\= 4**  
**3\*2 \=\= 6**  
**1^2 \=\= 1**  
**2^2 \=\= 4**  
**3^2 \=\= 9**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [bind 함수](../Topic/bind%20Function.md)   
 [is\_placeholder 클래스](../standard-library/is-placeholder-class.md)