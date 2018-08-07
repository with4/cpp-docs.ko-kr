---
title: is_destructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5b2c9237c7f17217d28e489edef4ab65863b54b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964117"
---
# <a name="isdestructible-class"></a>is_destructible 클래스

형식이 소멸 가능한지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>매개 변수

*T* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 형식이 소멸 가능한, 그렇지 않으면 false입니다. 소멸 가능한 형식은 참조 형식, 개체 형식 및 `U` 와 같은 일부 `remove_all_extents_t<T>` 형식의 경우 확인되지 않은 피연산자 `std::declval<U&>.~U()` 가 올바르게 구성되는 경우의 형식입니다. 다른 형식, 불완전 한 형식 포함 **void**, 함수 형식, 소멸 가능한 형식이 아닌 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
