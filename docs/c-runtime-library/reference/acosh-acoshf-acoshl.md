---
title: acosh, acoshf, acoshl | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- acoshf
- acosh
- acoshl
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
- acosh
- acoshf
- acoshl
- math/acosh
- math/acoshf
- math/acoshl
dev_langs:
- C++
helpviewer_keywords:
- acoshf function
- acosh function
- acoshl function
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 546006fcf1c559317b4afff424976db8109442e7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404754"
---
# <a name="acosh-acoshf-acoshl"></a>acosh, acoshf, acoshl

역쌍곡 코사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double acosh( double x );
float acoshf( float x );
long double acoshl( long double x );
```

```cpp
float acosh( float x );  // C++ only
long double acosh( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*  
부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

합니다 **acosh** 의 역 쌍 곡 코사인 (쌍곡선 아크코사인)를 반환 하는 함수 *x*합니다. 도메인을 통해 이러한 함수는 유효한 *x* ≥ 1입니다. 경우 *x* 1 보다 작으면 `errno` 로 설정 된 `EDOM` 결과 quiet NaN입니다. 하는 경우 *x* 는 quiet NaN, 무한 또는 무한대 이면 동일한 값이 반환 됩니다.

|입력|SEH 예외|`_matherr` 예외|
|-----------|-------------------|--------------------------|
|± QNAN, IND, INF|없음|없음|
|*x* < 1|없음|없음|

## <a name="remarks"></a>설명

C + +를 사용 하는 경우의 오버 로드를 호출할 수 있습니다 **acosh** 및 반환 하는 **float** 하거나 **긴** **double** 값입니다. C 프로그램에서 **acosh** 항상 받아서 반환 **double**합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**acosh**하십시오 **acoshf**, **acoshl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예

```C
// crt_acosh.c
// Compile by using: cl /W4 crt_acosh.c
// This program displays the hyperbolic cosine of pi / 4
// and the arc hyperbolic cosine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = cosh( pi / 4 );
   y = acosh( x );
   printf( "cosh( %f ) = %f\n", pi/4, x );
   printf( "acosh( %f ) = %f\n", x, y );
}
```

```Output
cosh( 0.785398 ) = 1.324609
acosh( 1.324609 ) = 0.785398
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)  
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)  
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)  
[cosh, coshf, coshl](cosh-coshf-coshl.md)  
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)  
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)  