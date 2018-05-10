---
title: logical_not 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::logical_not
dev_langs:
- C++
helpviewer_keywords:
- logical_not class
- logical_not struct
ms.assetid: 892db678-31da-4540-974b-17b05efc0849
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0d654c526e5c856431d69c045c5018d77a6fed3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="logicalnot-struct"></a>logical_not 구조체

인수에 대해 논리적 NOT 연산(`operator!`)을 수행하는 미리정의된 함수 개체입니다.

## <a name="syntax"></a>구문

```
template <class Type = void>
struct logical_not : public unary_function<Type, bool>
{
    bool operator()(const Type& Left) const;
};

// specialized transparent functor for operator!
template <>
struct logical_not<void>
{
  template <class Type>
  auto operator()(Type&& Left) const`
     -> decltype(!std::forward<Type>(Left));
 };
```

### <a name="parameters"></a>매개 변수

`Type` 지 원하는 모든 형식은 `operator!` 지정 되었거나 유추 된 형식의 피연산자를 사용 합니다.

`Left` 피연산자의 논리 not 연산을 합니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `Type`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

## <a name="return-value"></a>반환 값

`!Left`의 결과입니다. 특수화된 템플릿은 `operator!`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

## <a name="example"></a>예제

```cpp
// functional_logical_not.cpp
// compile with: /EHsc
#include <deque>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   deque<bool> d1, d2 ( 7 );
   deque<bool>::iterator iter1, iter2;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
   {
      d1.push_back((bool)((i % 2) != 0));
   }

   cout << boolalpha;    // boolalpha I/O flag on

   cout << "Original deque:\n d1 = ( " ;
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )
      cout << *iter1 << " ";
   cout << ")" << endl;

   // To flip all the truth values of the elements,
   // use the logical_not function object
   transform( d1.begin( ), d1.end( ), d2.begin( ),logical_not<bool>( ) );
   cout << "The deque with its values negated is:\n d2 = ( " ;
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )
      cout << *iter2 << " ";
   cout << ")" << endl;
}
/* Output:
Original deque:
 d1 = ( false true false true false true false )
The deque with its values negated is:
 d2 = ( true false true false true false true )
 */
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
