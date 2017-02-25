---
title: "integral_constant 클래스, bool_constant 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.integral_constant"
  - "integral_constant"
  - "std::tr1::integral_constant"
  - "std.integral_constant"
  - "std::integral_constant"
  - "type_traits/std::integral_constant"
  - "std.bool_constant"
  - "std::bool_constant"
  - "type_traits/std::bool_constant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "integral_constant 클래스[TR1]"
  - "integral_constant"
  - "bool_constant"
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# integral_constant 클래스, bool_constant 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 및 값에서 정수 계열을 상수를 만듭니다.  
  
## 구문  
  
```  
template <class T, T v>  
    struct integral_constant {  
        static constexpr T value = v;  
        typedef T value_type;  
        typedef integral_constant<T, v> type;  
        constexpr operator value_type() const noexcept { return (value); }  
        constexpr value_type operator()() const noexcept { return (value); }  
    };  
  
template <bool v>  
    using bool_constant = integral_constant<bool, v>;  
  
```  
  
#### 매개 변수  
 `T`  
 상수의 형식입니다.  
  
 `v`  
 상수의 값입니다.  
  
## 설명  
 `integral_constant` 템플릿 클래스는 정수 계열 형식으로 특수화 된 `T` 값 `v` 해당 형식의 지정 된 값이 해당 정수 계열 형식의 상수를 포함 하는 개체를 나타냅니다. 라는 멤버 `type` 생성 된 템플릿 특수화 형식에 대 한 별칭 및 `value` 멤버 값을 보유 `v` 를 특수화를 만드는 데 사용 합니다.  
  
 `bool_constant` 템플릿 클래스의 명시적 부분 특수화는 `integral_constant` 사용 하 여 `bool` 으로 `T` 인수입니다.  
  
## 예제  
  
```cpp  
// std__type_traits__integral_constant.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "integral_constant<int, 5> == "   
        << std::integral_constant<int, 5>::value << std::endl;   
    std::cout << "integral_constant<bool, false> == " << std::boolalpha   
        << std::integral_constant<bool, false>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
integral_constant < int, 5 > 5 integral_constant < bool false > = = = = false  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [false\_type Typedef](../Topic/false_type%20Typedef.md)   
 [true\_type Typedef](../Topic/true_type%20Typedef.md)