---
title: "is_default_constructible Class | Microsoft Docs"
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
  - "is_default_constructible"
  - "std.is_default_constructible"
  - "std::is_default_constructible"
  - "type_traits/std::is_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_default_constructible"
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
caps.latest.revision: 14
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_default_constructible Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식에 기본 생성자가 있는지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_default_constructible;  
```  
  
#### 매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 조건자의 인스턴스는 `T` 형식이 기본 생성자가 있는 클래스 형식인 경우 true이고 그렇지 않은 경우 false입니다. 이것은 조건자 `is_constructible<T>`에 해당합니다.`T` 형식은 완전한 형식, `void` 또는 범위를 알 수 없는 배열이어야 합니다.  
  
## 예제  
  
```cpp  
  
#include <type_traits>   
#include <iostream>   
  
struct Simple  
{  
    Simple() : val(0) {}  
    int val;  
};  
  
struct Simple2  
{  
    Simple2(int v) : val(v) {}  
    int val;  
};  
  
int main()  
{  
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha  
        << std::is_default_constructible<Simple>::value << std::endl;  
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha  
        << std::is_default_constructible<Simple2>::value << std::endl;  
  
    return (0);  
}  
  
```  
  
```Output  
is_default_constructible<Simple> == true is_default_constructible<Simple2> == false  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)