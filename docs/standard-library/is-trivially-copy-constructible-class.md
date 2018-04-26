---
title: is_trivially_copy_constructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73928574f2c96da952b7f18908c6b7a175549981
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible 클래스

형식에 trivial 복사 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>매개 변수

`T` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `T` 형식이 trivial 복사 생성자가 있는 클래스인 경우 true이고, 그렇지 않은 경우 false입니다.

`T` 클래스에 대한 복사 생성자는 암시적으로 선언되고, `T` 클래스에 가상 함수나 가상 기본이 없고, `T` 클래스의 모든 직접 기본에 trivial 복사 생성자가 있고, 클래스 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 복사 생성자가 있으며, 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 복사 생성자가 있는 경우 trivial입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
