---
title: "less_equal 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::less_equal"
  - "xfunctional/std::less_equal"
  - "std.less_equal"
  - "less_equal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "less_equal 함수"
  - "less_equal 구조체"
ms.assetid: 32085782-c7e0-4310-9b40-8aa3c1bff211
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# less_equal 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이진은 해당 인수에서 보다 적거나 같은 연산자 \(`operator<=`\)를 수행하는지를 예측합니다.\\  
  
## 구문  
  
```  
template<class Type = void>  
   struct less_equal : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator<=  
template<>  
   struct less_equal<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            <= std::forward<Type2>(Right));  
   };  
  
```  
  
#### 매개 변수  
 `Type`, `Type1`, `Type2`  
 유추 또는 지정된 형식의 피연산자를 사용하는 `operator<=` 를 지원하는 모든 형식입니다.  
  
 `Left`  
 작거나 같은 연산의 왼쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type1` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
 `Right`  
 작거나 같은 연산의 오른쪽 피연산자입니다.  특수화 되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 취합니다.  특수화 되지 않은 템플릿은 암시된 `Type2` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
## 반환 값  
 `Left` `<=` `Right`의 결과입니다.  특수화 된 템플릿은 `operator<=` 으로 반환되는 형식의 결과 전달을 완벽히 수행합니다.  
  
## 설명  
 이진 술부 `less_equal`\<`Type`\> 는 `Type` 형식의 요소 값의 집합을 엄격한 순서로 동일 클래스에 제공하고, 이것은 이 형식이 정렬된 표준 수학 요구 사항이 충족 하는 경우에만 적용됩니다.  포인터 형식에 대한 특수화는 서로 대해 고유한 값의 모든 요소를 정렬 하는 요소의 전체 순서를 생성 합니다.  
  
## 예제  
  
```  
// functional_less_equal.cpp  
// compile with: /EHsc  
#define _CRT_RAND_S  
#include <stdlib.h>  
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
   vector <int>::reverse_iterator rIter1;  
   unsigned int randomNumber;  
  
   int i;  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      if ( rand_s( &randomNumber ) == 0 )  
      {  
         // Convert the random number to be between 1 - 50000  
         // This is done for readability purposes  
         randomNumber = ( unsigned int) ((double)randomNumber /   
            (double) UINT_MAX * 50000) + 1;  
  
         v1.push_back( randomNumber );  
      }  
   }  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      v1.push_back( 2836 );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use the binary predicate less_equal<int>( )  
   sort( v1.begin( ), v1.end( ), less_equal<int>( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## 샘플 출력  
  
```  
Original vector v1 = ( 31247 37154 48755 15251 6205 2836 2836 2836 )  
Sorted vector v1 = ( 2836 2836 2836 6205 15251 31247 37154 48755 )  
```  
  
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)