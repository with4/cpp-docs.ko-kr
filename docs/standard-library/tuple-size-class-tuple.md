---
title: tuple_size 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c03c47502fdd9309b3d6553c3f46f9685d4eaa9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958268"
---
# <a name="tuplesize-class"></a>tuple_size 클래스

`tuple` 에 포함된 요소 수를 보관합니다.

## <a name="syntax"></a>구문

```cpp
// TEMPLATE STRUCT tuple_size
template <class Tuple>
   struct tuple_size;

// number of elements in array
template <class Elem, size_t Size>
   struct tuple_size<array<Elem, Size>>
      : integral_constant<size_t, Size>;

// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>>
      : integral_constant<size_t, 2>

// size of tuple
template <class... Types>
   struct tuple_size<tuple<Types...>>
      : integral_constant<size_t, sizeof...(Types)>;

// size of const tuple
template <class Tuple>
   struct tuple_size<const Tuple>;

// size of volatile tuple
template <class Tuple>
   struct tuple_size<volatile Tuple>;

// size of const volatile tuple
template <class Tuple>
   struct tuple_size<const volatile Tuple>;
```

### <a name="parameters"></a>매개 변수

*Tuple*  
튜플의 형식입니다.

*Elem*  
배열 요소의 형식입니다.

*Size*  
배열의 크기입니다.

*T1*  
쌍의 첫 번째 구성원 형식입니다.

*T2*  
쌍의 두 번째 구성원 형식입니다.

*유형*  
튜플 요소의 형식입니다.

## <a name="remarks"></a>설명

템플릿 클래스에 멤버가 `value` 는 정수 계열 상수 식 값은 튜플 형식의 범위로 *튜플*합니다.

배열에 대 한 템플릿 특수화에 멤버가 `value` 는 정수 계열 상수 식 값인 *크기*, 배열의 크기는 합니다.

쌍의 템플릿 특수화에는 해당 값이 2인 정수 계열 상수 식 `value` 구성원이 있습니다.

## <a name="example"></a>예

```cpp
#include <tuple>
#include <iostream>

using namespace std;

typedef tuple<int, double, int, double> MyTuple;
int main()
{
    MyTuple c0(0, 1.5, 2, 3.7);

    // display contents " 0 1 2 3"
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0);
    cout << " " << get<2>(c0);
    cout << " " << get<3>(c0) << endl;

    // display size " 4"
    cout << " " << tuple_size<MyTuple>::value << endl;
}
```

```Output
 0 1.5 2 3.7
```

## <a name="requirements"></a>요구 사항

**헤더:** \<튜플 > **헤더:** \<배열 > (배열 특수화 용) **헤더:** \<유틸리티 > (쌍 특수화 용)

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<tuple>](../standard-library/tuple.md)<br/>
[tuple](../standard-library/tuple-class.md)<br/>
[tuple_element 클래스](../standard-library/tuple-element-class-tuple.md)<br/>
