---
title: "lround, lroundf, lroundl, llround, llroundf, llroundl | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- llround
- llroundf
- llroundl
- lroundf
- lround
- lroundl
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
- lround
- lroundl
- llroundl
- llround
- lroundf
- llroundf
dev_langs:
- C++
helpviewer_keywords:
- lround function
- llroundl function
- llround function
- lroundf function
- llroundf function
- lroundl function
ms.assetid: cfb88a35-54c6-469f-85af-f7d695dcfdd8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2a3ec5e749823da6c49b7762334374292c8be50
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="lround-lroundf-lroundl-llround-llroundf-llroundl"></a>lround, lroundf, lroundl, llround, llroundf, llroundl
부동 소수점 값을 가장 가까운 정수로 반올림합니다.  
  
## <a name="syntax"></a>구문  
  
```  
long lround(   
   double x   
);  
long lround(  
   float x  
);  // C++ only  
long lround(  
   long double x  
);  // C++ only  
long lroundf(  
   float x  
);  
long lroundl(  
   long double x  
);  
long long llround(   
   double x   
);  
long long llround(  
   float x  
);  // C++ only  
long long llround(  
   long double x  
);  // C++ only  
long long llroundf(  
   float x  
);  
long long llroundl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 반올림할 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `lround` 및 `llround` 함수는 `x`에 가장 가까운 `long` 또는 `long long` 정수를 반환합니다. 중간값은 부동 소수점 반올림 모드의 설정에 관계없이 0에서 멀어지는 쪽으로 반올림됩니다. 반환되는 오류가 없습니다.  
  
|입력|SEH 예외|Matherr 예외|  
|-----------|-------------------|-----------------------|  
|± `QNAN`, `IND`|없음|`_DOMAIN`|  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `float` 및 `long double` 값을 사용하고 반환하는 `lround` 또는 `llround`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `lround` 및 `llround`는 항상 `double`을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`lround`, `lroundf`, `lroundl`, `llround`, `llroundf`, `llroundl`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_lround.c  
// Build with: cl /W3 /Tc crt_lround.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 3.5 and -3.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 3.5;  
  
   printf("lround(%f) is %d\n", x, lround(x));  
   printf("lround(%f) is %d\n", -x, lround(-x));  
   printf("lroundf(%f) is %d\n", y, lroundf(y));  
   printf("lroundf(%f) is %d\n", -y, lroundf(-y));  
   printf("lroundl(%Lf) is %d\n", z, lroundl(z));  
   printf("lroundl(%Lf) is %d\n", -z, lroundl(-z));  
}  
```  
  
```Output  
lround(2.499999) is 2  
lround(-2.499999) is -2  
lroundf(2.800000) is 3  
lroundf(-2.800000) is -3  
lroundl(2.500000) is 4  
lroundl(-2.500000) is -4  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)