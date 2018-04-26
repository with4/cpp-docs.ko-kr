---
title: scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
dev_langs:
- C++
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 111978053b35b73a4b5ef9b07e1ecb987d84f6bf
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl

부동 소수점 수에 FLT_RADIX의 정수 제곱을 곱합니다.

## <a name="syntax"></a>구문

```C
double scalbn(
   double x,
   int exp
);
float scalbn(
   float x,
   int exp
);  // C++ only
long double scalbn(
   long double x,
   int exp
);  // C++ only
float scalbnf(
   float x,
   int exp
);
long double scalbnl(
   long double x,
   int exp
);
double scalbln(
   double x,
   long exp
);
float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*exp*<br/>
정수 지수입니다.

## <a name="return-value"></a>반환 값

**scalbn** 의 값을 반환 하는 함수 *x* * **FLT_RADIX**<sup>exp</sup> 로그인이 성공 합니다. 오버플로에서 (의 부호에 따라 *x*), **scalbn** + /-반환 **HUGE_VAL**; **errno** 값으로 설정 되어 **ERANGE** .

에 대 한 자세한 내용은 **errno** 및 반환 값, 참조 가능한 오류 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.

## <a name="remarks"></a>설명

**FLT_RADIX** 에 정의 된 \<float.h > 값이 2에 네이티브 부동 소수점 기수로 서; 이진 시스템 및 **scalbn** 같습니다 [ldexp](ldexp.md)합니다.

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **scalbn** 및 **scalbln** 사용 하 고 반환 **float** 또는 **긴** **double** 형식입니다. C 프로그램에서 **scalbn** 항상 약간의 **double** 및 **int** 반환는 **double**, 및 **scalbln**항상 약간의 **double** 및 **긴** 반환는 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**scalbn**, **scalbnf**, **scalbnl**, **scalbln**, **scalblnf**, **scalblnl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_scalbn.c
// Compile using: cl /W4 crt_scalbn.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 6.4, y;
   int p = 3;

   y = scalbn( x, p );
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );
}
```

### <a name="output"></a>출력

```Output
6.4 times FLT_RADIX to the power of 3 is 51.2
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
