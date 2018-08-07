---
title: time_base 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e1111ede44edc36e5399d82b3c4e088b20cc1c9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957300"
---
# <a name="timebase-class"></a>time_base 클래스

이 클래스는 열거 형식에만 정의 되는 템플릿 클래스 time_get의 패싯에 대 한 기본 클래스로 사용 됩니다. `dateorder` 와이 형식의 여러 상수만 합니다.

## <a name="syntax"></a>구문

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```

## <a name="remarks"></a>설명

각 상수는 날짜의 구성 요소 순서를 지정하는 다른 방식을 지정합니다. 상수는 다음과 같습니다.

- `no_order` 특정 순서 없이 지정합니다.

- `dmy` 주문 날짜, 월, 2/12/1979와 같이 년을 지정 합니다.

- `mdy` 주문 월, 일, 1979 년 12 월 2와 같이 연도 지정 합니다.

- `ymd` 주문 연도, 월, 1979/12/2와 같이 날짜를 지정 합니다.

- `ydm` 주문 연도 차례로 일, 월, 년 12 월 1979: 2와 같이 지정합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
