---
title: "iterator_traits 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::iterator_traits"
  - "xutility/std::iterator_traits"
  - "iterator_traits"
  - "std.iterator_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator_traits 클래스"
  - "iterator_traits 구조체"
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# iterator_traits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A template helper struct used to specify all the critical type definitions that an iterator should have.  
  
## 구문  
  
```  
template<class Iterator>  
    struct iterator_traits {  
        typedef typename Iterator::iterator_category iterator_category;  
        typedef typename Iterator::value_type value_type;  
        typedef typename Iterator::difference_type difference_type;  
        typedef difference_type distance_type;  
        typedef typename Iterator::pointer pointer;  
        typedef typename Iterator::reference reference;  
    };  
template<class Type>  
    struct iterator_traits<Type*> {  
        typedef random_access_iterator_tag iterator_category;  
        typedef Type value_type;  
        typedef ptrdiff_t difference_type;  
        typedef difference_type distance_type;  
        typedef Type *pointer;  
        typedef Type& reference;  
    };  
template<class Type>  
    struct iterator_traits<const Type*> {  
        typedef random_access_iterator_tag iterator_category;  
        typedef Type value_type;  
        typedef ptrdiff_t difference_type;  
        typedef difference_type distance_type;  
        typedef const Type *pointer;  
        typedef const Type& reference;  
    };  
```  
  
## 설명  
 The template struct defines the member types  
  
-   **iterator\_category**: a synonym for **Iterator::iterator\_category**.  
  
-   `value_type`: a synonym for **Iterator::value\_type**.  
  
-   `difference_type`: a synonym for **Iterator::difference\_type**.  
  
-   `distance_type`: a synonym for **Iterator::difference\_type.**  
  
-   **pointer**: a synonym for **Iterator::pointer**.  
  
-   **reference**: a synonym for **Iterator::reference**.  
  
 The partial specializations determine the critical types associated with an object pointer of type **Type \*** or const **Type \***.  
  
 In this implementation you can also use several template functions that do not make use of partial specialization:  
  
```  
template<class Category, class Type, class Diff>  
C _Iter_cat(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    random_access_iterator_tag _Iter_cat(const Ty *);  
  
template<class Category, class Ty, class Diff>  
Ty *_Val_type(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    Ty *_Val_type(const Ty *);  
  
template<class Category, class Ty, class Diff>  
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    ptrdiff_t *_Dist_type(const Ty *);  
```  
  
 which determine several of the same types more indirectly.  You use these functions as arguments on a function call.  Their sole purpose is to supply a useful template class parameter to the called function.  
  
## 예제  
  
```  
// iterator_traits.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <vector>  
#include <list>  
  
using namespace std;  
  
template< class it >  
void  
function( it i1, it i2 )  
{  
   iterator_traits<it>::iterator_category cat;  
   cout << typeid( cat ).name( ) << endl;  
   while ( i1 != i2 )  
   {  
      iterator_traits<it>::value_type x;  
      x = *i1;  
      cout << x << " ";  
      i1++;  
   };     
   cout << endl;  
};  
  
int main( )   
{  
   vector<char> vc( 10,'a' );  
   list<int> li( 10 );  
   function( vc.begin( ), vc.end( ) );  
   function( li.begin( ), li.end( ) );  
}  
```  
  
  **struct std::random\_access\_iterator\_tag**  
**a a a a a a a a a a**   
**struct std::bidirectional\_iterator\_tag**  
**0 0 0 0 0 0 0 0 0 0**    
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)