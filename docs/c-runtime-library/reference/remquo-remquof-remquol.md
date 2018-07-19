---
title: remquo, remquof, remquol | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- remquof
- remquo
- remquol
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
- remquof
- remquol
- remquo
dev_langs:
- C++
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d2bcb774d7ebe7e71c3877af326177bbf8d7160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407004"
---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol

두 정수값의 나머지를 계산하고, 몫의 대략적인 크기와 부호가 포함된 정수값을 매개 변수에 지정된 위치에 저장합니다.

## <a name="syntax"></a>구문

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
```

```cpp
float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*번호*<br/>
분자입니다.

*denom*<br/>
분모입니다.

*현재*<br/>
몫의 대략적인 크기와 부호가 포함된 값을 저장하는 정수에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**remquo** 의 부동 소수점 나머지를 반환 *x* / *y*합니다. 하는 경우의 값 *y* 이 0.0 인 경우 **remquo** 자동 NaN을 반환 합니다. 자동 NaN으로 표현에 대 한 내용은 **printf** 제품군, 참조 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)합니다.

## <a name="remarks"></a>설명

**remquo** 함수는 부동 소수점 나머지 계산 *f* 의 *x* / *y* 되도록 *x*   =  *i* * *y* + *f*여기서 *i* 은 정수 *f* 와 동일한 기호가 *x*, 및의 절대값 *f* 의 절대 값 보다 작으면 *y*합니다.

C + + 오버 로드의 오버 로드를 호출할 수 있도록 허용 **remquo** 사용 하 고 반환 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **remquo** 항상는 두 가지 **double** 인수 및 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------|-|
|**remquo**, **remquof**, **remquol**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_remquo.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;
   int quo = 0;

   z = remquo(w, x, &quo);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
   printf("Approximate signed quotient is %d\n", quo);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
Approximate signed quotient is -3
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
