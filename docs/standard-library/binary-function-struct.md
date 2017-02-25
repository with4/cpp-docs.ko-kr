---
title: "binary_function 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.binary_function"
  - "functional/std::binary_function"
  - "std::binary_function"
  - "binary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_function 클래스"
ms.assetid: 79b6d53d-644c-4add-b0ba-3a5f40f69c60
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# binary_function 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An empty base struct that defines types that may be inherited by derived classes that provides a binary function object.  
  
## 구문  
  
```  
  
   template<class Arg1, class Arg2, class Result>  
struct binary_function {  
   typedef Arg1 first_argument_type;  
   typedef Arg2 second_argument_type;  
   typedef Result result_type;  
};  
```  
  
## 설명  
 The template struct serves as a base for classes that define a member function of the form:  
  
 **result\_type operator\(\)**\( **const first\_argument\_type&**,  
  
 **const second\_argument\_type&** \) **const**  
  
 All such binary functions can refer to their first argument type as **first\_argument\_type**, their second argument type as **second\_argument\_type**, and their return type as ***result\_type***.  
  
## 예제  
  
```  
// functional_binary_function.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
template <class Type> class average:   
binary_function<Type, Type, Type>   
{  
public:  
   result_type operator( ) ( first_argument_type a,   
                 second_argument_type b )  
   {  
      return (result_type) ( ( a + b ) / 2 );  
   }  
};  
  
int main( )  
{  
   vector <double> v1, v2, v3 ( 6 );  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   for ( int i = 1 ; i <= 6 ; i++ )  
      v1.push_back( 11.0 / i );  
  
   for ( int j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise averages of the elements of v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      average<double>( ) );  
  
   cout << "The element-wise averages are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **벡터 v1 \= \(11 5.5 3.66667 2.75 2.2 1.83333\)**  
**벡터 v2 \= \( \-0 \-2 \-4 \-6 \-8 \-10 \)**  
**The element\-wise averages are: \( 5.5 1.75 \-0.166667 \-1.625 \-2.9 \-4.08333 \)**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [binary\_function 구조체 샘플](../misc/binary-function-structure-sample.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)