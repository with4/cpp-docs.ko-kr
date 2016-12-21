---
title: "acosh, acoshf, acoshl | Microsoft Docs"
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
  - "acoshf"
  - "acosh"
  - "acoshl"
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
  - "acosh"
  - "acoshf"
  - "acoshl"
  - "math/acosh"
  - "math/acoshf"
  - "math/acoshl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acoshf 함수"
  - "acosh 함수"
  - "acoshl 함수"
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# acosh, acoshf, acoshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

역쌍곡 코사인을 계산합니다.  
  
## 구문  
  
```  
double acosh(  
   double x   
);  
float acosh(  
   float x   
);  // C++ only  
long double acosh(  
   long double x  
);  // C++ only  
float acoshf(  
   float x   
);  
long double acoshl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## 반환 값  
 `acosh` 함수는 `x`의 역쌍곡 코사인을 반환합니다. 이러한 함수는 도메인 `x` ≥ 1에 대해서 유효합니다.`x`가 1보다 작으면 `errno`는 `EDOM`으로 설정되고 결과는 Quiet NaN입니다.`x`가 Quiet NaN, 무한 또는 무한대이면 동일한 값이 반환됩니다.  
  
|입력|SEH 예외|`_matherr` 예외|  
|--------|------------|-------------------|  
|± QNAN, IND, INF|없음|없음|  
|x \< 1|없음|없음|  
  
## 설명  
 C\+\+을 사용하면 `acosh` 또는 `float` 값을 사용 및 반환하는 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `acosh`는 항상 `double`을 사용 및 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`acosh`, `acoshf`, `acoshl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```c  
// crt_acosh.c  
// Compile by using: cl /W4 crt_acosh.c  
// This program displays the hyperbolic cosine of pi / 4  
// and the arc hyperbolic cosine of the result.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = cosh( pi / 4 );  
   y = acosh( x );  
   printf( "cosh( %f ) = %f\n", pi/4, x );  
   printf( "acosh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
cosh( 0.785398 ) = 1.324609 acosh( 1.324609 ) = 0.785398  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하세요.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [asinh, asinhf, asinhl](../../c-runtime-library/reference/asinh-asinhf-asinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [atanh, atanhf, atanhl](../../c-runtime-library/reference/atanh-atanhf-atanhl.md)   
 [\_CItan](../../c-runtime-library/citan.md)