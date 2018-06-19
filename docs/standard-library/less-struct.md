---
title: less 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::less
dev_langs:
- C++
helpviewer_keywords:
- less struct
- less function
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fac4528c976e99a77ceec8bc170323846a0e3a28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858918"
---
# <a name="less-struct"></a>less 구조체

인수에서 작음 연산(`operator<`)을 수행하는 이진 조건자입니다.

## <a name="syntax"></a>구문

```cpp
template <class Type = void>
struct less : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<
template <>
struct less<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) <std::forward<U>(Right));
};
```

### <a name="parameters"></a>매개 변수

`Type``T`, `U` 지 원하는 모든 형식은 `operator<` 지정 되었거나 유추 된 형식의 피연산자를 사용 하는 합니다.

`Left` 작음의 왼쪽된 피연산자-작업 보다 합니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `T`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

`Right` 작음의 오른쪽 피연산자-작업 보다 합니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `U`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

## <a name="return-value"></a>반환 값

`Left < Right`의 결과입니다. 특수화된 템플릿은 `operator<`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

## <a name="remarks"></a>설명

이진 조건자 `less`< `Type`>은 이 형식이 표준 수학 요구 사항을 충족하는 경우에만 동등 클래스에 `Type` 형식 요소 값 집합의 엄격하고 약한 순서를 제공하여 그렇게 정렬되도록 합니다. 고유한 값의 모든 요소가 서로를 기준으로 정렬된다는 점에서 모든 포인터 형식에 대한 특수화는 요소의 전체 순서 지정을 생성합니다.

## <a name="example"></a>예제

```cpp
// functional_less.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

struct MyStruct {
   MyStruct(int i) : m_i(i){}

   bool operator < (const MyStruct & rhs) const {
      return m_i < rhs.m_i;
   }

   int m_i;
};

int main() {
   using namespace std;
   vector <MyStruct> v1;
   vector <MyStruct>::iterator Iter1;
   vector <MyStruct>::reverse_iterator rIter1;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
       v1.push_back( MyStruct(rand()));

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )
cout << Iter1->m_i << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   sort( v1.begin( ), v1.end( ), less<MyStruct>());

   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )
cout << Iter1->m_i << " ";
   cout << ")" << endl;
 }
```

## <a name="output"></a>출력

```Output
Original vector v1 = (41 18467 6334 26500 19169 15724 11478)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500)
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
