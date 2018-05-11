---
title: is_trivial 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivial
dev_langs:
- C++
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b30b634a84dc47d839e1288bc34437b440e914c3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="istrivial-class"></a>is_trivial 클래스

형식이 trivial 형식인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>매개 변수

`T` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `T` 형식이 trivial 형식인 경우 true이고 그렇지 않은 경우 false입니다. Trivial 형식은 스칼라 형식, 일반적으로 복사할 수 클래스 형식, 이러한 형식의 배열 및 이러한 형식의 cv 한정 버전입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
