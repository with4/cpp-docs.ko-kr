---
title: "_clear87, _clearfp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_clearfp"
  - "_clear87"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "clearfp"
  - "_clearfp"
  - "_clear87"
  - "clear87"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_clear87 함수"
  - "_clearfp 함수"
  - "clear87 함수"
  - "clearfp 함수"
  - "부동 소수점 상태 단어 지우기"
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _clear87, _clearfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 상태 단어를 가져오고 지웁니다.  
  
## 구문  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## 반환 값  
 반환된 값의 비트는 `_clear87` 또는 `_clearfp` 호출 전의 부동 소수점 상태를 나타냅니다.  `_clear87`에서 반환된 비트의 전체 정의를 보려면 Float.h를 참조하세요.  많은 수학 라이브러리 함수는 예기치 않은 결과를 포함하여 8087\/80287 상태 단어를 수정합니다.  부동 소수점 상태 단어의 알려진 상태 간에는 더 적은 부동 소수점 작업이 수행되므로 `_clear87` 및 `_status87` 반환 값의 신뢰성이 높아집니다.  
  
## 설명  
 `_clear87` 함수는 부동 소수점 상태 단어의 예외 플래그를 지우고 사용 중인 비트를 0으로 설정하고 상태 단어를 반환합니다.  부동 소수점 상태 단어는 8087\/80287 상태 단어와 8087\/80287 예외 처리기에서 검색한 기타 조건\(예: 부동 소수점 스택 오버플로 및 언더플로\)의 조합입니다.  
  
 `_clearfp`는 플랫폼 독립적이며 `_clear87` 루틴의 이식 가능한 버전입니다.  인텔\(x86\) 플랫폼에서는 `_clear87`과 동일하고 x64 및 ARM 플랫폼에 의해 지원됩니다.  부동 소수점 코드를 x64 및 ARM에 이식하려면 `_clearfp`를 사용하세요.  x86 플랫폼만 대상으로 하는 경우 `_clear87` 또는 `_clearfp`를 사용할 수 있습니다.  
  
 공용 언어 런타임은 기본 부동 소수점 정밀도만 지원하기 때문에 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 또는 `/clr:pure`를 사용하여 컴파일하는 경우 이러한 함수는 무시됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_clear87`|\<float.h\>|  
|`_clearfp`|\<float.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
  **Status: 0000 \- clear**  
**Status: 0003 \- inexact, underflow**  
**Status: 80000 \- denormal**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)