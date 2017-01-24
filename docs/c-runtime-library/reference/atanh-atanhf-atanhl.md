---
title: "atanh, atanhf, atanhl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atanhl"
  - "atanhf"
  - "atanh"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "atanhl"
  - "atanhf"
  - "atanh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atanh 함수"
  - "atanhf 함수"
  - "atanhl 함수"
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atanh, atanhf, atanhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

역쌍곡 탄젠트를 계산합니다.  
  
## 구문  
  
```  
double atanh(    double x  ); float atanh(    float x  );  // C++ only long double atanh(    long double x );  // C++ only float atanhf(    float x  ); long double atanhl(    long double x );  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## 반환 값  
 `atanh` 함수는 `x`의 역쌍곡 탄젠트를 반환합니다.  `x`가 1보다 크거나 –1 보다 작은 경우 `errno`는 `EDOM`으로 설정되고 결과는 Quiet NaN입니다.  `x`가 1 또는 \-1인 경우에는 양 또는 음의 무한대가 각각 반환되고 `errno`는 `ERANGE`로 설정됩니다.  
  
|입력|SEH 예외|`Matherr` 예외|  
|--------|------------|------------------|  
|± QNAN,IND|없음|없음|  
|`X` ≥ 1; `x` ≤ \-1|없음|없음|  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `float` 또는 `long double` 값을 사용 및 반환하는 `atanh`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `atanh`는 항상 `double`을 사용 및 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`atanh`, `atanhf`, `atanhl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
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
  
  **tanh\( 0.785398 \) \= 0.655794**  
**atanh\( 0.655794 \) \= 0.785398**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CItan](../../c-runtime-library/citan.md)