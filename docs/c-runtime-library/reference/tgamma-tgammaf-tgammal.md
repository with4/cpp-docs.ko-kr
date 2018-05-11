---
title: tgamma, tgammaf, tgammal | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs:
- C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7861b297646f4a704134e0d874fad8c924a7ebc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

지정된 값의 감마 함수를 결정합니다.

## <a name="syntax"></a>구문

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

```

### <a name="parameters"></a>매개 변수

*x*<br/>
감마를 찾을 값입니다.

## <a name="return-value"></a>반환 값

성공 하면 반환의 감마 *x*합니다.

범위 오류는 경우에 발생할 수 있습니다는 양이 *x* 이 너무 크거나 너무 작은 데이터 형식에 대 한 합니다. 경우에 발생할 수 있습니다는 도메인 오류 또는 범위 오류 *x* < = 0.

|문제|반환|
|-----------|------------|
|x = ±0|±INFINITY|
|x = 음의 정수|NaN|
|x =-무한대|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|도메인 오류|NaN|
|극 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|
|언더플로 범위 오류|반올림 후의 올바른 값|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **tgamma** 사용 하 고 반환 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **tgamma** 항상 사용 하 고 반환 된 **double**합니다.

X가 자연수인 경우 이 함수는 (x-1)의 계승을 반환합니다.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**, **tgammal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
