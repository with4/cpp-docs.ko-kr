---
title: "binary_negate 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::binary_negate"
  - "std::binary_negate"
  - "binary_negate"
  - "std.binary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_negate 클래스"
ms.assetid: 7b86f02c-af7e-4c7f-9df1-08addae4dd65
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# binary_negate 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 이항 함수의 반환 값을 무효화하는 멤버 함수를 제공하는 템플릿 클래스.  
  
## 구문  
  
```  
  
   template<class Operation>  
class binary_negate  
   : public binary_function <  
      typename Operation::first_argument_type,  
      typename Operation::second_argument_type,   
      bool>   
{  
public:  
explicit binary_negate(  
   const Operation& _Func  
);  
bool operator()(  
   const typename Operation::first_argument_type& _Left,  
   const typename Operation::second_argument_type& _Right  
) const;  
};  
```  
  
#### 매개 변수  
 `_Func`  
 The binary function to be negated.  
  
 `_Left`  
 The left operand of the binary function to be negated.  
  
 `_Right`  
 The right operand of the binary function to be negated.  
  
## 반환 값  
 The negation of the binary function.  
  
## 설명  
 The template class stores a copy of a binary function object \_*Func*.  It defines its member function `operator()` as returning **\!**\_*Func\(\_Left, \_Right\).*  
  
 The constructor of `binary_negate` is rarely used directly.  The helper function [not2](../Topic/not2%20Function.md) is usually preferred to declare and use the **binary\_negator** adaptor predicate.  
  
## 예제  
  
```  
// functional_binary_negate.cpp  
// compile with: /EHsc  
#define _CRT_RAND_S  
#include <stdlib.h>  
  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <unsigned int> v1;  
   vector <unsigned int>::iterator Iter1;  
  
   unsigned int i;  
   v1.push_back( 6262 );  
   v1.push_back( 6262 );  
   unsigned int randVal = 0;  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      rand_s(&randVal);  
      v1.push_back( randVal );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<unsigned int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,  
   // use the binary_negate function  
   sort( v1.begin( ), v1.end( ),  
   binary_negate<less<unsigned int> >(less<unsigned int>( ) ) );  
  
   // The helper function not2 could also have been used  
   // in the above line and is usually preferred for convenience  
   // sort( v1.begin( ), v1.end( ), not2(less<unsigned int>( ) ) );  
  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Original vector v1 \= \( 6262 6262 2233879413 2621500314 580942933 3715465425 3739828298 \)**  
**Sorted vector v1 \= \( 6262 6262 580942933 2233879413 2621500314 3715465425 3739828298 \)**  
**Resorted vector v1 \= \( 3739828298 3715465425 2621500314 2233879413 580942933 6262 6262 \)**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)