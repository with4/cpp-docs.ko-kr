---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs:
- C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c68d039ff1318ea082d409078a55c8d337a48de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403718"
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

표현 가능한 다음 부동 소수점 값을 반환합니다.

## <a name="syntax"></a>구문

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
시작할 부동 소수점 값입니다.

*y*<br/>
종료할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

후 반환 형식의 다음 표현 가능한 부동 소수점 값을 반환 *x* 방향으로 *y*합니다. 경우 *x* 및 *y* 같은지 함수 반환 *y*트리거된 예외가 없는 반환 형식으로 변환 합니다. 경우 *x* 과 같지 않은 *y*, 결과 0, 또는 비정상적인은 **FE_UNDERFLOW** 및 **FE_INEXACT** 부동 소수점 예외 상태 설정 되 고 올바른 결과 반환 됩니다. 어느 경우 *x* 또는 *y* 는 NAN, 반환 값은 입력된 Nan 중 하나입니다. 경우 *x* 한정 되어 있으므로 결과 무한 또는 형식으로 표현할 수 없습니다, 올바르게 서명 된 infinity 또는 NAN 반환 됩니다, **FE_OVERFLOW** 및 **FE_INEXACT** 부동 소수점 예외 상태를 설정 하 고 **errno** 로 설정 된 **ERANGE**합니다.

## <a name="remarks"></a>설명

**nextafter** 및 **nexttoward** 함수 패밀리는 매개 변수 형식 제외 하 고 해당 *y*합니다. 경우 *x* 및 *y* 가 같으면 반환 값은 *y* 반환 형식으로 변환 합니다.

C + + 오버 로드를 포함 하는 경우 허용 하므로 \<cmath >의 오버 로드를 호출할 수 **nextafter** 및 **nexttoward** 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **nextafter** 및 **nexttoward** 항상 반환 **double**합니다.

**_nextafter** 및 **_nextafterf** 함수는 Microsoft 전용입니다. **_nextafterf** x64를 컴파일할 경우 함수는 사용할 수만 있습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf** , **nexttowardl**|\<math.h>|\<math.h> 또는 \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> 또는 \<cfloat>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
