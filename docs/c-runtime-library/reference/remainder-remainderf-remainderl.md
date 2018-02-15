---
title: remainder, remainderf, remainderl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7a5d55fd079f03338a6860755a783ba4d82b76
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl
두 부동 소수점 값 몫의 나머지를 가장 가까운 적분 값으로 반올림하여 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
## <a name="return-value"></a>반환 값  
 `x` / `y`의 부동 소수점 나머지입니다. `y`의 값이 0.0인 경우 `remainder`는 자동 NaN을 반환합니다. `printf` 패밀리의 자동 NaN 표현에 대한 자세한 내용은 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `remainder` 함수는 `x` / `y`의 부동 소수점 나머지 `r`을 계산합니다(예: `x` = `n` * `y` + `r`). 여기서 `n`은 값이 `x` / `y`에 가장 가까운 정수이고, `n`은 &#124; `n` - `x` / `y` &#124; = 1/2일 때마다 짝수입니다. `r` = 0이면, `r`과 `x`의 부호는 동일합니다.  
  
 C++에서는 오버로드를 허용하므로 `remainder` 또는 `float` 값을 사용 및 반환하는 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `remainder`는 항상 double 값 두 개를 사용하며 double 값 하나를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`remainder`, `remainderf`, `remainderl`|\<math.h>|  
  
 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```C  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)