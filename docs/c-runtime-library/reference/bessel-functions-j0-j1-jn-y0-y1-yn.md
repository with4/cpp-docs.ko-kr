---
title: "Bessel 함수: _j0, _j1, _jn, _y0, _y1, _yn | Microsoft Docs"
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
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
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
  - "c.bessel"
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Bessel 함수"
  - "_j0 함수"
  - "_j1 함수"
  - "_jn 함수"
  - "_y0 함수"
  - "_y1 함수"
  - "_yn 함수"
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Bessel 함수: _j0, _j1, _jn, _y0, _y1, _yn
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

첫 번째 또는 두 번째 종류의 Bessel 함수를 0, 1 또는 n 순서로 계산합니다. The Bessel 함수는 일반적으로 전자기파 이론의 수학에 사용됩니다.  
  
## 구문  
  
```  
double _j0(   
   double x   
);  
double _j1(   
   double x   
);  
double _jn(   
   int n,  
   double x   
);  
double _y0(   
   double x   
);  
double _y1(   
   double x   
);  
double _yn(   
   int n,  
   double x   
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
 `n`  
 Bessel 함수의 정수 순서입니다.  
  
## 반환 값  
 이러한 각 루틴은 `x`의 Bessel 함수를 반환합니다.`x`가 `_y0`, `_y1` 또는 `_yn` 함수에서 음수이면 루틴은 `errno`를 `EDOM`으로 설정하고, `_DOMAIN` 오류 메시지를 `stderr`에 출력하고, `_HUGE_VAL`을 반환합니다.`_matherr`을 사용하여 오류 처리를 수정할 수 있습니다.  
  
## 설명  
 `_j0`, `_j1` 및 `_jn` 루틴은 첫 번째 종류의 Bessel 함수를 각각 0, 1, n의 순서로 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
  
 `_y0`, `_y1` 및 `_yn` 루틴은 두 번째 종류의 Bessel 함수를 각각 0, 1, n의 순서로 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
|± 0|`ZERODIVIDE`|`_SING`|  
|&#124;x&#124;\<0.0|`INVALID`|`_DOMAIN`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|\<cmath\> \(C\+\+\), \<math.h\> \(C, C\+\+\)|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
```  
// crt_bessel1.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.387;  
   int n = 3, c;  
  
   printf( "Bessel functions for x = %f:\n", x );  
   printf( " Kind   Order  Function     Result\n\n" );  
   printf( " First  0      _j0( x )     %f\n", _j0( x ) );  
   printf( " First  1      _j1( x )     %f\n", _j1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );  
   printf( " Second 0      _y0( x )     %f\n", _y0( x ) );  
   printf( " Second 1      _y1( x )     %f\n", _y1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );  
}  
```  
  
```Output  
Bessel functions for x = 2.387000: Kind   Order  Function     Result First  0      _j0( x )     0.009288 First  1      _j1( x )     0.522941 First  2      _jn( 2, x )  0.428870 First  3      _jn( 3, x )  0.195734 First  4      _jn( 4, x )  0.063131 Second 0      _y0( x )     0.511681 Second 1      _y1( x )     0.094374 Second 2      _yn( 2, x )  -0.432608 Second 3      _yn( 3, x )  -0.819314 Second 4      _yn( 4, x )  -1.626833  
```  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)