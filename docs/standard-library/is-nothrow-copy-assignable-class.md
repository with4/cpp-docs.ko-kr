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
ms.openlocfilehash: e540d6fe4c00772af01b187d24efae18fd62357f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957560"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable 클래스

throw되지 않는 것으로 컴파일러에 알려진 복사 대입 연산자가 형식에 있는지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>매개 변수

*T* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 참조 가능한 형식에 대 한 마찬가지 *T* 여기서 `is_nothrow_assignable<T&, const T&>` 보유 true이 고 그렇지 않으면 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable 클래스](../standard-library/is-nothrow-assignable-class.md)<br/>
