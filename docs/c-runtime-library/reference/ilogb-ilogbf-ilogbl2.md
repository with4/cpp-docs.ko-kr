---
title: ilogb, ilogbf, ilogbl2 | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1436874e1ab35cc72dc40390adf5597529d3bf57
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398181"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

지정된 값의 밑이 2인 비편향 지수를 나타내는 정수를 검색합니다.

## <a name="syntax"></a>구문

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);

```

### <a name="parameters"></a>매개 변수

*x*<br/>
지정된 값입니다.

## <a name="return-value"></a>반환 값

성공 하면 반환의 밑이 2 인 지 수 *x* signed로 **int** 값입니다.

그렇지 않으면 \<math.h>에 정의된 다음 값 중 하나를 반환합니다.

|입력|결과|
|-----------|------------|
|±0|FP_ILOGB0|
|±inf, ±nan, 무한|FP_ILOGBNAN|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **ilogb** 사용 하 고 반환 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **ilogb** 항상 사용 하 고 반환 된 **double**합니다.

이 함수를 호출 하는 것은 해당 하는 호출 비슷합니다 **logb** 함수를 다음 반환 값을 캐스팅 **int**합니다.

## <a name="requirements"></a>요구 사항

|루틴|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**ilogb**, **ilogbf**, **ilogbl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
