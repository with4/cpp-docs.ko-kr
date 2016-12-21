---
title: "rint, rintf, rintl | Microsoft Docs"
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
  - "rintf"
  - "rintl"
  - "rint"
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
  - "rintf"
  - "rintl"
  - "rint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rintf 함수"
  - "rint 함수"
  - "rintl 함수"
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rint, rintf, rintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값을 부동 소수점 형식의 가장 가까운 정수로 반올림합니다.  
  
## 구문  
  
```  
double rint( double x ); float rint( float x );  // C++ only long double rint( long double x );  // C++ only float rintf( float x );  long double rintl( long double x );    
```  
  
#### 매개 변수  
 `x`  
 반올림할 부동 소수점 값입니다.  
  
## 반환 값  
 `rint` 함수는 `x`에 가장 가까운 정수를 나타내는 부동 소수점 값을 반환합니다.  중간값은 `nearbyint` 함수와 마찬가지로 부동 소수점 반올림 모드의 현재 설정에 따라 반올림됩니다.  `nearbyint` 함수와 달리 `rint` 함수는 결과가 인수의 값과 다른 경우 `FE_INEXACT` 부동 소수점 예외를 일으킬 수 있습니다.  반환되는 오류가 없습니다.  
  
|입력|SEH 예외|`_matherr` 예외|  
|--------|------------|-------------------|  
|± ∞, QNAN, IND|없음|없음|  
|Denormals|EXCEPTION\_FLT\_UNDERFLOW|없음|  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `float` 및 `long double` 값을 사용 및 반환하는 `rint`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `rint`는 항상 `double`을 사용 및 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`rint`, `rintf`, `rintl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_rint.c  
// Build with: cl /W3 /Tc crt_rint.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 2.5 and -2.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 2.5;  
  
   printf("rint(%f) is %.0f\n", x, rint (x));  
   printf("rint(%f) is %.0f\n", -x, rint (-x));  
   printf("rintf(%f) is %.0f\n", y, rintf(y));  
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));  
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));  
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));  
}  
```  
  
  **rint\(2.499999\)는 2입니다.**  
**rint\(\-2.499999\)는 \-2입니다.**  
**rintf\(2.800000\)은 3입니다.**  
**rintf\(\-2.800000\)은 \-3입니다.**  
**rintl\(2.500000\)은 3입니다.**  
**rintl\(\-2.500000\)은 \-3입니다.**   
## 해당 .NET Framework 항목  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](http://msdn.microsoft.com/ko-kr/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [lround, lroundf, lroundl, llround, llroundf, llroundl](../../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)   
 [nearbyint, nearbyintf, nearbyintl](http://msdn.microsoft.com/ko-kr/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint](../../c-runtime-library/reference/rint-rintf-rintl.md)