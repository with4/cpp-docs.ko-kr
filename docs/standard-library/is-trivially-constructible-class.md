---
title: is_trivially_constructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 757a5eb526bc8d4294a64cbdc9645e72285162ce
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible 클래스

지정된 인수 형식을 사용할 경우 형식이 일반적으로 생성 가능한지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>매개 변수

`T` 형식이 쿼리입니다.

`Args` 생성자에서 일치 하도록 인수 형식을 `T`합니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `T` 형식이 `Args`의 인수 형식을 사용하여 일반적으로 생성 가능한 경우 true이고, 그렇지 않으면 false입니다. 변수 정의 `T t(std::declval<Args>()...);`의 형식이 올바르고 특수한 작업을 호출하지 않는 것으로 알려진 경우 `T` 형식은 일반적으로 생성 가능합니다. `T`와 `Args`의 모든 형식은 둘 다 완전한 형식이거나, `void`이거나, 범위를 알 수 없는 배열이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
