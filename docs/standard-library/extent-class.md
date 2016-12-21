---
title: "extent 클래스 | Microsoft Docs"
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
  - "std.tr1.extent"
  - "extent"
  - "std::tr1::extent"
  - "std.extent"
  - "std::extent"
  - "type_traits/std::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent 클래스[TR1]"
  - "extent"
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# extent 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열 차원을 가져옵니다.  
  
## 구문  
  
```  
template<class Ty, unsigned I = 0>  
    struct extent;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
 `I`  
 쿼리에 바인딩되는 배열입니다.  
  
## 설명  
 `Ty`가 `I` 이상의 차원을 가진 배열 형식인 경우 형식 쿼리에는 `I`에서 지정되는 차원의 요소 수가 포함됩니다.  `Ty`가 배열 형식이 아니거나 순위가 `I`보다 작은 경우, 또는 `I`가 0이고 `Ty`가 "범위를 알 수 없는 배열 `U`" 형식인 경우 형식 쿼리는 0 값을 가집니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **범위 0 \=\= 5**  
**범위 1 \=\= 10**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_all\_extents 클래스](../standard-library/remove-all-extents-class.md)   
 [remove\_extent 클래스](../standard-library/remove-extent-class.md)