---
title: "divides 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::divides
- divides
dev_langs:
- C++
helpviewer_keywords:
- divides struct
- divides class
ms.assetid: b9cf8e9c-6981-43a6-a6a3-8f761987dd7a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: a82ec380e3be786dfdac2b8ebe3b108d5776c3a9
ms.lasthandoff: 02/24/2017

---
# <a name="divides-struct"></a>divides 구조체
인수에 대해 나누기 연산(`operator/`)을 수행하는 사전 정의된 함수 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Type = void>
struct divides : public binary_function <Type, Type, Type>  
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator/
template <>
struct divides<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    -> decltype(std::forward<T>(Left)*/ std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>매개 변수  
 `Type`, `T`, `U`  
 지정되었거나 유추된 형식의 피연산자를 가져오는 `operator/`를 지원하는 형식입니다.  
  
 `Left`  
 나누기 연산의 왼쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `T`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.  
  
 `Right`  
 나누기 연산의 오른쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `U`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.  
  
## <a name="return-value"></a>반환 값  
 `Left``/``Right`의 결과입니다. 특수화된 템플릿은 `operator/`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// functional_divides.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v1, v2, v3 (6);  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 0 ; i <= 5 ; i++ )  
   {  
      v1.push_back( 7.0 * i );  
   }  
  
   int j;  
   for ( j = 1 ; j <= 6 ; j++ )  
   {  
      v2.push_back( 2.0 * j);  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise quotients of the elements of v1 & v2  
   transform ( v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ),   
      divides<double>( ) );  
  
   cout << "The element-wise quotients are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
  
/* Output:  
The vector v1 = ( 0 7 14 21 28 35 )  
The vector v2 = ( 2 4 6 8 10 12 )  
The element-wise quotients are: ( 0 1.75 2.33333 2.625 2.8 2.91667 )  
*/  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<functional>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)




