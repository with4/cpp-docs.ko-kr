---
title: is_arithmetic 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_arithmetic
dev_langs:
- C++
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 034279ceb67727e0a39bfaac76574ed03fe65560
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="isarithmetic-class"></a>is_arithmetic 클래스

산술 형식인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `Ty` 형식이 산술 형식, 즉 정수 형식이나 부동 소수점 형식 또는 이러한 형식 중 하나의 `cv-qualified` 형태인 경우 true이고 그렇지 않은 경우 false입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_arithmetic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha
        << std::is_arithmetic<trivial>::value << std::endl;
    std::cout << "is_arithmetic<int> == " << std::boolalpha
        << std::is_arithmetic<int>::value << std::endl;
    std::cout << "is_arithmetic<float> == " << std::boolalpha
        << std::is_arithmetic<float>::value << std::endl;

    return (0);
    }
```

```Output
is_arithmetic<trivial> == false
is_arithmetic<int> == true
is_arithmetic<float> == true
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_floating_point 클래스](../standard-library/is-floating-point-class.md)<br/>
[is_integral 클래스](../standard-library/is-integral-class.md)<br/>
