---
title: "greater_equal 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.greater_equal"
  - "greater_equal"
  - "std::greater_equal"
  - "xfunctional/std::greater_equal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "greater_equal 구조체"
  - "greater_equal 함수"
ms.assetid: a8ba911b-7af8-4653-b972-d8618f4df7d5
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# greater_equal 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이진은 해당 인수에서 보다 크거나 같은 연산자 \(`operator>=`\)를 수행하는지를 예측합니다.  
  
## 구문  
  
```  
template<class Type = void>  
   struct greater_equal : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator>=  
template<>  
   struct greater_equal<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            >= std::forward<Type2>(Right));  
   };  
  
```  
  
#### 매개 변수  
 `Type`, `Type1`, `Type2`  
 유추 또는 지정된 형식의 피연산자를 사용하는 `operator>=` 를 지원하는 모든 형식입니다.  
  
 `Left`  
 큼 또는 같음 연산의 왼쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type1` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
 `Right`  
 큼 또는 같음 연산의 오른쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type2` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
## 반환 값  
 `Left` `>=` `Right`의 결과입니다.  특수화 된 템플릿은 `operator>=` 으로 반환되는 형식의 결과 전달을 완벽히 수행합니다.  
  
## 설명  
 이진 술부 `greater_equal`\<`Type`\> 는 `Type` 형식의 요소 값의 집합을 엄격한 순서로 동일 클래스에 제공하고, 이것은 이 형식이 정렬된 표준 수학 요구 사항이 충족 하는 경우에만 적용됩니다.  포인터 형식에 대한 특수화는 서로 대해 고유한 값의 모든 요소를 정렬 하는 요소의 전체 순서를 생성 합니다.  
  
## 예제  
  
```  
// functional_greater_equal.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
  
   int i;  
   v1.push_back( 6262 );  
   v1.push_back( 6262 );  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      v1.push_back( rand( ) );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,   
   // specify binary predicate greater_equal<int>( )  
   sort( v1.begin( ), v1.end( ), greater_equal<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## Output  
  
```  
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )  
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )  
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )  
```  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)