---
title: "pow, powf, powl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "powl"
  - "pow"
  - "powf"
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
  - "powl"
  - "pow"
  - "_powl"
  - "powf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_powl 함수"
  - "지수 계산"
  - "지수 계산"
  - "지수"
  - "pow 함수"
  - "거듭제곱, 계산"
  - "powf 함수"
  - "powl 함수"
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# pow, powf, powl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 `x` 의 `y` 승을 계산합니다.  
  
## 구문  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### 매개 변수  
 `x`  
 Base.  
  
 `y`  
 지수.  
  
## 반환 값  
 이 `x`<sup>y</sup> 값을 반환합니다.  오버플로 또는 언더플로가 오류 메시지가 인쇄됩니다.  
  
|x 값과 y|Pow의 반환 값|  
|------------|---------------|  
|`x` \< \> 0 과 `y` \= 0.0|1|  
|`x` \= 0.0 과 `y` \= 0.0|1|  
|`x` \= 0.0 과 `y` \< 0|INF|  
  
## 설명  
 `pow` 는 2<sup>64</sup> \(예를 들자면, `1.0E100`\) 보다 큰 부동 소수점 값을 알아차리지 못합니다.  
  
 `pow` 스트리밍 SIMD 확장 2 \(SSE2\)을 사용하여구현을 했습니다.  정보 및 SSE2 구현을 사용하는 방법에 대한 제한 사항을 참조 하십시오. [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 C\+\+ 오버 로딩을 허용 하기 때문에, `pow`인 다양한 오버 로드 중 하나를 호출할 수 있습니다  C 프로그램에서 `pow` 는 항상 2개의 double 값을 사용하고 하나의 double 값을 반환합니다.  
  
 이 `pow(int, int)` 오버 로드를 사용할 수 없습니다.  이 오버 로드를 사용 하면 컴파일러가 C2668 낼 수 있습니다.  이 문제를 방지 하려면, 첫 번째 매개 변수를 `double`, `float`, 혹은 `long double` 으로 캐스팅합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`pow`, `powf`, `powl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## Output  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## 해당 .NET Framework 항목  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [\_CIpow](../../c-runtime-library/cipow.md)