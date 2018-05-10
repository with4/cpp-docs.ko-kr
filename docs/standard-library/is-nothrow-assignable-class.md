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
ms.openlocfilehash: 0f11e1ce8b016ab8c6e8af04e351e80307b2189e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable 클래스

`From` 형식의 값을 `To` 형식에 할당할 수 있는지 여부와 할당이 throw되지 않는 것으로 알려져 있는지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>매개 변수

할당을 받는 개체의 형식입니다.

값을 제공 하는 개체의 형식입니다.

## <a name="remarks"></a>설명

`declval<To>() = declval<From>()` 식은 올바른 형식이어야 하며 throw되지 않는 것으로 컴파일러에 알려져 있어야 합니다. `From`과 `To`는 둘 다 완전한 형식이거나, `void`이거나, 범위를 알 수 없는 배열이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
