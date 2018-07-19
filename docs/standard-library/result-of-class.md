---
title: result_of 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b385d822c2f58d26938b3300207a790dc1193060
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953051"
---
# <a name="resultof-class"></a>result_of 클래스

지정된 인수 유형을 사용하는 호출 가능 형식의 반환 형식을 결정합니다.

## <a name="syntax"></a>구문

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>매개 변수

*Fn* 쿼리할 호출 가능 형식입니다.

*ArgTypes* 쿼리할 호출 가능 형식 인수 목록의 형식입니다.

## <a name="remarks"></a>설명

이 템플릿을 사용 하 여의 결과 형식은 컴파일 타임에 결정 `Fn`(`ArgTypes`), 여기서 *Fn* 에서형식인수목록을사용하여호출할호출가능형식에대한참조,함수에대한참조또는호출가능형식 *ArgTypes*합니다. 템플릿 클래스의 `type` 구성원은 평가되지 않은 식 `std::invoke(declval<Fn>(), declval<ArgTypes>()...)`가 올바른 형식인 경우 `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`의 결과 형식 이름을 지정합니다. 그렇지 않은 경우 템플릿 클래스에는 구성원 `type`이 없습니다. 형식 *Fn* 및 매개 변수 팩에는 모든 형식이 *ArgTypes* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
