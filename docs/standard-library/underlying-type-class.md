---
title: underlying_type 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b3f796d5039900b591c219c840d1aef94d23e8f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957583"
---
# <a name="underlyingtype-class"></a>underlying_type 클래스

열거형 형식에 대한 내부 정수 계열 형식을 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>매개 변수

*T*  
 수정할 형식입니다.

## <a name="remarks"></a>설명

`type` 템플릿 클래스의 멤버 typedef의 기본 정수 계열 형식 이름을 *T*면 *T* 가 열거형 형식이 없는 멤버 typedef 않으면 `type`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
