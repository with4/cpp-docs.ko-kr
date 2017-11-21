---
title: "negate 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::negate
dev_langs: C++
helpviewer_keywords:
- negate struct
- negate class
ms.assetid: 8a372686-786e-4262-b37c-ca13dc11e62f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0eab26299a40496cbcd8e59a79eb48643fbcdf3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="negate-struct"></a>negate 구조체
인수에 대해 산술 부정 연산(단항 `operator-`)을 수행하는 미리 정의된 함수 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Type = void>
struct negate : public unary_function<Type, Type>  
{
    Type operator()(const Type& Left) const;
};

// specialized transparent functor for unary operator-
template <>
struct negate<void>  
{
  template <class Type>
  auto operator()(Type&& Left) const`
    -> decltype(-std::forward<Type>(Left));
 };
```  
  
#### <a name="parameters"></a>매개 변수  
 `Type`  
 지정되었거나 유추된 형식의 피연산자를 사용하는 `operator-`를 지원하는 모든 형식입니다.  
  
 `Left`  
 부정할 피연산자입니다. 특수화된 템플릿은 유추 형식 `Type`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.  
  
## <a name="return-value"></a>반환 값  
 `-Left.`의 결과. 특수화된 템플릿은 단항 `operator-`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// functional_negate.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <int> v1, v2 ( 8 );  
   vector <int>::iterator Iter1, Iter2;  
  
   int i;  
   for ( i = -2 ; i <= 5 ; i++ )  
   {  
      v1.push_back( 5 * i );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise negatives of the vector v1  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), negate<int>( ) );  
  
   cout << "The negated elements of the vector = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
}  
\* Output:   
The vector v1 = ( -10 -5 0 5 10 15 20 25 )  
The negated elements of the vector = ( 10 5 0 -5 -10 -15 -20 -25 )  
*\  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<functional>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)



