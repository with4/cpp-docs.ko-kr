---
title: "rank 클래스 | Microsoft Docs"
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
  - "std::tr1::rank"
  - "std.tr1.rank"
  - "rank"
  - "std.rank"
  - "std::rank"
  - "type_traits/std::rank"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rank 클래스[TR1]"
  - "rank"
ms.assetid: bc9f1b8f-800f-46ca-b6f4-d8579ed5406a
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rank 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열 차원 수를 가져옵니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct rank;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 쿼리는 배열 형식 `Ty`의 차원 수 값이거나, `Ty`가 배열 형식이 아니면 0입니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__rank.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "rank<int> == "   
        << std::rank<int>::value << std::endl;   
    std::cout << "rank<int[5]> == "   
        << std::rank<int[5]>::value << std::endl;   
    std::cout << "rank<int[5][10]> == "   
        << std::rank<int[5][10]>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
순위 < int > 0 순위 < int [5] > = = 1 순위 < int [5] [10] > = = 2 = =  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [extent 클래스](../standard-library/extent-class.md)