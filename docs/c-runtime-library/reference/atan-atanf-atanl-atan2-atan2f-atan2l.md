---
title: "atan, atanf, atanl, atan2, atan2f, atan2l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atan2f"
  - "atan2l"
  - "atan2"
  - "atanf"
  - "atan"
  - "atanl"
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
  - "atan"
  - "atan2l"
  - "atan2"
  - "atanl"
  - "atanf"
  - "atan2f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "아크탄젠트 함수"
  - "atan 함수"
  - "atan2 함수"
  - "atan2f 함수"
  - "atan2l 함수"
  - "atanf 함수"
  - "atanl 함수"
  - "삼각 함수"
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# atan, atanf, atanl, atan2, atan2f, atan2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

아크탄젠트인 `x` \(`atan`, `atanf`, 및 `atanl`\) 또는 아크탄젠트인 `y`\/`x` \(`atan2`, `atan2f`, 및 `atan2l`\).를 계산합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `x`, `y`  
 모든 숫자.  
  
## 반환 값  
 `atan` 아크탄젠트 값을 `x` π\/2 라디안 범위 –π\/2에서 반환합니다.  `atan2` 아크탄젠트 값을 `y/x` π\/2 라디안 범위 –π\/2에서 반환합니다.  `x` 가 0인경우, `atan` 는 0을 반환합니다.  두 매개변수인 `atan2` 가 0인 경우, 함수는 0을 반환 합니다.  모든 결과 라디안입니다.  
  
 `atan2` 사분면의 반환 값을 확인 하려면 두 매개 변수의 기호를 사용 합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
  
## 설명  
 `atan` \(역 탄젠트 함수\)의 아크탄젠트를 계산 하는 함수 `x` 입니다.  `atan2` 아크탄젠트인 `y`\/`x` 를 계산합니다. \( `x` 0 인경우 `atan2` π\/2를 반환합니다. `y` 가 양수인 경우, \-π\/2를 반환합니다. `y` 가 음수인 경우, 또는 `y` 가 0인 경우.\)  
  
 `atan` 스트리밍 SIMD 확장 2 \(SSE2\)을 사용하여구현을 했습니다.  정보 및 SSE2 구현을 사용하는 방법에 대한 제한 사항을 참조 하십시오. [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 C \+ \+ 오버 로딩을 허용하기 때문에 오버 로드인 `atan` 및 `atan2`을 호출할 수 있습니다.  C 프로그램에서 `atan` 및 `atan2` 는 항상 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`atan`, `atan2`, `atanf`, `atan2f`, `atanl`, `atan2l`|\<math.h\>|  
  
## 예제  
  
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
  
  **5.000000: 1.373401의 아크탄젠트 값**  
**5.000000: 1.373401의 아크탄젠트 값**   
## 해당 .NET Framework 항목  
  
-   [System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx)  
  
-   [System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIatan](../../c-runtime-library/ciatan.md)   
 [\_CIatan2](../../c-runtime-library/ciatan2.md)