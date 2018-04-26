---
title: atanh, atanhf, atanhl | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- atanhl
- atanhf
- atanh
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
- atanhl
- atanhf
- atanh
dev_langs:
- C++
helpviewer_keywords:
- atanhf function
- atanhl function
- atanh funciton
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f56568fa4e38d68e45acf976a8802971e63ea66
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="atanh-atanhf-atanhl"></a>atanh, atanhf, atanhl

역쌍곡 탄젠트를 계산합니다.

## <a name="syntax"></a>구문

```C
double atanh( double x );
float atanhf( float x );
long double atanhl( long double x );
```

```cpp
float atanh( float x );  // C++ only
long double atanh( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**atanh** 함수 반환의 역 탄젠트 (쌍 곡 아크탄젠트) *x*합니다. 경우 *x* 1 또는-1 보다 작은 보다 크면 **errno** 로 설정 된 **EDOM** 결과 quiet NaN입니다. 경우 *x* 은 1 또는-1 이상이 면 양 또는 음의 무한대가 각각 반환 되, 및 **errno** 로 설정 된 **ERANGE**합니다.

|입력|SEH 예외|**Matherr** 예외|
|-----------|-------------------|-------------------------|
|± QNAN,IND|없음|없음|
|*X* ≥ 1; *x* ≤-1|없음|없음|

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **atanh** 사용 하 고 반환 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **atanh** 항상 사용 하 고 반환 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**atanh**, **atanhf**, **atanhl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_atanh.c
// This program displays the hyperbolic tangent of pi / 4
// and the arc hyperbolic tangent of the result.
//

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = tanh( pi / 4 );
   y = atanh( x );
   printf( "tanh( %f ) = %f\n", pi/4, x );
   printf( "atanh( %f ) = %f\n", x, y );
}
```

```Output
tanh( 0.785398 ) = 0.655794
atanh( 0.655794 ) = 0.785398
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
