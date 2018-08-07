---
title: is_nothrow_assignable 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 424fcf5b960182326dc1192d8d60f168ead59d98
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965417"
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable 클래스

값이 있는지 여부를 테스트 *에서* 형식에 할당할 수 있습니다 *하려면* 유형 및 할당은 throw 되지 않는 합니다.

## <a name="syntax"></a>구문

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>매개 변수

 할당을 받는 개체의 형식입니다.

 값을 제공 하는 개체의 형식입니다.

## <a name="remarks"></a>설명

`declval<To>() = declval<From>()` 식은 올바른 형식이어야 하며 throw되지 않는 것으로 컴파일러에 알려져 있어야 합니다. 둘 다 *에서* 하 고 *에* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
