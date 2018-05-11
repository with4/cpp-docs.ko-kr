---
title: lgamma, lgammaf, lgammal | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
dev_langs:
- C++
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fb668e1c24d3f24331e0892002530192afdaeb6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

지정된 값에 대한 감마 함수 절대 값의 자연 로그를 확인합니다.

## <a name="syntax"></a>구문

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
계산할 값입니다.

## <a name="return-value"></a>반환 값

성공 하면의 감마 함수의 절대 값의 자연 로그를 반환 *x*합니다.

|문제|반환|
|-----------|------------|
|*x* = NaN|NaN|
|*x* ±0 =|+INFINITY|
|*x*= 음의 정수|+INFINITY|
|±INFINITY|+INFINITY|
|극 오류|+HUGE_VAL, +HUGE_VALF 또는 +HUGE_VALL|
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **lgamma** 사용 하 고 반환 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **lgamma** 항상 사용 하 고 반환 된 **double**합니다.

X 유리수 이면이 함수는 (x-1)의 계승값 로그를 반환 합니다.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
