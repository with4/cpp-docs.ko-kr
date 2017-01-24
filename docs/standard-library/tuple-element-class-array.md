---
title: "tuple_element 클래스 &lt;array&gt; | Microsoft Docs"
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
  - "tuple_element 클래스 <array>(TR1)"
ms.assetid: 99201ca4-190a-4d9e-9013-de95ddfe5901
caps.latest.revision: 21
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element 클래스 &lt;array&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열 요소의 형식을 래핑합니다.  
  
## 구문  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
template<size_t Index, class T, size_t Size>  
struct tuple_element<Index, array<T, Size>>  
  
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
  
## 매개 변수  
 `Index`  
 요소 위치입니다.  
  
 `T`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
## 설명  
 이 템플릿 클래스는 배열에 대한 템플릿 클래스 [tuple\_element 클래스](../standard-library/tuple-element-class-tuple.md)의 특수화입니다. 이 클래스는 각각 동일한 형식을 갖는 N개 요소의 튜플로 배열에 대한 인터페이스를 제공합니다. 각 특수화에는 `array`의 `Index` 요소 형식에 대한 동의어인 중첩된 typedef `type`이 있어 모든 const\-volatile 한정자가 유지됩니다.  
  
## 예제  
  
```  
  
#include <array>   
#include <iostream>   
  
using namespace std;  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display first element " 0"   
    tuple_element<0, MyArray>::type val = c0.front();  
    cout << " " << val << endl;  
}  
  
/*  
Output:  
0 1 2 3  
0  
*/  
  
```  
  
## 요구 사항  
 **헤더:** \<array\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<array\>](../standard-library/array.md)   
 [\<tuple\>](../standard-library/tuple.md)   
 [tuple\_element 클래스](../standard-library/tuple-element-class-tuple.md)