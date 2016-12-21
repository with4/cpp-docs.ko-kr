---
title: "plus 구조체 | Microsoft Docs"
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
  - "xfunctional/std::plus"
  - "std.plus"
  - "plus"
  - "std::plus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "plus 클래스"
  - "plus 구조체"
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# plus 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

해당 인수에서 덧셈 연산을 \(이진 `operator+`\) 수행하는 미리 정의된 함수 개체입니다.  
  
## 구문  
  
```  
template<class Type = void>  
   struct plus : public binary_function <Type, Type, Type>   
   {  
      Type operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator+  
template<> struct plus<void>  
   {  
   template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
      -> decltype(std::forward<Type1>(Left)  
         + std::forward<Type2>(Right));  
   };  
  
```  
  
#### 매개 변수  
 `Type`, `Type1`, `Type2`  
 유추 또는 지정된 형식의 피연산자를 사용하는 이진 `operator+` 를 지원하는 형식입니다.  
  
 `Left`  
 덧셈 연산의 왼쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type1` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
 `Right`  
 덧셈 연산의 오른쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type2` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
## 반환 값  
 `Left` `+` `Right`의 결과입니다.  특수화 된 템플릿은 이진 `operator+` 으로 반환되는 형식의 결과 전달을 완벽히 수행합니다.  
  
## 예제  
  
```  
// functional_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v1, v2, v3 ( 6 );  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 0 ; i <= 5 ; i++ )  
      v1.push_back( 4 * i );  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j - 4 );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise sums of the elements of v1 & v2  
   transform (v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ), plus<double>( ) );  
  
   cout << "The element-wise sums are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **벡터 v1 \= \(0 4 8 12 16 20\)**  
**벡터 v2 \= \( \-4 \-6 \-8 \-10 \-12 \-14 \)**  
**Element\-wise 합계는: \(\-4 0 2 4 6\-2\)**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)