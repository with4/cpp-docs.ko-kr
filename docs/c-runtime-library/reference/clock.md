---
title: "clock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clock"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "clock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용된 프로세서 시간 계산"
  - "clock 함수"
  - "사용된 프로세서 시간"
  - "사용된 프로세서 시간, 계산"
  - "시간, 프로세서 시간 계산"
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# clock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

호출 프로세스에서 사용하는 벽시계 시간을 계산합니다.  
  
## 구문  
  
```  
clock_t clock( void );  
```  
  
## 반환 값  
 프로세스가 시작된 이후에 경과된 벽시계 시간\(`CLOCKS_PER_SEC`초 시간의 경과된 시간\)입니다.  경과된 시간을 사용할 수 없는 경우 함수는 `clock_t`로 캐스트된 \-1을 반환합니다.  
  
## 설명  
 `clock` 함수는 호출 프로세스에서 사용한 벽시계 시간을 알려 줍니다.  이 함수는 ISO C99를 엄격하게 준수하지는 않으며, 순 CPU 시간을 반환 값으로 지정합니다.  CPU 시간을 가져오려면 Win32 [GetProcessTimes](http://msdn.microsoft.com/library/windows/desktop/ms683223) 함수를 사용합니다.  
  
 타이머 틱은 1\/`CLOCKS_PER_SEC`초와 거의 동일합니다.  충분한 시간을 지정할 경우 `clock`에서 반환되는 값이 `clock_t`의 최대 양수 값을 초과하고 음수가 되거나, 최대 절대 값을 초과하고 롤오버될 수 있습니다.  214,748초 이상이나 약 59시간 동안 실행되는 프로세서의 총 경과 시간에는 이 값을 사용하지 마세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`clock`|\<time.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
```  
// crt_clock.c  
// This example prompts for how long  
// the program is to run and then continuously  
// displays the elapsed time for that period.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
void sleep( clock_t wait );  
  
int main( void )  
{  
   long    i = 6000000L;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   printf( "Time to do %ld empty loops is ", i );  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "%2.1f seconds\n", duration );  
}  
  
// Pauses for a specified number of milliseconds.  
void sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
```  
  
  **Delay for three seconds**  
**Done\!  Time to do 6000000 empty loops is 0.1 seconds**    
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [difftime, \_difftime32, \_difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)