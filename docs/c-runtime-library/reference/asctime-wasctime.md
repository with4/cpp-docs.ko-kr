---
title: "asctime, _wasctime | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wasctime"
  - "asctime"
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
  - "_tasctime"
  - "asctime"
  - "_wasctime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tasctime 함수"
  - "_wasctime 함수"
  - "asctime 함수"
  - "tasctime 함수"
  - "시간 구조체 변환"
  - "시간, 변환"
  - "wasctime 함수"
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# asctime, _wasctime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`tm` 시간 구조를 문자 문자열로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)를 참조하십시오.  
  
## 구문  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### 매개 변수  
 `timeptr`  
 시간\/날짜 구조체  
  
## 반환 값  
 `asctime` 는 문자열 결과에 대한 포인터를 반환합니다; `_wasctime` 는 와이드 문자 문자열 결과에 대한 포인터를 반환합니다.  반환되는 값에 대한 오류가 없습니다.  
  
## 설명  
 이러한 기능의 더 안전한 버전을 사용할 수 있습니다; [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)를 참조하세요.  
  
 `asctime` 함수는 구조체로 저장 된 시간을 문자 문자열로 변환합니다.  `timeptr` 값은 항상 `gmtime` 또는 `localtime` 을 호출함으로써 얻을 수 있고 이것은 모두 TIME.H에서 정의된 `tm` 구조체에 대한 포인터를 반환합니다.  
  
|timeptr 멤버|값|  
|----------------|-------|  
|`tm_hour`|Hours since midnight \(0–23\)|  
|`tm_isdst`|양의 경우 일광 절약 시간제를 적용 합니다. 일광 적얄 시간제가 효과가 없으면 0을 반환합니다. 일광 절약 시간을 알 수 없으면 음수를 반환합니다.  C 런타임 라이브러리는 일광 절약 시간제\(DST\)의 계산을 실행하는데 미국의 규칙을 사용한다고 가정합니다.|  
|`tm_mday`|Day of month \(1–31\)|  
|`tm_min`|Minutes after hour \(0–59\)|  
|`tm_mon`|Month \(0–11; January \= 0\)|  
|`tm_sec`|Seconds after minute \(0–59\)|  
|`tm_wday`|Day of week \(0–6; Sunday \= 0\)|  
|`tm_yday`|Day of year \(0–365; January 1 \= 0\)|  
|`tm_year`|Year \(current year minus 1900\)|  
  
 변환 된 문자열은 현지 표준 시간대 설정에 따라 조정할 수 있습니다.  현지 시간 구성에 대한 자세한 정보는 [time](../../c-runtime-library/reference/time-time32-time64.md) 을 참고하세요. 시간대 환경을 정의하는 정보와 전역 변수들에 대한 정보는 [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)과, [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 함수와 [\_tzset](../../c-runtime-library/reference/tzset.md) 함수를 참고하세요.  
  
 `asctime` 으로 생성된 문자열 결과는 정확히 26개의 문자들을 포함하고 `Wed Jan 02 02:03:55 1980\n\0` 형식을 지닙니다.  24 시간제를 사용 합니다.  모든 필드 너비가 일정합니다.  줄 바꿈 문자 및 null 문자가 문자열의 마지막 두 자리를 차지 합니다.  `asctime` 는 반환 문자열로 지닌 단일, 정적으로 할당된 버퍼를 사용합니다.  이 함수를 호출할 때마다 이전 호출의 결과 삭제합니다.  
  
 `_wasctime` 는 `asctime` 의 와이드 문자 버전입니다.  `_wasctime` 및 `asctime` 는 동일하게 작동합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  만일 `timeptr` 이 null포인터인 경우, 또는 값의 범위를 넘어가는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 것처럼 잘못된 매개변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `NULL` 를 반환하고 `errno` 을 `EINVAL`으로 설정합니다.  
  
### Generic\-Text Routine Mapping  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`asctime`|\<time.h\>|  
|`_wasctime`|\<time.h\> or \<wchar.h\>|  
  
## 예제  
 이 프로그램은 `asctime` 함수를 사용하여 시스템 시간을 구조체 `newtime` 로 변환하고 출력에 대해 문자열 서식으로 변환하는 long 정수`aclock`에 배치 합니다.  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
  **현재 날짜 및 시간: 2002년 2월 3일 일요일 11:38:58**   
## 해당 .NET Framework 항목  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)