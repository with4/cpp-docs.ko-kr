---
title: modf, modff, modfl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
dev_langs:
- C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87cddb8b565cdc369e6b1e9679583db64039bb49
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404833"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

부동 소수점 값을 소수 부분과 정수 부분으로 분할합니다.

## <a name="syntax"></a>구문

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*intptr*<br/>
저장된 정수 부분에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이 함수는 *x*의 부호 있는 소수 부분을 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

**modf** 함수 부동 소수점 값을 구분 *x* 소수 부분에 각각 같은 부호를 포함 하는 정수 부품 및 *x*합니다. 부호 있는 소수 부분 *x* 반환 됩니다. 정수 부분에서 부동 소수점 값으로 저장 됩니다 *intptr*합니다.

**modf** 스트리밍 SIMD 확장명 2 (SSE2)를 사용 하는 구현 합니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

C + + 오버 로드의 오버 로드를 호출할 수 있도록 허용 **modf** 사용 하 고 반환 **float** 또는 **긴** **double** 매개 변수입니다. C 프로그램에서 **modf** 항상 두 double 값을 사용 하 고 double 값을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h><br /><br /> C++: , \<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_modf.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y, n;

   x = -14.87654321;      /* Divide x into its fractional */
   y = modf( x, &n );     /* and integer parts            */

   printf( "For %f, the fraction is %f and the integer is %.f\n",
           x, y, n );
}
```

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
