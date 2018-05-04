---
title: exp, expf, 탐색 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9569eee475a80fc5c08c2ec1d099cf627c7b5fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="exp-expf-expl"></a>exp, expf, expl

지수를 계산합니다.

## <a name="syntax"></a>구문

```C
double exp(
   double x
);
float exp(
   float x
);  // C++ only
long double exp(
   long double x
);  // C++ only
float expf(
   float x
);
long double expl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값을 exponentiate 자연 로그 자료 *e* 여 합니다.

## <a name="return-value"></a>반환 값

**exp** 부동 소수점 매개 변수를 지 수 값을 반환 하는 함수 *x*성공 하는 경우, 합니다. 즉, 결과 *e*<sup>*x*</sup>여기서 *e* 는 자연 로그의 기본 인터페이스입니다. 오버플로 함수 반환 값 (무한대) INF 및 언더플로, **exp** 0을 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± Quiet NaN, 비활성화|없음|_DOMAIN|
|± 무한대|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

**exp** 함수에 스트리밍 SIMD 확장명 2 (SSE2)를 사용 하는 구현 합니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

## <a name="remarks"></a>설명

C + + 오버 로드의 오버 로드를 호출할 수 있도록 허용 **exp** 사용 하는 **float** 또는 **long double** 인수입니다. C 프로그램에서 **exp** 항상 사용 하 고 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 C 헤더|필수 C++ 헤더|
|--------------|---------------------|---|
|**exp**, **expf**, **탐색**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_exp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.302585093, y;

   y = exp( x );
   printf( "exp( %f ) = %f\n", x, y );
}
```

```Output
exp( 2.302585 ) = 10.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
