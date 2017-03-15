---
title: "floor, floorf, floorl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "floorf"
  - "floorl"
  - "floor"
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
  - "floor"
  - "floorl"
  - "_floorl"
  - "floorf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "바닥 값 계산"
  - "floor 함수"
  - "floorf 함수"
  - "floorl 함수"
ms.assetid: e9955f70-d659-414f-8050-132e13c8ff36
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# floor, floorf, floorl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값의 층을 계산합니다.  
  
## 구문  
  
```  
double floor(  
   double x  
);  
float floor(  
   float x   
); // C++ only  
long double floor(  
   long double x  
); // C++ only  
float floorf(  
   float x  
);  
long double floorl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값.  
  
## 반환 값  
 이 `floor` 함수는 `x` 이 같거나 더 적은 더 큰 정수를 표현하는 부동 소수점 값을 반환합니다.  반환되는 오류가 없습니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± QNAN,IND|없음|\_DOMAIN|  
  
 `floor` 스트리밍 SIMD 확장 2 \(SSE2\)을 사용하여구현을 했습니다.  정보 및 SSE2 구현을 사용하는 방법에 대한 제한 사항을 참조 하십시오. [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## 설명  
 C\+\+는 오버로드를 허용하기 때문에 `float` 및 `long double` 값을 사용하고 반환하는 `floor` 의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `floor`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`floor`, `floorf`, `floorl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_floor.c  
// This example displays the largest integers  
// less than or equal to the floating-point values 2.8  
// and -2.8. It then shows the smallest integers greater  
// than or equal to 2.8 and -2.8.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double y;  
  
   y = floor( 2.8 );  
   printf( "The floor of 2.8 is %f\n", y );  
   y = floor( -2.8 );  
   printf( "The floor of -2.8 is %f\n", y );  
  
   y = ceil( 2.8 );  
   printf( "The ceil of 2.8 is %f\n", y );  
   y = ceil( -2.8 );  
   printf( "The ceil of -2.8 is %f\n", y );  
}  
```  
  
  **2.8의 최소는 2.000000 입니다.**  
**\-2.8의 최소는 \-3.000000 입니다.**  
**2.8의 ceil은 3.000000 입니다.**  
**\-2.8의 ceil은 \-2.000000 입니다.**   
## 해당 .NET Framework 항목  
 [System::Math::Floor](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)