---
title: "equal_to 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- equal_to
- xfunctional/std::equal_to
dev_langs:
- C++
helpviewer_keywords:
- equal_to function
- equal_to struct
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: bac0d0114b10fc4ac7a83a60f21db5218cb3f1c8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="equalto-struct"></a>equal_to 구조체
인수에서 같음 연산(`operator==`)을 수행하는 이진 조건자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Type = void>  
struct equal_to : public binary_function<Type, Type, bool>   
 {  
    bool operator()(const Type& Left, const Type& Right) const; 
 };  
 
// specialized transparent functor for operator== 
template <>  
struct equal_to<void>  
 {  
    template <class T, class U>  
    auto operator()(T&& Left, U&& Right) const 
      ->  decltype(std::forward<T>(Left) == std::forward<U>(Right));
 };  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Type`, `T`, `U`  
 지정되었거나 유추된 형식의 피연산자를 가져오는 `operator==`를 지원하는 모든 형식입니다.  
  
 `Left`  
 같음 연산의 왼쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `T`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.  
  
 `Right`  
 같음 연산의 오른쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `U`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.  
  
## <a name="return-value"></a>반환 값  
 `Left``==``Right`의 결과입니다. 특수화된 템플릿은 `operator==`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.  
  
## <a name="remarks"></a>설명  
 `Type` 형식 개체는 같은지 비교할 수 있어야 합니다. 이를 위해서는 개체 집합에서 정의된 `operator==`가 동등 관계의 수학적 속성을 충족해야 합니다. 기본 제공되는 숫자 및 포인터 형식은 모두 이 요구 사항을 충족합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// functional_equal_to.cpp  
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
   for ( i = 0 ; i <= 5 ; i+=2 )  
   {  
      v1.push_back( 2.0 *i );  
      v1.push_back( 2.0 * i + 1.0 );  
   }  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j+=2 )  
   {  
      v2.push_back( - 2.0 * j );  
      v2.push_back( 2.0 * j + 1.0 );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Testing for the element-wise equality between v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      equal_to<double>( ) );  
  
   cout << "The result of the element-wise equal_to comparison\n"  
      << "between v1 & v2 is: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
```Output  
The vector v1 = ( 0 1 4 5 8 9 )  
The vector v2 = ( -0 1 -4 5 -8 9 )  
The result of the element-wise equal_to comparison  
between v1 & v2 is: ( 1 1 0 1 0 1 )  
```


