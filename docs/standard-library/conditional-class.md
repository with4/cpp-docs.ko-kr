---
title: conditional 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57e01cbfd7cb291ff7d2651e3244b74ae96adbea
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962402"
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

*B* 선택한 형식을 결정 하는 값입니다.

*T1* B가 true 인 경우의 형식 결과입니다.

*T2* B가 false 인 경우의 형식 결과입니다.

## <a name="remarks"></a>설명

템플릿 멤버 typedef `conditional<B, T1, T2>::type` 로 평가 *T1* 때 *B* 로 **true**를 계산 하 고 *T2* 때  *B* 로 평가 **false**합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
