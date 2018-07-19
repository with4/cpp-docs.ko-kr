---
title: remainder, remainderf, remainderl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f277292f413e09b9c41a87cd82e438e0e1e883a8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406669"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

두 부동 소수점 값 몫의 나머지를 가장 가까운 적분 값으로 반올림하여 계산합니다.

## <a name="syntax"></a>구문

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
분자입니다.

*y*<br/>
분모입니다.

## <a name="return-value"></a>반환 값

부동 소수점 나머지 *x* / *y*합니다. 하는 경우의 값 *y* 이 0.0 인 경우 **나머지** 자동 NaN을 반환 합니다. 자동 NaN으로 표현에 대 한 내용은 **printf** 제품군, 참조 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)합니다.

## <a name="remarks"></a>설명

**나머지** 함수는 부동 소수점 나머지 계산 *r* 의 *x* / *y* 되도록 *x*   =  *n* * *y* + *r*여기서 *n*되 고 값을 가장 가까운 정수 *x* / *y* 및 *n*짝수 때마다 &#124; *n*  -  *x* / *y* &#124; = 1/2입니다. 때 *r* = 0, *r* 와 동일한 기호가 *x*합니다.

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **나머지** 사용 하 고 반환 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **나머지** 항상는 두 가지 **double** 인수 및 반환은 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------|-|
|**나머지**, **remainderf**, **remainderl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
