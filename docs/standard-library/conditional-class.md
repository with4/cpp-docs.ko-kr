---
title: conditional 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40d7e873ce7ae5814423d4b5e3899ef8bbb46fa7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="conditional-class"></a>conditional 클래스

지정된 조건에 따라 두 가지 형식 중 하나를 선택합니다.

## <a name="syntax"></a>구문

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>매개 변수

`B` 선택된 된 형식을 확인 하는 값입니다.

`T1` B가 true 인 경우의 형식 결과입니다.

`T2` B가 false 인 경우 형식 결과입니다.

## <a name="remarks"></a>설명

템플릿 멤버 typedef `conditional<B, T1, T2>::type` 는 `T1` 가 `B` 로 확인될 때 `true`으로 확인되고, `T2` 가 `B` 로 확인될 때 `false`로 확인됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
