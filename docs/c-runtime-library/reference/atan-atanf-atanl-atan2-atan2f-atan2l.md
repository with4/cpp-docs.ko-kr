---
title: "atan, atanf, atanl, atan2, atan2f, atan2l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
dev_langs: C++
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36e90d781c4cc4512f4869247c296b69b19c1f9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l
`x`(`atan`, `atanf` 및 `atanl`) 또는 `y`/`x`(`atan2`, `atan2f` 및 `atan2l`)의 아크탄젠트를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double atan(   
   double x   
);  
float atan(  
   float x   
);  // C++ only  
long double atan(  
   long double x  
);  // C++ only  
double atan2(   
   double y,   
   double x   
);  
float atan2(  
   float y,  
   float x  
);  // C++ only  
long double atan2(  
   long double y,  
   long double x  
);  // C++ only  
float atanf(   
   float x   
);  
long double atanl(  
   long double x  
);  
float atan2f(  
   float y,  
   float x  
);  
long double atan2l(  
   long double y,  
   long double x  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`, `y`  
 임의의 숫자입니다.  
  
## <a name="return-value"></a>반환 값  
 `atan`아크탄젠트를 반환 `x` π/2 라디안으로 범위-π/2에서입니다. `atan2`아크탄젠트를 반환 `y/x` π 라디안으로 범위 π에 있습니다. `x`가 0이면 `atan`은 0을 반환합니다. `atan2`의 두 매개 변수가 0이면 함수는 0을 반환합니다. 모든 결과는 라디안 단위입니다.  
  
 `atan2`는 두 매개 변수의 기호를 사용하여 반환 값의 사분면을 결정합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
  
## <a name="remarks"></a>설명  
 `atan` 함수는 `x`의 아크탄젠트(역 탄젠트 함수)를 계산합니다. `atan2`는 `y`/`x`의 아크탄젠트를 계산합니다(`x`가 0과 같은 경우, `y`가 양수이면 `atan2`는 π/2, `y`가 음수이면 -π/2, `y`가 0이면 0을 반환).  
  
 `atan`에는 SSE2(스트리밍 SIMD 확장 2)를 사용하는 구현이 포함됩니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)을 참조하세요.  
  
 C++에서는 오버로드를 허용하므로 `atan` 및 `atan2`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `atan` 및 `atan2`는 항상 Double을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`atan`, `atan2`, `atanf`, `atan2f`, `atanl`, `atan2l`|\<math.h>|  
  
## <a name="example"></a>예  
  
```  
// crt_atan.c  
// arguments: 5 0.5  
#include <math.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( int ac, char* av[] )   
{  
   double x, y, theta;  
   if( ac != 3 ){  
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );  
      return 1;  
   }  
   x = atof( av[1] );  
   theta = atan( x );  
   printf( "Arctangent of %f: %f\n", x, theta );  
   y = atof( av[2] );  
   theta = atan2( y, x );  
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );   
   return 0;  
}  
```  
  
```Output  
Arctangent of 5.000000: 1.373401  
Arctangent of 0.500000 / 5.000000: 0.099669  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CIatan](../../c-runtime-library/ciatan.md)   
 [_CIatan2](../../c-runtime-library/ciatan2.md)