---
title: _scalb, _scalbf | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _scalb
- _scalbf
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
- scalb
- _scalb
- _scalbf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47b6e20c6395337113088aa51d8ba75744421922
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207522"
---
# <a name="scalb-scalbf"></a>_scalb, _scalbf

2의 거듭제곱으로 인수의 크기를 조정합니다.

## <a name="syntax"></a>구문

```C
double _scalb(
   double x,
   long exp
);
float _scalbf(
   float x,
   long exp
); /* x64 only */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
배정밀도, 부동 소수점 값입니다.

*exp*<br/>
정수(Long) 지수입니다.

## <a name="return-value"></a>반환 값

성공하는 경우 지수 값을 반환합니다. 오버플로에서 (의 부호에 따라 *x*), **_scalb** + /-반환 **HUGE_VAL**; **errno** 변수가로 설정 된  **ERANGE**합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

합니다 **_scalb** 의 값을 계산 하는 함수 *x* \* 2<sup>*exp*</sup>합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_scalb**, **_scalbf**|\<float.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
