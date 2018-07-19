---
title: is_constructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9e3f71a0d8647000f77863ecc9243b069f0521
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955833"
---
# <a name="isconstructible-class"></a>is_constructible 클래스

지정된 인수 형식을 사용할 경우 형식이 생성 가능한지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>매개 변수

*T* 쿼리할 형식입니다.

*Args* 의 생성자에서 일치 시킬 인수 형식 *T*합니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 의 인수 형식을 사용 하 여 형식이 되 *Args*, 그렇지 않으면 false입니다. 형식 *T* 생성 가능한 경우 변수 정의 `T t(std::declval<Args>()...);` 이 제대로 구성 합니다. 둘 다 *T* 와의 모든 형식 *Args* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
