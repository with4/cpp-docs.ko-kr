---
title: "asinh, asinhf, asinhl | Microsoft Docs"
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
  - "asinh"
  - "asinhf"
  - "asinhl"
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
  - "asinhf"
  - "asinhl"
  - "asinh"
dev_langs: 
  - "C++"
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asinh, asinhf, asinhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

역쌍곡 사인을 계산합니다.  
  
## 구문  
  
```  
double asinh(    double x  ); float asinh(    float x  );  // C++ only long double asinh(    long double x );  // C++ only float asinhf(    float x  ); long double asinhl(    long double x );  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## 반환 값  
 `asinh` 함수는 `x`의 역쌍곡 사인을 반환합니다.  이 함수는 부동 소수점 도메인에 대해 유효합니다.  `x`가 Quiet NaN, 무한 또는 무한대이면 동일한 값이 반환됩니다.  
  
|입력|SEH 예외|`_matherr` 예외|  
|--------|------------|-------------------|  
|± QNAN, IND, INF|없음|없음|  
  
## 설명  
 C\+\+을 사용하면 `float` 또는 `long double` 값을 사용 및 반환하는 `asinh`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `asinh`는 항상 `double`을 사용 및 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`asinh`, `asinhf`, `asinhl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```c  
// crt_asinh.c  
// Compile by using: cl /W4 crt_asinh.c  
// This program displays the hyperbolic sine of pi / 4  
// and the arc hyperbolic sine of the result.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = sinh( pi / 4 );  
   y = asinh( x );  
   printf( "sinh( %f ) = %f\n", pi/4, x );  
   printf( "asinh( %f ) = %f\n", x, y );  
}  
```  
  
  **sinh\( 0.785398 \) \= 0.868671**  
**asinh\( 0.868671 \) \= 0.785398**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [acosh, acoshf, acoshl](../../c-runtime-library/reference/acosh-acoshf-acoshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [atanh, atanhf, atanhl](../../c-runtime-library/reference/atanh-atanhf-atanhl.md)   
 [\_CItan](../../c-runtime-library/citan.md)