---
title: "tuple_element 클래스 &lt;utility&gt; | Microsoft Docs"
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
  - "std.tr1.tuple_element"
  - "tuple_element"
  - "std::tr1::tuple_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_element 클래스 <utility>(TR1)"
ms.assetid: f9db79e8-685c-49e3-97ee-81763e516ce3
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element 클래스 &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`pair` 요소의 형식을 래핑합니다.  
  
## 구문  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
// struct to determine type of element 0 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<0, pair<Ty1, Ty2> >;  
  
// struct to determine type of element 1 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<1, pair<Ty1, Ty2> >;  
  
// tuple_element for const  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const Tuple>;  
  
// tuple_element for volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, volatile Tuple>;  
  
// tuple_element for const volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const volatile Tuple>;  
  
template<size_t Index, class Tuple>  
using tuple_element_t = typename tuple_element<Index, Tuple>::type;  
```  
  
#### 매개 변수  
 Index  
 요소의 위치이며, pair에 대한 이 값은 0 또는 1입니다.  
  
 `T1`  
 첫 번째 pair 요소의 형식입니다.  
  
 `T2`  
 두 번째 pair 요소의 형식입니다.  
  
 type  
  
## 설명  
 템플릿은 템플릿 클래스 [tuple\_element 클래스](../standard-library/tuple-element-class-tuple.md)의 특수화입니다. 각각에는 단일 멤버 typedef인 `type`이 있으며, 모든 const 및\/또는 volatile 한정자가 유지되는, `pair`의 지정된 위치에 있는 요소의 형식에 대한 동의어입니다.`tuple_element_t`는 `tuple_element<N, pair<T1, T2>>::type`에 대한 편리한 별칭입니다. 요소를 지정된 위치 또는 지정된 형식\(C\+\+14\/Visual Studio 2015\)으로 반환하려면 [get 함수](../Topic/get%20Function%20%3Cutility%3E.md)을 사용합니다.  
  
## 예제  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
int main()  
{  
    MyPair c0(0, 1.333);  
  
    // display contents " 0 1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display first element " 0" by index  
    tuple_element<0, MyPair>::type val = get<0>(c0);  
    cout << " " << val;  
  
    // display second element by type   
    tuple_element<1, MyPair>::type val2 = get<double>(c0);  
    cout << " " << val2 << endl;  
}  
  
/*  
Output:  
0 1.333  
0 1.333  
*/  
```  
  
## 요구 사항  
 **헤더:** \<utility\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<utility\>](../standard-library/utility.md)   
 [get 함수](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_size 클래스](../standard-library/tuple-size-class-utility.md)