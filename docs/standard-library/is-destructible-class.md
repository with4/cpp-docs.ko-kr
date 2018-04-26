---
title: is_destructible 클래스 | Microsoft 문서
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
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 887946156084d962debf569fc4f23f45dea18293
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="isdestructible-class"></a>is_destructible 클래스

형식이 소멸 가능한지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>매개 변수

`T` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `T` 형식이 소멸 가능한 형식인 경우 true이고 그렇지 않은 경우 false입니다. 소멸 가능한 형식은 참조 형식, 개체 형식 및 `U` 와 같은 일부 `remove_all_extents_t<T>` 형식의 경우 확인되지 않은 피연산자 `std::declval<U&>.~U()` 가 올바르게 구성되는 경우의 형식입니다. 불완전한 형식, `void`, 및 함수 형식을 비롯한 기타 형식은 소멸 가능한 형식이 아닙니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
