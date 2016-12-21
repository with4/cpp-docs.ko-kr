---
title: "logical_or 구조체 | Microsoft Docs"
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
  - "std.logical_or"
  - "std::logical_or"
  - "logical_or"
  - "xfunctional/std::logical_or"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_or 클래스"
  - "logical_or 구조체"
ms.assetid: ec8143f8-5755-4e7b-8025-507fb6bf6911
caps.latest.revision: 22
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# logical_or 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

해당 인수에서 논리합 연산을 \(`operator||`\) 수행하는 미리 정의된 함수 개체입니다.  
  
## 구문  
  
```  
template<class Type = void>  
   struct logical_or : public binary_function<Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator||  
template<>  
   struct logical_or<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            || std::forward<Type2>(Right));  
   };  
  
```  
  
#### 매개 변수  
 `Type`, `Type1`, `Type2`  
 유추 또는 지정된 형식의 피연산자를 사용하는 `operator||` 를 지원하는 모든 형식입니다.  
  
 `Left`  
 논리합 연산의 왼쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type1` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
 `Right`  
 논리합 연산의 오른쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type2` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
## 반환 값  
 `Left` `||` `Right`의 결과입니다.  특수화 된 템플릿은 `operator||` 으로 반환되는 형식의 결과 전달을 완벽히 수행합니다.  
  
## 설명  
 사용자 정의 형식에 대해서는 피연산자 평가 단락이 없습니다.  두 인수는 `operator||` 에 의해 측정됩니다.  
  
## 예제  
  
```  
// functional_logical_or.cpp  
// compile with: /EHsc  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque <bool> d1, d2, d3( 7 );  
   deque <bool>::iterator iter1, iter2, iter3;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      d1.push_back((bool)((rand() % 2) != 0));  
   }  
  
   int j;  
   for ( j = 0 ; j < 7 ; j++ )  
   {  
      d2.push_back((bool)((rand() % 2) != 0));  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "Original deque:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
  
   // To find element-wise disjunction of the truth values  
   // of d1 & d2, use the logical_or function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),  
      d3.begin( ), logical_or<bool>( ) );  
   cout << "The deque which is the disjuction of d1 & d2 is:\n d3 = ( " ;  
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )  
      cout << *iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **기존 deque:**  
 **d1 \= \( true true false false true false false \)**  
**기존 deque:**  
 **d2 \= \( false false false true true true true \)**  
**d1 & d2 의 분리 deque:**  
 **d3 \= \( true true false true true true true \)**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)