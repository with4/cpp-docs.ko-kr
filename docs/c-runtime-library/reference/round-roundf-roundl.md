---
title: "round, roundf, roundl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "round"
  - "roundl"
  - "roundf"
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
  - "roundf"
  - "roundl"
  - "round"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "round 함수"
  - "roundf 함수"
  - "roundl 함수"
ms.assetid: 6be90877-193c-4b80-a32b-c3eca33f9c6f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# round, roundf, roundl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값을 가장 가까운 정수로 반올림합니다.  
  
## 구문  
  
```  
double round(   
   double x   
);  
float round(  
   float x  
);  // C++ only  
long double round(  
   long double x  
);  // C++ only  
float roundf(  
   float x  
);  
long double roundl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 반올림할 부동 소수점 지수 값입니다.  
  
## 반환 값  
 `round` 함수는 `x`에 대한 가장 가까운 정수를 나타내는 부동 소수점 값을 반환합니다.  중간 값은 부동 소수점 반올림 모드의 설정에 상관없이 0 이상의 정수 값으로 표시됩니다.  반환되는 오류가 없습니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
  
## 설명  
 C\+\+가 오버로딩을 허용하기 때문에, `float`와`long double`값을 사용하고 반환하는 `round`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `round`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`round`, `roundf`, `roundl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_round.c  
// Build with: cl /W3 /Tc crt_round.c  
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
  
   printf("round(%f) is %.0f\n", x, round(x));  
   printf("round(%f) is %.0f\n", -x, round(-x));  
   printf("roundf(%f) is %.0f\n", y, roundf(y));  
   printf("roundf(%f) is %.0f\n", -y, roundf(-y));  
   printf("roundl(%Lf) is %.0Lf\n", z, roundl(z));  
   printf("roundl(%Lf) is %.0Lf\n", -z, roundl(-z));  
}  
```  
  
  **round\(2.499999\)는 2입니다.**  
**round\(\-2.499999\)는 \-2입니다.**  
**roundf\(2.800000\)는 3입니다.**  
**roundf\(\-2.800000\)는 \-3입니다.**  
**roundl\(2.500000\)은 3입니다.**  
**roundl\(\-2.500000\)은 \-3입니다.**   
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
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)