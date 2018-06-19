---
title: is_final 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_final
dev_langs:
- C++
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b3d2c37b73d79619aeb16e7b1b81ad71819b09b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844057"
---
# <a name="isfinal-class"></a>is_final 클래스

형식이 `final`로 표시된 클래스 형식인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>매개 변수

`T` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `T` 형식이 `final`로 표시된 클래스 형식인 경우 true이고, 그렇지 않으면 false입니다. `T`가 클래스 형식일 경우 완전한 형식이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[final 지정자](../cpp/final-specifier.md)<br/>
