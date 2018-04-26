---
title: is_nothrow_copy_constructible 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_constructible
ms.assetid: f13a0bea-63b1-492a-9a45-d445df35c282
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7d08c736bce54c6f5847a74a01b44c781f66d9c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="isnothrowcopyconstructible-class"></a>is_nothrow_copy_constructible 클래스

형식에 **nothrow** 복사 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_nothrow_copy_constructible;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 `Ty` 형식에 nothrow 복사 생성자가 있는 경우 true이고 그렇지 않은 경우 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
