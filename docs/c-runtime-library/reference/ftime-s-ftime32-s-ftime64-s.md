---
title: "_ftime_s, _ftime32_s, _ftime64_s | Microsoft Docs"
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
  - "_ftime_s"
  - "_ftime64_s"
  - "_ftime32_s"
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
  - "_ftime_s"
  - "_ftime64_s"
  - "ftime_s"
  - "_ftime32_s"
  - "ftime32_s"
  - "ftime64_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ftime32_s 함수"
  - "ftime_s 함수"
  - "_ftime64_s 함수"
  - "현재 시간"
  - "ftime64_s 함수"
  - "시간, 현재 가져오기"
  - "_ftime_s 함수"
  - "_ftime32_s 함수"
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftime_s, _ftime32_s, _ftime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 시간을 가져옵니다. 이 버전의 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
errno_t _ftime_s(   
   struct _timeb *timeptr   
);  
errno_t _ftime32_s(   
   struct __timeb32 *timeptr   
);  
errno_t _ftime64_s(   
   struct __timeb64 *timeptr   
);  
```  
  
#### 매개 변수  
 `timeptr`  
 에 대 한 포인터는 `_timeb,``__timeb32`, 를 또는 `__timeb64` 구조입니다.  
  
## 반환 값  
 성공 시 0, 실패 하면 오류 코드가 있습니다.`timeptr`가 `NULL`인 경우 반환 값은 `EINVAL`입니다.  
  
## 설명  
 `_ftime_s` 함수 현재 현지 시간을 가져오고 가리키는 구조에 저장 `timeptr`*.*`_timeb,``__timeb32`,및`__timeb64` 구조체 SYS\\Timeb.h에서 정의 됩니다. 다음 표에 나열 된 4 개의 필드를 포함 합니다.  
  
 `dstflag`  
 일광 절약 시간에서 실행 되는 현지 표준 시간대에 대 한 0이 아닌 지정 합니다. \(참조 [\_tzset](../../c-runtime-library/reference/tzset.md) 일광 절약 시간을 확인 하는 방법에 대 한.\)  
  
 `millitm`  
 초의 소수 \(밀리초\)입니다.  
  
 `time`  
 자정 이후의 초 단위 시간 \(00: 00:00\), 1970 년 1 월 1 일 협정 세계시 \(UTC\)입니다.  
  
 `timezone`  
 차이 \(분\), UTC와 현지 시간 사이의 westward를 이동 합니다. 값 `timezone` 전역 변수의 값에서 설정 `_timezone` \(참조 `_tzset`\).  
  
 `_ftime64_s`, 를 사용 하는 `__timeb64` 구조, 파일 작성 날짜 23시 59분: 59 까지의 3000 년 12 월 31 일 UTC 표현할 수를 허용 하는 반면 `_ftime32_s` 만 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다. 자정 1970 년 1 월 1 일에 이러한 모든 함수에 대 한 날짜 범위의 하한값입니다.  
  
 `_ftime_s` 에 해당 `_ftime64_s` 및 `_timeb` 64 비트 시간을 포함 합니다. 그렇습니다 하지 않는 한 \_`USE_32BIT_TIME_T` 정의 된 이전 동작이 적용 되는 경우; \_`ftime_s` 32 비트 시간을 사용 하 고 `_timeb` 32 비트 시간을 포함 합니다.  
  
 `_ftime_s` 해당 매개 변수의 유효성을 검사 합니다. 으로 null 포인터를 전달 하는 경우 `timeptr`, 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수를 설정 하는 실행을 계속 허용 되는 경우 `errno` 를 `EINVAL`합니다.  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`_ftime_s`|\< sys\/types.h \> 및 \< sys\/timeb.h \>|  
|`_ftime32_s`|\< sys\/types.h \> 및 \< sys\/timeb.h \>|  
|`_ftime64_s`|\< sys\/types.h \> 및 \< sys\/timeb.h \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_ftime64_s.c  
// This program uses _ftime64_s to obtain the current  
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
  
   _ftime64_s( &timebuffer );  
  
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
  
```Output  
1970 년 1 월 1 일 (UTC), 자정부터 경과 시간 (초): 1051553334 시간 (밀리초): UTC와 현지 시간 사이의 230 분: 480 일광 절약 시간 (일광 절약 시간이 적용 중인 1 의미) 플래그: 1 시간은 4 월 28 일 월요일 11:08:54.230 2003  
```  
  
## 해당 .NET Framework 항목  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)