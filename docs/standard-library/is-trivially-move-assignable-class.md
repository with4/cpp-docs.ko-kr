---
title: is_trivially_move_assignable 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee7fb3e92064ebced6390c0eaf81fc68552381ca
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable 클래스

형식에 trivial 이동 할당 연산자가 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 형식 `Ty`가 trivial 이동 할당 연산자를 가진 클래스인 경우 true이고 그렇지 않은 경우 false입니다.

클래스 `Ty`에 대한 이동 할당 연산자는 다음과 같은 경우 trivial입니다.

암시적으로 제공된 경우

클래스 `Ty`에 가상 함수가 없는 경우

클래스 `Ty`에 가상 기본이 없는 경우

클래스 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 이동 할당 연산자가 있는 경우

클래스 형식 배열의 모든 비정적 데이터 멤버의 클래스에 trivial 이동 할당 연산자가 있는 경우

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
