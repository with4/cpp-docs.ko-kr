---
title: is_move_constructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 979e726e1374ac37844472d9e2f9ae8ddd5ddf4d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965804"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible 클래스

형식에 이동 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>매개 변수

*T* 평가할 형식

## <a name="remarks"></a>설명

형식 경우 true로 계산 되는 형식 조건자 *T* 이동 작업을 사용 하 여 생성할 수 있습니다. 이 조건자는 `is_constructible<T, T&&>`과 같습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
