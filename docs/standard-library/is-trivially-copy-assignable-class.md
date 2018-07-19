---
title: is_trivially_copy_assignable 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f7c4c748d7328f534aebfb2133c72635bbdc36f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953968"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable 클래스

형식에 Trivial 복사 할당 연산자가 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>매개 변수

*T* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 는 클래스에 trivial 복사 할당 연산자를, 그렇지 않으면 false입니다.

클래스에 대 한 할당 생성자는 *T* 암시적으로 제공 되는 클래스 경우 trivial *T* 에 클래스 가상 함수가 없는 *T* 에 없는 가상 기본을 클래스 클래스 형식의 모든 비정적 데이터 멤버에 trivial 대입 연산자 및 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 대입 연산자입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
