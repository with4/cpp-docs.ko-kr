---
title: cosh, coshf, coshl | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- cosh
- coshf
- coshl
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
- cosh
- coshf
- coshl
dev_langs:
- C++
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d77bb1d1b8f055bb4fe11d4c44c48fb3bf3be535
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395473"
---
# <a name="cosh-coshf-coshl"></a>cosh, coshf, coshl

쌍 곡 코사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
```

```cpp
float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
각도(라디안)입니다.

## <a name="return-value"></a>반환 값

쌍 곡 코사인 *x*합니다.

결과에 너무 큰 경우 기본적으로는 **cosh**, **coshf**, 또는 **coshl** 호출 함수가 반환 **HUGE_VAL** 설정**errno** 를 **ERANGE**합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|없음|**_DOMAIN**|
|*x* ≥ 7.104760e + 002|**부정확 한**+**오버플로가 발생 했습니다.**|**오버플로**|

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **cosh** 사용 하 고 반환 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **cosh** 항상 사용 하 고 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**coshf**, **cosl**, **coshl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

예제를 참조 [sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)합니다.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
