---
title: money_base 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3195d2c988abcfb2d62acb4ece957c8c5156bbd7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965690"
---
# <a name="moneybase-class"></a>money_base 클래스

이 클래스는 템플릿 클래스 [moneypunct](../standard-library/moneypunct-class.md)의 모든 특수화에 공통적인 열거형과 구조체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>설명

열거형 `part` 구조체 패턴에서 배열 필드의 요소에 사용 가능한 값에 설명 합니다. 값 `part` 됩니다.

- `none` 0 개 이상의 공백과 일치 시키거나 아무 항목도 생성 됩니다.

- `sign` 검색 하거나 양수 또는 음수 기호를 생성 합니다.

- `space` 0 개 이상의 공백과 일치 시키거나 공백을 생성 합니다.

- `symbol` -일치 시키거나 통화 기호를 생성 합니다.

- `value` -일치 시키거나 통화 값을 생성 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
