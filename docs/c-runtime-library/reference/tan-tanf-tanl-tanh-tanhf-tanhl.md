---
title: tan, tanf, tanl, tanh, tanhf, tanhl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tanhf
- tanh
- tan
- tanhl
- tanf
- tanl
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
- tanh
- tan
- _tanl
- tanl
- _tanhl
- tanf
- tanhf
- tanhl
dev_langs: C++
helpviewer_keywords:
- tanl function
- tanhl function
- _tanl function
- _tanhl function
- tan function
- calculating tangents
- tangent
- tanh function
- tanhf function
- tanf function
- trigonometric functions
- hyperbolic functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a418683e23525d6e3c46853312b217788c0969e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tan-tanf-tanl-tanh-tanhf-tanhl"></a>tan, tanf, tanl, tanh, tanhf, tanhl
탄젠트(`tan`, `tanf` 또는 `tanl`) 또는 쌍곡선 탄젠트(`tanh`, `tanhf` 또는 `tanhl`)를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double tan(  
   double x   
);  
float tan(  
   float x   
);  // C++ only  
long double tan(  
   long double x  
);  // C++ only  
float tanf(  
   float x   
);  
long double tanl(  
   long double x  
);  
double tanh(  
   double x   
);  
float tanh(  
   float x   
);  // C++ only  
long double tanh(  
   long double x  
);  // C++ only  
float tanhf(  
   float x   
);  
long double tanhl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 각도(라디안)입니다.  
  
## <a name="return-value"></a>반환 값  
 `tan` 함수는 `x`의 탄젠트를 반환합니다. 경우 `x` 보다 큰 또는 263 같거나 작은 보다 크거나-263, 결과에 중요 한 손실이 발생 합니다.  
  
 `tanh` 함수는 `x`의 쌍곡선 탄젠트를 반환합니다. 반환되는 오류가 없습니다.  
  
|입력|SEH 예외|`Matherr` 예외|  
|-----------|-------------------|-------------------------|  
|± QNAN,IND|없음|_DOMAIN|  
|± ∞  (`tan`, `tanf`)|`INVALID`|_DOMAIN|  
  
## <a name="remarks"></a>설명  
 C++는 오버로딩을 허용하기 때문에 `tan` 또는 `tanh` 값을 사용하고 반환하는 `float` 및 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `tan` 및 `tanh`는 항상 `double`을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`tan`, `tanf`, `tanl`, `tanh`, `tanhf`, `tanhl`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_tan.c  
// This program displays the tangent of pi / 4  
// and the hyperbolic tangent of the result.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = tan( pi / 4 );  
   y = tanh( x );  
   printf( "tan( %f ) = %f\n", pi/4, x );  
   printf( "tanh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
tan( 0.785398 ) = 1.000000  
tanh( 1.000000 ) = 0.761594  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [_CItan](../../c-runtime-library/citan.md)