---
title: "frexp | Microsoft Docs"
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
  - "frexp"
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
  - "frexp"
  - "_frexpl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_frexpl 함수"
  - "지수, 부동 소수점 숫자"
  - "부동 소수점 함수, 가수 및 지수"
  - "frexp 함수"
  - "frexpl 함수"
  - "가수, 부동 소수점 변수"
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# frexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가수와 지수의 부동 소수점 숫자를 가져옵니다.  
  
## 구문  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값.  
  
 `expptr`  
 저장된 정수의 지수에 대한 포인터입니다.  
  
## 반환 값  
 `frexp`는 가수를 반환합니다.  만일 `x` 가 0인 경우, 이 함수는 가수와 지수 모두에 대해 0을 반환합니다.  만일 `expptr` 가 `NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 보여주는 것처럼 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 로 설정하고 0을 반환합니다.  
  
## 설명  
 `frexp` 함수는 `m` 의 절대값은 0.5 보다 크거나 같고 1.0 보다 작은 `x` \= `m`\*2<sup>n</sup>처럼, 부동 소수점 값\(`x`\)를 가수\(`m`\)와 지수\(`n`\)로 분해합니다.  정수의 지수 `n` 이 `expptr` 로 지정된 위치에 저장됩니다.  
  
 C\+\+ 오버 로딩을 허용하여 오버 로드인 `frexp` 을 호출할 수 있습니다.  C 프로그램에서, `frexp` 는 double형식을 받고 정수형과 double 데이터 형식을 반환 합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`frexp`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
  **frexp \(16.400000, &n\) \= 0.512500, n \= 5**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)