---
title: "scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft Docs"
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
  - "scalblnl"
  - "scalbnl"
  - "scalbnf"
  - "scalblnf"
  - "scalbn"
  - "scalbln"
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
  - "scalblnf"
  - "scalbnl"
  - "scalblnl"
  - "scalbln"
  - "scalbn"
  - "scalbnf"
dev_langs: 
  - "C++"
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 수에 FLT\_RADIX의 정수 제곱을 곱합니다.  
  
## 구문  
  
```  
double scalbn(    double x,    int exp  ); float scalbn(    float x,    int exp );  // C++ only long double scalbn(    long double x,    int exp );  // C++ only  float scalbnf(    float x,    int exp );  long double scalbnl(    long double x,    int exp ); double scalbln(    double x,    long exp  ); float scalbln(    float x,    long exp );  // C++ only long double scalbln(    long double x,    long exp );  // C++ only  float scalblnf(    float x,    long exp );  long double scalblnl(    long double x,    long exp );  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
 `exp`  
 정수 지수입니다.  
  
## 반환 값  
 `scalbn` 함수는 성공하면 `x` \* `FLT_RADIX`<sup>exp</sup>의 값을 반환합니다.  오버플로 시 `x`의 부호에 따라 `scalbn`는 \+\/– `HUGE_VAL`을 반환하고 `errno` 값은 `ERANGE`로 설정됩니다.  
  
 `errno` 및 가능한 오류 반환 값에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `FLT_RADIX`는 \<float.h\>에 네이티브 부동 소수점 radix로 정의되어 있고 이진 시스템에서는 값이 2이며 `scalbn`은 [ldexp](../../c-runtime-library/reference/ldexp.md)와 동일합니다.  
  
 C\+\+에서는 오버로드를 허용하므로 `float` 또는 `long double` 형식을 사용 및 반환하는 `scalbn` 및 `scalbln`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `scalbn`은 항상 `double` 및 `int`를 사용하고 `double`을 반환하고 `scalbln`은 항상 `double` 및 `long`을 사용하고 `double`을 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## 출력  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## 해당 .NET Framework 항목  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)