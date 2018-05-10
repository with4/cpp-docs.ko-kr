---
title: is_base_of 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_base_of
dev_langs:
- C++
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed73314d5cef6849c84a8e1019e1fd2d6c8ead86
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="isbaseof-class"></a>is_base_of 클래스

한 형식이 다른 형식의 기본 형식인지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>매개 변수

`Base` 테스트 하기 위해 기본 클래스입니다.

`Derived` 파생된 형식에 대 한 테스트입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `Base` 형식이 `Derived` 형식의 기본 클래스인 경우 true이고, 그렇지 않은 경우 false입니다.

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_convertible 클래스](../standard-library/is-convertible-class.md)<br/>
