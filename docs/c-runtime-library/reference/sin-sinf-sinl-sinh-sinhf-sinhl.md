---
title: sin, sinf, sinl, sinh, sinhf, sinhl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- sinl
- sinf
- sinhf
- sinh
- sin
- sinhl
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
- _sinl
- sinf
- sinhl
- sinl
- sin
- sinhf
- _sinhl
dev_langs:
- C++
helpviewer_keywords:
- sinh function
- _sinl function
- _sinhl function
- sinhf function
- sinl function
- calculating sines
- sin function
- trigonometric functions
- sinf function
- sinhl function
- hyperbolic functions
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54718553d71a498463dbc881da8ceb3401ff5b5b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="sin-sinf-sinl-sinh-sinhf-sinhl"></a>sin, sinf, sinl, sinh, sinhf, sinhl
사인 및 쌍곡선 사인을 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
double sin(double x);
  
float sin(float x);  // C++ only 
 
long double sin(long double x);  // C++ only  

float sinf(float x);  

long double sinl(long double x);  

double sinh(double x);  

float sinh(float x);  // C++ only  

long double sinh(long double x);  // C++ only  

float sinhf(float x);  

long double sinhl(long double x);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 각도(라디안)입니다.  
  
## <a name="return-value"></a>반환 값  
 `sin` 함수는 `x`의 사인을 반환합니다. 경우 `x` 보다 큰 또는 263 같거나 작은 보다 크거나-263, 결과에 중요 한 손실이 발생 합니다.  
  
 `sinh` 함수는 `x`의 쌍곡선 사인을 반환합니다. 기본적으로 결과가 너무 크면 `sinh`는 `errno`를 `ERANGE`로 설정하고 ±`HUGE_VAL`을 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|없음|_DOMAIN|  
|± ∞ (sin, sinf, sinl)|INVALID|_DOMAIN|  
|&#124;x&#124; ≥ 7.104760e+002(sinh, sinhf, sinhl)|OVERFLOW+INEXACT|OVERFLOW|  
  
 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 C++는 오버로딩을 허용하기 때문에 `sin` 또는 `sinh` 값을 사용하고 반환하는 `float` 및 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `sin` 및 `sinh`는 항상 `double`을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`sin`, `sinf`, `sinl`, `sinh`, `sinhf`, `sinhl`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_sincos.c  
// This program displays the sine, hyperbolic  
// sine, cosine, and hyperbolic cosine of pi / 2.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void)  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = pi / 2;  
   y = sin( x );  
   printf( "sin( %f ) = %f\n", x, y );  
   y = sinh( x );  
   printf( "sinh( %f ) = %f\n",x, y );  
   y = cos( x );  
   printf( "cos( %f ) = %f\n", x, y );  
   y = cosh( x );  
   printf( "cosh( %f ) = %f\n",x, y );  
}  
```  
  
```Output  
sin( 1.570796 ) = 1.000000  
sinh( 1.570796 ) = 2.301299  
cos( 1.570796 ) = 0.000000  
cosh( 1.570796 ) = 2.509178  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CIsin](../../c-runtime-library/cisin.md)