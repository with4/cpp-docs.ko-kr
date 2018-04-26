---
title: money_base 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a33e60ff54c7ec03ef806f5104513c9838449190
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
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

열거형 **part**는 구조체 패턴에서 배열 필드의 요소에 사용 가능한 값을 설명합니다. **part**의 값은 다음과 같습니다.

- **none** - 0개 이상의 공백과 일치시키거나 아무 항목도 생성하지 않습니다.

- **sign** - 양수/음수 부호와 일치시키거나 해당 부호를 생성합니다.

- **space** - 0개 이상의 공백과 일치시키거나 공백을 생성합니다.

- **symbol** - 통화 기호와 일치시키거나 통화 기호를 생성합니다.

- **value** - 통화 값과 일치시키거나 통화 값을 생성합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
