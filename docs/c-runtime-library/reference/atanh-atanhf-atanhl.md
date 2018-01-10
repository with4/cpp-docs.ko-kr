---
title: "atanh, atanhf, atanhl | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- atanhl
- atanhf
- atanh
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
- atanhl
- atanhf
- atanh
dev_langs: C++
helpviewer_keywords:
- atanhf function
- atanhl function
- atanh funciton
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a9e88a28ca99fdad07e91ab305944b2de276db8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atanh-atanhf-atanhl"></a>atanh, atanhf, atanhl
역쌍곡 탄젠트를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double atanh(  
   double x   
);  
float atanh(  
   float x   
);  // C++ only  
long double atanh(  
   long double x  
);  // C++ only  
float atanhf(  
   float x   
);  
long double atanhl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `atanh` 함수는 `x`의 역쌍곡 탄젠트를 반환합니다. 경우 `x` 1 또는-1 보다 작은 보다 크면 `errno` 로 설정 된 `EDOM` 결과 quiet NaN입니다. `x`가 1 또는 -1인 경우에는 양 또는 음의 무한대가 각각 반환되고 `errno`는 `ERANGE`로 설정됩니다.  
  
|입력|SEH 예외|`Matherr` 예외|  
|-----------|-------------------|-------------------------|  
|± QNAN,IND|없음|없음|  
|`X` ≥ 1; `x` ≤ -1|없음|없음|  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `atanh` 또는 `float` 값을 사용 및 반환하는 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `atanh`는 항상 `double`을 사용 및 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`atanh`, `atanhf`, `atanhl`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_atanh.c  
// This program displays the hyperbolic tangent of pi / 4  
// and the arc hyperbolic tangent of the result.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = tanh( pi / 4 );  
   y = atanh( x );  
   printf( "tanh( %f ) = %f\n", pi/4, x );  
   printf( "atanh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
tanh( 0.785398 ) = 0.655794  
atanh( 0.655794 ) = 0.785398  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CItan](../../c-runtime-library/citan.md)