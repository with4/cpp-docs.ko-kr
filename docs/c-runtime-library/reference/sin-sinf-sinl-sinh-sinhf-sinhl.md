---
title: "sin, sinf, sinl, sinh, sinhf, sinhl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "sinl"
  - "sinf"
  - "sinhf"
  - "sinh"
  - "sin"
  - "sinhl"
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
  - "_sinl"
  - "sinf"
  - "sinhl"
  - "sinl"
  - "sin"
  - "sinhf"
  - "_sinhl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sinhl 함수"
  - "_sinl 함수"
  - "사인 계산"
  - "하이퍼볼릭 함수"
  - "sin 함수"
  - "sinf 함수"
  - "sinh 함수"
  - "sinhf 함수"
  - "sinhl 함수"
  - "sinl 함수"
  - "삼각 함수"
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# sin, sinf, sinl, sinh, sinhf, sinhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사인과 하이퍼볼릭 사인을 계산합니다.  
  
## 구문  
  
```  
double sin(  
   double x   
);  
float sin(  
   float x  
);  // C++ only  
long double sin(  
   long double x  
);  // C++ only  
float sinf(  
   float x   
);  
long double sinl(  
   long double x  
);  
double sinh(  
   double x   
);  
float sinh(  
   float x   
);  // C++ only  
long double sinh(  
   long double x  
);  // C++ only  
float sinhf(  
   float x  
);  
long double sinhl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 라디안에서 단위의 각도입니다.  
  
## 반환 값  
 `sin` 함수는  `x` 의 사인 값을 반환합니다.   `x` 가 263와 같거나 클 경우 또는 –263와 같거나 작을 경우, 결과에 중요한 손실 발생합니다.  
  
 `sinh` 함수는  `x` 의 쌍곡선 사인을 반환합니다.  기본적으로 결과가 너무 큰 경우  `sinh` 는  `errno`  을  `ERANGE` 으로 설정하고 ±`HUGE_VAL`을 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± QNAN,IND|없음|\_DOMAIN|  
|± ∞ \(sin, sinf, sinl\)|잘못된|\_DOMAIN|  
|&#124;x&#124; ≥ 7.104760e\+002 \(sinh, sinhf, sinhl\)|OVERFLOW\+INEXACT|오버플로가 발생했습니다.|  
  
 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.  
  
## 설명  
 C\+\+가 오버로딩을 허용하기 때문에 `float` 혹은 `long double` 값을 사용하고 반환하는 `sin` 과 `sinh` 의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `sin` 및 `sinh`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`sin`, `sinf`, `sinl`, `sinh`, `sinhf`, `sinhl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_sincos.c  
// This program displays the sine, hyperbolic  
// sine, cosine, and hyperbolic cosine of pi / 2.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
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
  
  **sin\( 1.570796 \) \= 1.000000**  
**sinh\( 1.570796 \) \= 2.301299**  
**cos\( 1.570796 \) \= 0.000000**  
**cosh\( 1.570796 \) \= 2.509178**   
## 해당 .NET Framework 항목  
  
-   [System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx)  
  
-   [System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIsin](../../c-runtime-library/cisin.md)