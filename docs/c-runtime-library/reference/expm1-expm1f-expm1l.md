---
title: expm1, expm1f, expm1l | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
dev_langs:
- C++
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba382fb29b5ec841d9acd127ad5f48e0ca7b68fa
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l

값의 밑이 e인 지수 - 1을 계산합니다.

## <a name="syntax"></a>구문

```C
double expm1(
   double x
);
float expm1(
   float x
);  // C++ only
long double expm1(
   long double x
);  // C++ only
float expm1f(
   float x
);
long double expm1l(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 지수 값입니다.

## <a name="return-value"></a>반환 값

**expm1** 함수 e를 나타내는 부동 소수점 값을 반환<sup>x</sup> -1, 성공 하는 경우. 오버플로에서 **expm1** 반환 **HUGE_VAL**, **expm1f** 반환 **HUGE_VALF**, **expm1l** 반환 **HUGE_VALL**, 및 **errno** 로 설정 된 **ERANGE**합니다. 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **expm1** 사용 하 고 반환 **float** 및 **긴** **double** 값입니다. C 프로그램에서 **expm1** 항상 사용 하 고 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
