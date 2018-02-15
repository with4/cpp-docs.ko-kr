---
title: "clock | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- clock
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d56f29f1693fba1f4b455d8ae80ee38603e3a604
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="clock"></a>clock
호출 프로세스에서 사용하는 벽시계 시간을 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
clock_t clock( void );  
```  
  
## <a name="return-value"></a>반환 값  
프로세스 시작 시 CRT 초기화 이후 경과된 시간으로, 초당 `CLOCKS_PER_SEC` 단위로 측정됩니다. 경과된 시간을 사용할 수 없거나 경과된 시간이 `clock_t` 형식으로 기록될 수 있는 최대 양수 시간을 초과한 경우 함수가 `(clock_t)(-1)` 값을 반환합니다.   
  
## <a name="remarks"></a>설명  
`clock` 함수는 프로세스 시작 중 CRT 초기화 이후 경과된 벽시계 시간을 알려 줍니다. 이 함수는 ISO C를 엄격하게 준수하지는 않으며, 순 CPU 시간을 반환 값으로 지정합니다. CPU 시간을 가져오려면 Win32 [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223) 함수를 사용합니다. 경과된 시간을 초 단위로 확인하려면 `clock` 함수에서 반환한 값을 `CLOCKS_PER_SEC` 매크로로 나눕니다.  
  
충분한 시간을 가정하면 `clock`에서 반환한 값이 `clock_t`의 최대 양수 값을 초과할 수 있습니다. 프로세스가 더 길게 실행되면 `clock`에서 반환한 값은 ISO C99 표준(7.23.2.1) 및 ISO C11 표준(7.27.2.1)에 의해 지정된 대로 항상 `(clock_t)(-1)`입니다. Microsoft는 `clock_t`를 부호 있는 32비트 정수, `long`으로 구현하며 `CLOCKS_PER_SEC` 매크로가 1000으로 정의됩니다. 이렇게 하면 2147483.647초 또는 약 24.8일의 최대 `clock` 함수 반환 값이 제공됩니다. 이 기간보다 오랫동안 실행된 프로세스에서 `clock` 함수가 반환한 값은 사용하지 마세요. 64비트 `time` 함수 또는 Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) 함수를 사용하여 여러 해의 프로세스 경과 시간을 기록할 수 있습니다.  

## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`clock`|\<time.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_clock.c  
// This sample uses clock() to 'sleep' for three 
// seconds, then determines how long it takes  
// to execute an empty loop 600000000 times.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
// Pauses for a specified number of milliseconds.  
void do_sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
  
const long num_loops = 600000000L;

int main( void )  
{  
   long    i = num_loops;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "Time to do %ld empty loops is ", num_loops );  
   printf( "%2.3f seconds\n", duration );  
}  
```  
  
```Output  
Delay for three seconds  
Done!  
Time to do 600000000 empty loops is 1.354 seconds  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [difftime, _difftime32, _difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)