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
ms.openlocfilehash: 2e6df4526eea3b0b8b4e91fa4f3e6a89cdd8adb7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964312"
---
# <a name="extent-class"></a>extent 클래스

배열 차원을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>매개 변수

*Ty* 쿼리할 형식입니다.

*I* 쿼리 바인딩되는 배열입니다.

## <a name="remarks"></a>설명

경우 *Ty* 이상이 있는 배열 형식입니다 *합니까* 차원 형식 쿼리는 지정 된 차원의 요소 수가 보유 *I*합니다. 경우 *Ty* 배열 형식이 아니거나 순위가 보다 작거나 *있습니까*, 이거나 *합니까* 0 및 *Ty* 형식입니다 "의 경계를 알 수 없는 배열 `U` "에 형식 쿼리는 0 값을 보유 합니다.

## <a name="example"></a>예

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
