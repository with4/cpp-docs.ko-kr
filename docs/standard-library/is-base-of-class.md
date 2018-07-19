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
ms.openlocfilehash: 43f4aec5796db6a277b6bfb1edecdcd2e7f5c455
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954619"
---
# <a name="isbaseof-class"></a>is_base_of 클래스

한 형식이 다른 형식의 기본 형식인지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>매개 변수

*기본* 테스트 하기 위해 기본 클래스입니다.

*파생 된* 파생된 형식에 대 한 테스트입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *기본* 형식의 기본 클래스인 *파생*, 그렇지 않으면 false입니다.

## <a name="example"></a>예

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
