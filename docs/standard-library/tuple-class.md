---
title: "tuple 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::tuple"
  - "std.tr1.tuple"
  - "tuple"
  - "tr1.tuple"
  - "std::tr1::tuple"
  - "tuple/std::tr1::tuple"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple 클래스"
  - "tuple 클래스[TR1]"
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# tuple 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wraps a fixed\-length sequence of elements.  
  
## 구문  
  
```  
template<class T1, class T2, ..., class TN>  
class tuple {  
public:  
    tuple();  
    explicit tuple(P1, P2, ..., PN);              // 0 < N  
    tuple(const tuple&);  
    template <class U1, class U2, ..., class UN>  
        tuple(const tuple<U1, U2, ..., UN>&);  
    template <class U1, class U2>  
        tuple(const pair<U1, U2>&);               // N == 2  
    void swap(tuple& right);  
    tuple& operator=(const tuple&);  
    template <class U1, class U2, ..., class UN>  
        tuple& operator=(const tuple<U1, U2, ..., UN>&);  
    template <class U1, class U2>  
        tuple& operator=(const pair<U1, U2>&);    // N == 2  
    };  
```  
  
#### 매개 변수  
 `TN`  
 The type of the Nth tuple element.  
  
## 설명  
 The template class describes an object that stores N objects of types `T1`, `T2`, ..., `TN`, respectively, where where `0 <= N <= Nmax`.  The extent of a tuple instance `tuple<T1, T2, ..., TN>` is the number `N` of its template arguments.  The index of the template argument `Ti` and of the corresponding stored value of that type is `i - 1`.  Thus, while we number the types from 1 to N in this documentation, the corresponding index values range from 0 to N \- 1.  
  
## 예제  
  
```  
// tuple.cpp  
// compile with: /EHsc  
  
#include <vector>  
#include <iomanip>  
#include <iostream>  
#include <tuple>  
#include <string>  
  
using namespace std;  
  
typedef tuple <int, double, string> ids;  
  
void print_ids(const ids& i)  
{  
   cout << "( "  
        << get<0>(i) << ", "   
        << get<1>(i) << ", "   
        << get<2>(i) << " )." << endl;  
}  
  
int main( )  
{  
   // Using the constructor to declare and initialize a tuple  
   ids p1(10, 1.1e-2, "one");  
  
   // Compare using the helper function to declare and initialize a tuple  
   ids p2;  
   p2 = make_tuple(10, 2.22e-1, "two");  
  
   // Making a copy of a tuple  
   ids p3(p1);  
  
   cout.precision(3);  
   cout << "The tuple p1 is: ( ";  
   print_ids(p1);  
   cout << "The tuple p2 is: ( ";  
   print_ids(p2);  
   cout << "The tuple p3 is: ( ";  
   print_ids(p3);  
  
   vector<ids> v;  
  
   v.push_back(p1);  
   v.push_back(p2);  
   v.push_back(make_tuple(3, 3.3e-2, "three"));  
  
   cout << "The tuples in the vector are" << endl;  
   for(vector<ids>::const_iterator i = v.begin(); i != v.end(); ++i)  
   {  
      print_ids(*i);  
   }  
}  
```  
  
  **The tuple p1 is: \( 10, 0.011, one \).**  
**The tuple p2 is: \( 10, 0.222, two \).**  
**The tuple p3 is: \( 10, 0.011, one \).**  
**The tuples in the vector are**  
**\( 10, 0.011, one \).**  
**\( 10, 0.222, two \).**  
**\( 3, 0.033, three \).**   
## 요구 사항  
 **Header:** \<tuple\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<tuple\>](../standard-library/tuple.md)   
 [make\_tuple 함수](../Topic/make_tuple%20Function.md)