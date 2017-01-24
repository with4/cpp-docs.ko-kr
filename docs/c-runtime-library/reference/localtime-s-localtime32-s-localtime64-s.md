---
title: "localtime_s, _localtime32_s, _localtime64_s | Microsoft Docs"
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
  - "_localtime64_s"
  - "_localtime32_s"
  - "localtime_s"
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
  - "_localtime32_s"
  - "localtime32_s"
  - "localtime_s"
  - "localtime64_s"
  - "_localtime64_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_localtime64_s 함수"
  - "localtime32_s 함수"
  - "_localtime32_s 함수"
  - "localtime64_s 함수"
  - "시간, 값 변환"
  - "localtime_s 함수"
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localtime_s, _localtime32_s, _localtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간 값으로 변환 하 고 현지 표준 시간대에 대 한 수정 합니다. 이 버전의 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
errno_t localtime_s(  
   struct tm* _tm,  
   const time_t *time   
);  
errno_t _localtime32_s(  
   struct tm* _tm,  
   const time32_t *time   
);  
errno_t _localtime64_s(  
   struct tm* _tm,  
   const _time64_t *time   
);  
```  
  
#### 매개 변수  
 `_tm`  
 입력 될 때까지 구조에 대 한 포인터입니다.  
  
 `time`  
 저장 된 시간에 대 한 포인터입니다.  
  
## 반환 값  
 성공 하면 0입니다. 반환 값은 오류가 발생 하는 경우 오류 코드는 합니다. 오류 코드는 Errno.h에서 정의 됩니다. 이러한 오류의 목록을 보려면 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.  
  
### 오류 조건  
  
|`_tm`|`time`|반환 값|값 `_tm`|잘못 된 매개 변수 처리기가 호출|  
|-----------|------------|----------|-------------|------------------------|  
|`NULL`|any|`EINVAL`|수정 안 됨|예|  
|하지 `NULL` \(올바른 메모리 포인트\)|`NULL`|`EINVAL`|\-1로 설정 하는 모든 필드|예|  
|하지 `NULL` \(올바른 메모리 포인트\)|보다 작거나 0 보다 크고 `_MAX__TIME64_T`|`EINVAL`|\-1로 설정 하는 모든 필드|아니요|  
  
 첫 번째 두 오류 상태를의 경우는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 `_localtime32_s` 함수 변환으로 저장 하는 시간을 [time\_t](../../c-runtime-library/standard-types.md) 값 및 형식의 구조에 결과 저장 `tm`합니다.`long` 값 `timer` 자정 이후 경과 된 초를 나타냅니다 \(00: 00:00\), 1970 년 1 월 1 일 UTC입니다. 이 값에서 가져온 일반적으로 `time` 함수입니다.  
  
 `_localtime32_s` 사용자는 먼저 전역 환경 변수를 설정 하는 경우 현지 표준 시간대에 대 한 수정 `TZ`합니다. 때 `TZ` 설정 되어 다른 세 가지 환경 변수 \(`_timezone`, `_daylight`, 및 `_tzname`\)도 자동으로 설정 됩니다. 하는 경우는 `TZ` 변수를 설정 하지 않으면 `localtime32_s` 제어판의 날짜\/시간 응용 프로그램에 지정 된 표준 시간대 정보를 사용 하려고 시도 합니다. 이 정보를 가져올 수 없으며 PST8PDT 태평양 표준 시간대를 의미를 기본적으로 사용 됩니다. 참조 [\_tzset](../../c-runtime-library/reference/tzset.md) 에 대 한 설명은 이러한 변수입니다.`TZ` Microsoft 확장 이며 ANSI 표준 정의의 일부가 아닌 `localtime`합니다.  
  
> [!NOTE]
>  대상 환경 일광 절약 시간이 적용 되는지 확인 하십시오.  
  
 `_localtime64_s`, 를 사용 하는 `__time64_t` 구조, 23시 59분: 59 까지의 3000 년 12 월 31 일 협정 세계시 \(UTC\)를 표시 해야 하는 날짜 허용 하는 반면 `_localtime32_s` 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다.  
  
 `localtime_s` 계산 되는 인라인 함수 인지 `_localtime64_s`, 및 `time_t` 같습니다 `__time64_t`합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면이로 인해 `localtime_s` 로 계산 `_localtime32_s`합니다. 응용 프로그램 2038 년 1 월 18 일 후 실패 하 고 64 비트 플랫폼에서 허용 되지 않으므로 때문에이 권장 되지 않습니다.  
  
 필드는 구조체 형식의 [tm](../../c-runtime-library/standard-types.md) 는 각각 다음 값을 저장 한 `int`합니다.  
  
 `tm_sec`  
 분 후 시간 \(초\) \(0\-59\).  
  
 `tm_min`  
 1 시간 후 분 \(0\-59\).  
  
 `tm_hour`  
 자정 이후의 시간 \(0\-23\).  
  
 `tm_mday`  
 날짜 \(1\-31\)입니다.  
  
 `tm_mon`  
 월 \(0\-11; 1 월 \= 0\).  
  
 `tm_year`  
 연도 \(1900\-현재 년\)입니다.  
  
 `tm_wday`  
 요일 \(0\-6; 일요일 \= 0\).  
  
 `tm_yday`  
 연간 일자 \(0\-365; 1 월 1 일 \= 0\).  
  
 `tm_isdst`  
 일광 절약 시간에 적용 된 경우, 양수 값 일광 절약 시간이 적용;에 없는 경우 0 일광 절약 시간의 상태 알 수 없는 경우 음수 값입니다. 하는 경우는 `TZ` 환경 변수가 설정 되어, C 런타임 라이브러리 간주 규칙 미국에 적합 한 일광 절약 시간 \(DST\)의 계산을 구현 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`localtime_s`|\<time.h\>|  
|`_localtime32_s`|\<time.h\>|  
|`_localtime64_s`|\<time.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_localtime_s.c  
/* This program uses _time64 to get the current time   
 * and then uses _localtime64_s() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
        char timebuf[26];  
        errno_t err;  
  
        // Get time as 64-bit integer.  
        _time64( &long_time );   
        // Convert to local time.  
        err = _localtime64_s( &newtime, &long_time );   
        if (err)  
        {  
            printf("Invalid argument to _localtime64_s.");  
            exit(1);  
        }  
        if( newtime.tm_hour > 12 )        // Set up extension.   
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime.tm_hour > 12 )        // Convert from 24-hour   
                newtime.tm_hour -= 12;    // to 12-hour clock.   
        if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime.tm_hour = 12;  
  
        // Convert to an ASCII representation.   
        err = asctime_s(timebuf, 26, &newtime);  
        if (err)  
        {  
           printf("Invalid argument to asctime_s.");  
           exit(1);  
        }  
        printf( "%.19s %s\n", timebuf, am_pm );  
}  
```  
  
## 샘플 출력  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## 해당 .NET Framework 항목  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)