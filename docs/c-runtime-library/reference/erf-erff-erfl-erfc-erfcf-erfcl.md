---
title: erf, erff, erfl, erfc, erfcf, erfcl | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b7ab1448c3f1d77ab79266858a19d822b1cdb4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

값의 오차 함수 또는 보상 오차 함수를 계산합니다.

## <a name="syntax"></a>구문

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**erf** 함수 반환 가우스의 오류 함수 *x*합니다. **erfc** 함수 반환 가우스 보상 오차 함수의 *x*합니다.

## <a name="remarks"></a>설명

**erf** 함수 계산의 가우스 오차 함수 *x*, 정의 됩니다.

![x의 오차 함수](media/crt_erf_formula.PNG "CRT_erf_formula")

가우스 보상 오차 함수는-1로 정의 된 erf (x). **erf** 함수 1.0-1.0 범위의 값을 반환 합니다. 반환되는 오류가 없습니다. **erfc** 함수에 0 ~ 2 범위의 값을 반환 합니다. 경우 *x* 너무 커서 **erfc**, **errno** 변수가로 설정 된 **ERANGE**합니다.

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **erf** 및 **erfc** 사용 하 고 반환 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **erf** 및 **erfc** 항상 사용 하 고 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
