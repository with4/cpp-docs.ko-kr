---
title: is_nothrow_copy_assignable 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c5c5bdc1e944483071f0f1dcd53c3bc93eb6ed3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable 클래스

throw되지 않는 것으로 컴파일러에 알려진 복사 대입 연산자가 형식에 있는지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>매개 변수

`T` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `is_nothrow_assignable<T&, const T&>`가 true인 참조 가능한 형식 `T`에 대해서는 true이고, 그렇지 않으면 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable 클래스](../standard-library/is-nothrow-assignable-class.md)<br/>
