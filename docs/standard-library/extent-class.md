---
title: extent 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb721b23f473c59051e72edc969e5de38f1c984
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="extent-class"></a>extent 클래스

배열 차원을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

`I` 쿼리할 바인딩되는 배열입니다.

## <a name="remarks"></a>설명

`Ty`가 `I` 이상의 차원을 가진 배열 형식인 경우 형식 쿼리에는 `I`에서 지정되는 차원의 요소 수가 포함됩니다. `Ty`가 배열 형식이 아니거나 순위가 `I`보다 작은 경우, 또는 `I`가 0이고 `Ty`가 "범위를 알 수 없는 배열 `U`" 형식인 경우 형식 쿼리는 0 값을 가집니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }

```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_all_extents 클래스](../standard-library/remove-all-extents-class.md)<br/>
[remove_extent 클래스](../standard-library/remove-extent-class.md)<br/>
