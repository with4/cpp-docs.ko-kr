---
title: "_ftime, _ftime32, _ftime64 | Microsoft Docs"
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
  - "_ftime64"
  - "_ftime"
  - "_ftime32"
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
  - "_ftime32"
  - "_ftime"
  - "_ftime64"
  - "ftime64"
  - "ftime"
  - "ftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ftime64 함수"
  - "_ftime64 함수"
  - "현재 시간"
  - "_ftime 함수"
  - "ftime 함수"
  - "_ftime32 함수"
  - "ftime32 함수"
  - "시간, 현재 가져오기"
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftime, _ftime32, _ftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 시간을 가져옵니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)를 참조하십시오.  
  
## 구문  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### 매개 변수  
 `timeptr`  
 `_timeb`,`__timeb32` 또는 `__timeb64` 구조체에 대한 포인터입니다.  
  
## 설명  
 `_ftime` 함수는 현재 현지 시간을 가져오고 `timeptr`*.* 으로 지정된 구조체에서 이것을 저장합니다. `_timeb`, `__timeb32`,그리고`__timeb64` 구조체는 SYS\\Timeb.h에서 정의됩니다.  그들은 다음 표에서 나열된 4개의 필드를 포함합니다.  
  
 `dstflag`  
 만약 현지에 섬머타임제가 적용된 경우 0이 아닙니다. \(섬머타임제가 결정되는 방법의 대한 설명은 [tzset](../../c-runtime-library/reference/tzset.md) 를 참조하세요.\)  
  
 `millitm`  
 초를 밀리초로 나눕니다.  
  
 `time`  
 셰게 협정시\(UTC\), 1970년 1월 1일 자정\(00:00:00\)이후 시간입니다.  
  
 `timezone`  
 UTC와 현지 시간 간에, westward 이동시간만큼 차이가 납니다.  `timezone` 의 값은 `_timezone` 전역변수의 값으로 설정됩니다. \( `_tzset`을 참조\)  
  
 `_ftime64` 는 `__timeb64` 구조체를 사용하고, \(UTC\) 3000년 12월 31일 23:59:59까지 표현할 수 있습니다. `_ftime32` 는 오직 \(UTC\) 2038년 1월 19일 03:14:07까지 표현할 수 있습니다.  1970년 1월 1일 자정은 모든 함수의 날짜 범위의 하한 값입니다.  
  
 `_ftime` 는 `_ftime64` 와 동일하고 `_timeb` 는 64비트 시간을 포함합니다.  `_USE_32BIT_TIME_T` 가 정의 되지 않는 한 이것은 사실입니다. 오랜 동작도 영향을 받습니다. `_ftime` 는 32비트 시간을 사용하고 `_timeb` 는 32비트 시간을 포함합니다.  
  
 `_ftime` 매개 변수의 유효성을 검사합니다.  `timeptr` 이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno`를 `EINVAL`로 설정합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_ftime`|\<sys\/types.h\> 및 \<sys\/timeb.h\>|  
|`_ftime32`|\<sys\/types.h\> 및 \<sys\/timeb.h\>|  
|`_ftime64`|\<sys\/types.h\> 및 \<sys\/timeb.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_ftime.c  
// compile with: /W3  
// This program uses _ftime to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime( &timebuffer ); // C4996  
   // Note: _ftime is deprecated; consider using _ftime_s instead  
  
   time1 = timebuffer.time;  
   millitm1 = timebuffer.millitm;  
   timezone1 = timebuffer.timezone;  
   dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
  **\(UTC\) 1970년 1월 1일 자정 이후의 시간 \(초\): 1051553334**  
**230밀리초**  
**UTC와 현지 시간 간격\(분\): 480**  
**일광 절약 시간 플래그 \(1은 일광 시간을 의미합니다\): 1**  
**시간은 2003년 4월 28일 \(월\) 11시08분54초 230입니다.**   
## 해당 .NET Framework 항목  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)