---
title: "log, logf, log10, log10f | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "log10f"
  - "logf"
  - "log10"
  - "log"
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
  - "logf"
  - "_log10l"
  - "log"
  - "_logl"
  - "log10f"
  - "log10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "로그 계산"
  - "log10f 함수"
  - "log10 함수"
  - "log 함수"
  - "logf 함수"
  - "로그"
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# log, logf, log10, log10f
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로그를 계산합니다.  
  
## 구문  
  
```  
  
      double log(  
   double x   
);  
float log(  
   float x  
);  // C++ only  
long double log(  
   long double x  
);  // C++ only  
float logf(  
   float x   
);  
double log10(  
   double x  
);  
float log10(  
   float x  
);  // C++ only  
long double log10(  
   long double x  
);  // C++ only  
float log10f (  
   float x  
);  
```  
  
#### 매개 변수  
 *x*  
 발견된 로그의 값입니다.  
  
## 반환 값  
 **log** 함수는 성공적인 경우 *x*의 자연 로그\(밑 e\) 값을 반환합니다.  log10 함수는 밑이 10인 로그값을 반환합니다.  *x*가 음수인 경우, 이러한 함수는 기본적으로 정의되지 않음을 반환합니다.  *x*가 0인 경우, INF\(무한대\)를 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± QNAN,IND|없음|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
|x \< 0|잘못된|\_DOMAIN|  
  
 **log** 및 `log10`은 스트리밍 SIMD 확장 2 \(SSE2\)을 사용하여 구현을 했습니다.  SSE2 구현을 사용에서 제한과 정보에 대에 대해서는 [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) 를 참고하세요.  
  
## 설명  
 C\+\+는 오버로딩을 허용하기 때문에 오버로드인 **log** 및 `log10`을 호출할 수 있습니다.  C 프로그램에서, **log** 및 `log10`는 항상 double을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**log**, `logf`, `log10`, `log10f`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_log.c  
/* This program uses log and log10  
 * to calculate the natural logarithm and  
 * the base-10 logarithm of 9,000.  
 */  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 9000.0;  
   double y;  
  
   y = log( x );  
   printf( "log( %.2f ) = %f\n", x, y );  
   y = log10( x );  
   printf( "log10( %.2f ) = %f\n", x, y );  
}  
```  
  
## Output  
  
```  
log( 9000.00 ) = 9.104980  
log10( 9000.00 ) = 3.954243  
```  
  
 수학적 관계를 사용하여 다른 밑에 대한 로그값을 생성합니다. 밑이 b인 a의 로그값 \=\= 자연 로그 \(a\) \/ 자연 로그 \(b\).  
  
```  
// logbase.cpp  
#include <math.h>  
#include <stdio.h>  
  
double logbase(double a, double base)  
{  
   return log(a) / log(base);  
}  
  
int main()  
{  
   double x = 65536;  
   double result;  
  
   result = logbase(x, 2);  
   printf("Log base 2 of %lf is %lf\n", x, result);  
}  
```  
  
## Output  
  
```  
Log base 2 of 65536.000000 is 16.000000  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx)  
  
-   [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [\_CIlog](../../c-runtime-library/cilog.md)   
 [\_CIlog10](../../c-runtime-library/cilog10.md)