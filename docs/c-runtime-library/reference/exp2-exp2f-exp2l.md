---
title: exp2, exp2f, exp2l | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- exp2
- exp2f
- exp2l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs:
- C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aea847d367200635c8fecbd694f8a50be859b3ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396724"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

지정된 된 값으로 2를 계산 합니다.

## <a name="syntax"></a>구문

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
지수 값입니다.

## <a name="return-value"></a>반환 값

성공 하면의 밑이 2 인 지 수를 반환 *x*, 2, 즉<sup>x</sup>합니다. 그렇지 않으면 다음 값 중 하나 반환 합니다.

|문제|반환|
|-----------|------------|
|*x* ±0 =|1|
|*x* =-무한대|+0|
|*x* = + INFINITY|+INFINITY|
|*x* = NaN|NaN|
|오버플로 범위 오류|+HUGE_VAL, +HUGE_VALF 또는 +HUGE_VALL|
|언더플로 범위 오류|올바른 결과 반올림 한 후|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **exp2** 사용 하 고 반환 **float** 및 **long double** 형식입니다. C 프로그램에서 **exp2** 항상 사용 하 고 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**exp**, **expf**, **탐색**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
