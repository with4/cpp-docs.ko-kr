---
title: "localtime, _localtime32, _localtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_localtime64"
  - "_localtime32"
  - "localtime"
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
  - "localtime64"
  - "_localtime64"
  - "localtime32"
  - "localtime"
  - "_localtime32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "localtime32 함수"
  - "_localtime32 함수"
  - "_localtime64 함수"
  - "localtime64 함수"
  - "localtime 함수"
  - "시간, 값 변환"
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# localtime, _localtime32, _localtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간 값으로 변환 하 고 현지 표준 시간대에 대 한 수정 합니다. 이러한 함수의 더 안전한 버전은 사용할 수 있습니다. 참조 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)합니다.  
  
## 구문  
  
```  
struct tm *localtime(  
   const time_t *timer   
);  
struct tm *_localtime32(  
   const __time32_t *timer  
);  
struct tm *_localtime64(  
   const __time64_t *timer   
);  
```  
  
#### 매개 변수  
 `timer`  
 저장 된 시간에 대 한 포인터입니다.  
  
## 반환 값  
 구조 결과에 대 한 포인터를 반환 하거나 `NULL` 날짜 함수에 전달 하는 경우:  
  
-   전에 1970 년 1 월 1 일 자정입니다.  
  
-   03시 14분: 07 이후, 2038 년 1 월 19 일 UTC \(사용 하 여 `_time32` 및 `time32_t`\).  
  
-   23시 59분: 59 3000 년 12 월 31 일 UTC 이후 \(사용 하 여 `_time64` 및 `__time64_t`\).  
  
 `_localtime64`, 를 사용 하는 `__time64_t` 구조, 23시 59분: 59 까지의 3000 년 12 월 31 일 협정 세계시 \(UTC\)를 표시 해야 하는 날짜 허용 하는 반면 `_localtime32` 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다.  
  
 `localtime` 계산 되는 인라인 함수 인지 `_localtime64`, 및 `time_t` 같습니다 `__time64_t`합니다. 컴파일러가를 해석 하는 경우 `time_t`이전 32 비트로 `time_t`, 를 정의할 수 있습니다 `_USE_32BIT_TIME_T`합니다. 이렇게 하면이로 인해 `localtime` 로 계산 `_localtime32`합니다. 응용 프로그램 2038 년 1 월 18 일 후 실패 하 고 64 비트 플랫폼에서 허용 되지 않으므로 때문에이 권장 되지 않습니다.  
  
 필드는 구조체 형식의 [tm](../../c-runtime-library/standard-types.md) 는 각각 다음 값을 저장 한 `int`:  
  
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
 일광 절약 시간에 적용 된 경우, 양수 값 일광 절약 시간이 적용;에 없는 경우 0 일광 절약 시간의 상태 알 수 없는 경우 음수 값입니다. 하는 경우는 `TZ` 환경 변수는 설정, C 런타임 라이브러리 간주 규칙 미국에 적절 한 일광 절약 시간제가 \(DST\) 계산을 구현 합니다.  
  
## 설명  
 `localtime` 함수 변환으로 저장 하는 시간을 [time\_t](../../c-runtime-library/standard-types.md) 값 및 형식의 구조에 결과 저장 `tm`합니다.`long` 값 `timer` 자정 이후 경과 된 초를 나타냅니다 \(00: 00:00\), 1970 년 1 월 1 일 UTC입니다. 이 값에서 가져온 일반적으로 `time` 함수입니다.  
  
 32 비트 및 64 비트 버전 모두 `gmtime`, `mktime`, `mkgmtime`, 및 `localtime` 단일을 사용 하 여 모든 `tm` 변환을 위해 스레드당 구조입니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과 삭제합니다.  
  
 `localtime` 사용자는 먼저 전역 환경 변수를 설정 하는 경우 현지 표준 시간대에 대 한 수정 `TZ`합니다. 때 `TZ` 설정 되어 다른 세 가지 환경 변수 \(`_timezone`, `_daylight`, 및 `_tzname`\)도 자동으로 설정 됩니다. 하는 경우는 `TZ` 변수를 설정 하지 않으면 `localtime` 제어판의 날짜\/시간 응용 프로그램에 지정 된 표준 시간대 정보를 사용 하려고 시도 합니다. 이 정보를 가져올 수 없으며 PST8PDT 태평양 표준 시간대를 의미를 기본적으로 사용 됩니다. 참조 [\_tzset](../../c-runtime-library/reference/tzset.md) 에 대 한 설명은 이러한 변수입니다.`TZ` Microsoft 확장 이며 ANSI 표준 정의의 일부가 아닌 `localtime`합니다.  
  
> [!NOTE]
>  대상 환경 일광 절약 시간이 적용 되는지 확인 하십시오.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 `timer` 가 null 포인터 또는 타이머 값이 음수 이면 이러한 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 함수가 반환 `NULL` 설정 `errno` 를 `EINVAL`합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`localtime`|\<time.h\>|  
|`_localtime32`|\<time.h\>|  
|`_localtime64`|\<time.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_localtime.cpp  
// compile with: /W3  
/* This program uses _time64 to get the current time   
 * and then uses localtime64() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm *newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
  
        _time64( &long_time );           // Get time as 64-bit integer.  
                                         // Convert to local time.  
        newtime = _localtime64( &long_time ); // C4996  
        // Note: _localtime64 deprecated; consider _localetime64_s  
  
        if( newtime->tm_hour > 12 )        // Set up extension.  
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime->tm_hour > 12 )        // Convert from 24-hour  
                newtime->tm_hour -= 12;    //   to 12-hour clock.  
        if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime->tm_hour = 12;  
  
        char buff[30];  
        asctime_s( buff, sizeof(buff), newtime );  
        printf( "%.19s %s\n", buff, am_pm );  
}  
```  
  
```Output  
화요일 년 2 월 12 오전 10시 05분: 58  
```  
  
## 해당 .NET Framework 항목  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)