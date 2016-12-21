---
title: "ldexp | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ldexp"
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
  - "ldexp"
  - "_ldexpl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "실수 계산"
  - "실수 계산"
  - "지수, 부동 소수점 숫자"
  - "부동 소수점 함수, 가수 및 지수"
  - "ldexp 함수"
  - "가수, 부동 소수점 변수"
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ldexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 수에 2의 정수 거듭제곱을 곱합니다.  
  
## 구문  
  
```  
double ldexp(    double x,    int exp  ); float ldexp(    float x,    int exp );  // C++ only long double ldexp(    long double x,    int exp );  // C++ only  float ldexpf(    float x,    int exp );  long double ldexpl(    long double x,    int exp );   
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
 `exp`  
 정수 지수입니다.  
  
## 반환 값  
 `ldexp` 함수는 성공하면 `x` \* 2<sup>exp</sup>의 값을 반환합니다.  오버플로 및 `x`의 부호에 따라 `ldexp`는 \+\/– `HUGE_VAL`을 반환하고 `errno` 값은 `ERANGE`로 설정됩니다.  
  
 `errno` 및 가능한 오류 반환 값에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `float` 또는 `long double` 형식을 사용하는 `ldexp`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `ldexp`는 항상 `double` 및 `int`를 사용하고 `double`을 반환합니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`ldexp`, `ldexpf`, `ldexpl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_ldexp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 4.0, y;  
   int p = 3;  
  
   y = ldexp( x, p );  
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## 출력  
  
```  
4.0 times two to the power of 3 is 32.0  
```  
  
## 해당 .NET Framework 항목  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)