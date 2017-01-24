---
title: "_status87, _statusfp, _statusfp2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_statusfp2"
  - "_statusfp"
  - "_status87"
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
  - "_statusfp2"
  - "_statusfp"
  - "statusfp2"
  - "_status87"
  - "status87"
  - "statusfp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "부동 소수점 함수, 상태 단어 가져오기"
  - "부동 소수점 숫자, 상태 단어"
  - "status87 함수"
  - "상태 단어, 부동 소수점 가져오기"
  - "statusfp 함수"
  - "_statusfp 함수"
  - "_statusfp2 함수"
  - "statusfp2 함수"
  - "_status87 함수"
  - "부동 소수점 함수"
  - "상태 단어"
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _status87, _statusfp, _statusfp2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 상태 단어를 가져옵니다.  
  
## 구문  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### 매개 변수  
 `px86`  
 X 87 부동 소수점 단위에서 주소 상태 라는 단어를 사용하여 채워집니다.  
  
 `pSSE2`  
 X 87 부동 소수점 단위에서 주소 상태 라는 단어를 사용하여 채워집니다.  
  
## 반환 값  
 `_status87` 및 `_statusfp` 에서, 반환되는 값의 비트 부동 소수점 상태를 나타냅니다.  파일에서 반환 되는 비트의 정의인 `_statusfp` FLOAT.H를 참조하십시오.  예기치 않은 결과로, 많은 수학 라이브러리 함수는 부동 소수점 상태 단어를 수정합니다.  최적화수 순서, 결합 및 부동 소수점 연산을 호출을 제거 `_status87`, `_statusfp`, 및 관련 함수입니다.  [\/Od\(디버그 비활성화\)](../../build/reference/od-disable-debug.md) 컴파일러 옵션 또는 [fenv\_access](../../preprocessor/fenv-access.md) 부동 소수점 연산 순서를 변경하는 최적화를 방지 하기 위해 pragma 지시문을 사용합니다.  `_clearfp` 및 `_statusfp` 로부터 값을 반환하고, 반환 매개 변수인 `_statusfp2` 를 알려진 상태인 부동 소수점 상태 단어의 부동 소수점 연산을 수행 하는 경우 신뢰할 수 있습니다.  
  
## 설명  
 `_statusfp` 함수는 부동 소수점 상태 단어를 가져옵니다.  상태 단어는 부동 소수점 프로세서 상태 및 기타 조건을 감지하여 부동 소수점 예외 처리기의 조합입니다.\-예를 들어, 부동 소수점 스택 오버플로 및 언더플로입니다.  상태 단어의 내용을 반환하기 전에 마스크 되지 않은 예외에 대해 확인합니다.  즉, 호출자가 예외가 보류 중인 내용을 의미합니다.  X 86 플랫폼에서, `_statusfp` 는 조합 x87 및 SSE2 부동 소수점 상태를 반환 합니다.  X 64 플랫폼에서 반환 되는 상태는 SSE의 MXCSR 상태를 기반으로 합니다.  ARM 플랫폼에서, `_statusfp` 는 FPSCR 레지스터의 상태를 반환 합니다.  
  
 `_statusfp` 는 `_status87` 의 휴대용 버전 독립 플렛폼입니다.  `_status87` 는 인텔 \(x86\) 플랫폼에서 동일하고 x 64와 ARM 플랫폼에 의해 지원 됩니다.  부동 소수점 코드는 모든 아키텍처에 이식 가능한지 확인하기위해, `_statusfp` 를 사용합니다.  X 86플랫폼만 대상으로 하는 경우, `_status87` 또는 `_statusfp` 를 사용할 수 있습니다.  
  
 x87 및 SSE2 부동 소수점 프로세서를 모두 가진 \(펜티엄 IV와 같은\)칩에 대한 `_statusfp2` 를 권고합니다.  `_statusfp2` 에 대해, 주소는 모두 x 87 또는 SSE2 부동 소수점 프로세서 부동 소수점 상태 단어를 사용함으로써 채워집니다.  X87 및 SSE2 부동 소수점 프로세서에서 지원 되는 칩에 대하여, EM\_AMBIGUOUS은 1로 설정됩니다. 왜냐하면, `_statusfp` 또는 `_controlfp` 는 액션 x 87 또는 SSE2 부동 소수점 상태 단어를 참조할 수 있기 때문에 모호할 경우입니다.  `_statusfp2` 함수는 x 86만 지원 플랫폼입니다.  
  
 이러한 함수에 대해서 유용하지 않은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 또는 `/clr:pure` 컴파일을 공용 언어 런타임 \(CLR\)만 기본 부동 소수점 정밀도를 지원하기 때문입니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
  **상태 \= 0x00000000\-지우기**  
**상태 \= 0x00000003\-정확 하지 않습니다, 언더플로**  
**상태 \= 0x00080003\-정확 하지 않습니다, 언더플로 비정상적인**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)