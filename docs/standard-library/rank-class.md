---
title: rank 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::rank
dev_langs:
- C++
helpviewer_keywords:
- rank class
- rank
ms.assetid: bc9f1b8f-800f-46ca-b6f4-d8579ed5406a
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae0bc9fd59b4c7de147ccdd94581a54131efe8b6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="rank-class"></a>rank 클래스

배열 차원 수를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct rank;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 쿼리는 배열 형식 `Ty`의 차원 수 값이거나, `Ty`가 배열 형식이 아니면 0입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__rank.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "rank<int> == "
        << std::rank<int>::value << std::endl;
    std::cout << "rank<int[5]> == "
        << std::rank<int[5]>::value << std::endl;
    std::cout << "rank<int[5][10]> == "
        << std::rank<int[5][10]>::value << std::endl;

    return (0);
    }

```

```Output
rank<int> == 0
rank<int[5]> == 1
rank<int[5][10]> == 2
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[extent 클래스](../standard-library/extent-class.md)<br/>
