---
title: "tuple_size 클래스 &lt;utility&gt; | Microsoft Docs"
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
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_size 클래스 <utility>(TR1)"
ms.assetid: 36d04207-ed87-4c11-9875-150c59833b79
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_size 클래스 &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`pair` 요소 개수를 래핑합니다.  
  
## 구문  
  
```  
template<class Tuple>  
struct tuple_size;  
  
template<class T1, class T2>  
struct tuple_size<pair<T1, T2>>   : integral_constant<size_t, 2>  
  
// size of const tuple  
template<class Tuple>  
struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template<class Tuple>  
struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template<class Tuple>  
struct tuple_size<const volatile Tuple>;  
```  
  
#### 매개 변수  
 `T1`  
 첫 번째 pair 요소의 형식입니다.  
  
 `T2`  
 두 번째 pair 요소의 형식입니다.  
  
## 설명  
 이 템플릿은 템플릿 클래스 [tuple\_size 클래스](../standard-library/tuple-size-class-tuple.md)의 특수화입니다. 해당 값이 2인 정수 계열 상수 식인 `value` 멤버가 있습니다.  
  
## 예제  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
  
int main()  
{  
    MyPair c0(0, 1.1);  
  
    // display contents " 0 1.1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display size " 2"   
    cout << " " << tuple_size<MyPair>::value << endl;  
  
}  
  
/*  
Output:  
0 1.1  
2  
*/  
```  
  
## 요구 사항  
 **헤더:** \<utility\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<utility\>](../standard-library/utility.md)   
 [get 함수](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_element 클래스](../standard-library/tuple-element-class-utility.md)