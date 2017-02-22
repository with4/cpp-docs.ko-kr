---
title: "exp, expf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "expf"
  - "exp"
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
  - "_expl"
  - "expf"
  - "exp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "지수 계산"
  - "expf 함수"
  - "지수 계산"
  - "exp 함수"
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# exp, expf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지수를 계산합니다.  
  
## 구문  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값.  
  
## 반환 값  
 `exp` 함수는 성공할 경우 부동 소수점 매개 변수 `x`의 지수 값을 반환합니다.  즉, 결과는 e의 `x` 제곱이며, 여기서 e는 자연 로그의 밑입니다.  오버플로우시, 함수는 INF \(무한대\)를 반환하며, 언더플로우시 `exp`는 0을 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± QNAN,IND|없음|\_DOMAIN|  
|± ∞|잘못된|\_DOMAIN|  
|x ≥ 7.097827e\+002|INEXACT\+OVERFLOW|오버플로가 발생했습니다.|  
|X ≤ \-7.083964e\+002|INEXACT\+UNDERFLOW|UNDERFLOW|  
  
 `exp` 스트리밍 SIMD 확장 2 \(SSE2\)을 사용하여구현을 했습니다.  SSE2 구현을 사용에서 제한과 정보에 대에 대해서는 [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) 를 참고하세요.  
  
## 설명  
 C\+\+ 오버 로딩을 허용하여 오버 로드인 `exp` 을 호출할 수 있습니다.  C 프로그램에서 `exp` 는 항상 2배를 사용하고 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`exp`, `expf`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
  **exp\( 2.302585 \) \= 10.000000**   
## 해당 .NET Framework 항목  
 [System::Math::Exp](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [\_CIexp](../../c-runtime-library/ciexp.md)