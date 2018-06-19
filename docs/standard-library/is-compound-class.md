---
title: is_compound 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_compound
dev_langs:
- C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d062912a441f16e9eb26415287fbbb574b829e9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843810"
---
# <a name="iscompound-class"></a>is_compound 클래스

지정된 형식이 기본 형식이 아닌지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 `false` 경우 유형의 `Ty` 형식 (즉, [is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > 보유 `true`), 그렇지 않으면 보유 `true`합니다. 따라서 `Ty`가 배열 형식이거나, 함수 형식이거나, `void`, 개체 또는 함수에 대한 포인터이거나, 비정적 클래스 멤버에 대한 참조, 클래스, 집합체, 열거형 또는 포인터이거나, 이들 중 하나의 *cv 한정* 형식이면 조건자는 `true`입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }

```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_class 클래스](../standard-library/is-class-class.md)<br/>
