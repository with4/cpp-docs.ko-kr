---
title: "modf, modff, modfl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "modff"
  - "modf"
  - "modfl"
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
  - "modff"
  - "_modfl"
  - "modf"
  - "modfl"
  - "math/modf"
  - "math/modff"
  - "math/modfl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modf 함수"
  - "modff 함수"
  - "modfl 함수"
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# modf, modff, modfl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수 부분과 소수 부분에 부동 소수점 값을 분할합니다.  
  
## 구문  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### 매개 변수  
 *x*  
 부동 소수점 값입니다.  
  
 `intptr`  
 저장 된 정수 부분에 대 한 포인터입니다.  
  
## 반환 값  
 이 함수는 부호 있는 소수 부분이 반환 *x*합니다. 반환되는 오류가 없습니다.  
  
## 설명  
 `modf` 함수는 부동 소수점 값을 세분화 `x` 소수에 및와 같은 부호에 각각 정수 부분을 `x`합니다. 부호 있는 소수 부분 `x` 반환 됩니다. 정수 부분에는 부동 소수점 값으로 저장 됩니다. `intptr.`  
  
 `modf` 스트리밍 SIMD 확장 2 \(SSE2\)을 사용 하는 구현을 있습니다. 참조 [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) 내용과 SSE2 구현을 사용 하 여에 대 한 제한입니다.  
  
 C \+ \+ 오버 로드의 오버 로드를 호출할 수 있도록 허용 `modf` 및 반환 하 `float` 또는 `long double` 매개 변수입니다. C 프로그램에서 `modf` 항상 두 double 값을 사용 하 고 double 값을 반환 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`modf`, `modff`, `modfl`|C: \< h. h \><br /><br /> C \+ \+:, \< cmath \> 또는 \< h. h \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## 출력  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)