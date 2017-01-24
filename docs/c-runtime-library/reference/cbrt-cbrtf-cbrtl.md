---
title: "cbrt, cbrtf, cbrtl | Microsoft Docs"
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
  - "cbrt"
  - "cbrtf"
  - "cbrtl"
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
  - "cbrtl"
  - "cbrt"
  - "cbrtf"
dev_langs: 
  - "C++"
ms.assetid: ab51d916-3db2-4beb-b46a-28b4062cd33f
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cbrt, cbrtf, cbrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

세제곱근을 계산합니다.  
  
## 구문  
  
```  
double cbrt(    double x  ); float cbrt(    float x  );  // C++ only long double cbrt(    long double x );  // C++ only float cbrtf(    float x  ); long double cbrtl(    long double x );  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값  
  
## 반환 값  
 `cbrt` 함수는 `x`의 세제곱근을 반환합니다.  
  
|입력|SEH 예외|`_matherr` 예외|  
|--------|------------|-------------------|  
|± ∞, QNAN, IND|없음|없음|  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `float` 또는 `long double` 형식을 사용하는 `cbrt`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `cbrt`는 항상 `double`을 사용 및 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`cbrt`, `cbrtf`, `cbrtl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```c  
// crt_cbrt.c  
// Compile using: cl /W4 crt_cbrt.c  
// This program calculates a cube root.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double question = -64.64;  
   double answer;  
  
   answer = cbrt(question);  
   printf("The cube root of %.2f is %.6f\n", question, answer);  
}  
```  
  
  **\-64.64의 세제곱근은 \-4.013289입니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)