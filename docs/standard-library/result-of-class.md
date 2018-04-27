---
title: result_of 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e05b8eb4352ca1556f8266dfc73247222583d4a8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
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

`Fn` 호출 가능 형식이 쿼리입니다.

`ArgTypes` 쿼리를 호출 가능 형식에는 인수 목록의 형식입니다.

## <a name="remarks"></a>설명

이 템플릿을 사용하여 컴파일 시간에 결과 형식 `Fn`(`ArgTypes`)을 결정합니다. 여기서 `Fn`은 `ArgTypes` 내 형식의 인수 목록을 사용하여 호출되는 호출 가능 형식, 함수에 대한 참조 또는 호출 가능 형식에 대한 참조입니다. 템플릿 클래스의 `type` 구성원은 평가되지 않은 식 `std::invoke(declval<Fn>(), declval<ArgTypes>()...)`가 올바른 형식인 경우 `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`의 결과 형식 이름을 지정합니다. 그렇지 않은 경우 템플릿 클래스에는 구성원 `type`이 없습니다. 형식 `Fn` 및 매개 변수 팩 `ArgTypes`의 모든 형식은 완전한 형식, `void` 또는 경계를 알 수 없는 배열이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
