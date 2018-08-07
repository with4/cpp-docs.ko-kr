---
title: is_trivially_copy_constructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 410566c623595cc941ab6e6ad21dd95bd70fe516
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963669"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible 클래스

형식에 trivial 복사 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>매개 변수

*T* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 는 클래스에 trivial 복사 생성자가 있는 그렇지 않으면 false입니다.

클래스에 대 한 복사 생성자 *T* 암시적으로 선언 된 클래스 경우 trivial *T* 없습니다 가상 함수나 가상 기본을 클래스의 모든 직접 기본에 *T* 가 trivial 복사 생성자가 클래스 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 복사 생성자 및 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 복사 생성자입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
