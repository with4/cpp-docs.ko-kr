---
title: iterator_traits 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator_traits
dev_langs:
- C++
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57387af452ff4a127eec6b669cec6e02863b8fd3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="iteratortraits-struct"></a>iterator_traits 구조체

반복기에 포함되어야 하는 모든 중요한 형식 정의를 지정하는 데 사용되는 템플릿 도우미 구조체입니다.

## <a name="syntax"></a>구문

```cpp
struct iterator_traits {
   typedef typename Iterator::iterator_category iterator_category;
   typedef typename Iterator::value_type value_type;
   typedef typename Iterator::difference_type difference_type;
   typedef difference_type distance_type;
   typedef typename Iterator::pointer pointer;
   typedef typename Iterator::reference reference;
   };
```

## <a name="remarks"></a>설명

이 템플릿 구조체는 멤버 형식을 정의합니다.

- **iterator_category**: **Iterator::iterator_category**의 동의어입니다.

- `value_type`: **Iterator::value_type**의 동의어입니다.

- `difference_type`: **Iterator::difference_type**의 동의어입니다.

- `distance_type`: **Iterator::difference_type.** 의 동의어입니다.

- **pointer**: **Iterator::pointer**의 동의어입니다.

- **reference**: **Iterator::reference**의 동의어입니다.

부분 특수화는 **Type \*** 또는 const **Type \*** 형식의 개체 포인터와 연결된 중요한 형식을 결정합니다.

이 구현에서는 부분 특수화를 사용하지 않는 여러 가지 템플릿 함수를 사용할 수도 있습니다.

```cpp
template <class Category, class Type, class Diff>
C _Iter_cat(const iterator<Category, Ty, Diff>&);

template <class Ty>
random_access_iterator_tag _Iter_cat(const Ty *);

template <class Category, class Ty, class Diff>
Ty *val_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
Ty *val_type(const Ty *);

template <class Category, class Ty, class Diff>
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
ptrdiff_t *_Dist_type(const Ty *);
```

이러한 함수는 여러 가지 동일한 형식을 보다 간접적으로 결정합니다. 함수 호출에서 인수로 이러한 함수를 사용합니다. 또한 호출된 함수에 유용한 템플릿 클래스 매개 변수를 제공하려는 용도로만 사용됩니다.

## <a name="example"></a>예제

```cpp
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
\* Output:
struct std::random_access_iterator_tag
a a a a a a a a a a
struct std::bidirectional_iterator_tag
0 0 0 0 0 0 0 0 0 0
*\
```

## <a name="requirements"></a>요구 사항

**헤더:** \<iterator>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<iterator>](../standard-library/iterator.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
