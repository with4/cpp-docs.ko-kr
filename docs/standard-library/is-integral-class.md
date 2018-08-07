---
title: is_integral 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_integral
dev_langs:
- C++
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58f3245e430ba1c74ea88f6262f14a4d38c1ca2c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954033"
---
# <a name="isintegral-class"></a>is_integral 클래스

형식이 정수 계열인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>매개 변수

*Ty* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 정수 형식 중 하나인 또는 `cv-qualified` 정수 형식, 그렇지 않으면 false 중 하나의 형식을 합니다.

정수 계열 형식 중 하나인 **bool**를 **char**를 **unsigned char**를 **char 서명**를 **wchar_t**, **짧은**를 **unsigned short**를 **int**를 **부호 없는 int**를 **긴**, 및 **부호 없는 long**합니다. 또한 제공 하는 컴파일러를 사용 하 여 정수 계열 형식 중 하나일 수 있습니다 **long long**, **부호 없는 long long**하십시오 **__int64**, 및 **unsigned __int64**.

## <a name="example"></a>예

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }

```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_enum 클래스](../standard-library/is-enum-class.md)<br/>
[is_floating_point 클래스](../standard-library/is-floating-point-class.md)<br/>
