---
title: "_mkgmtime, _mkgmtime32, _mkgmtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mkgmtime32"
  - "_mkgmtime64"
  - "_mkgmtime"
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
  - "_mkgmtime64"
  - "mkgmtime32"
  - "_mkgmtime32"
  - "mkgmtime"
  - "mkgmtime64"
  - "_mkgmtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mkgmtime32 함수"
  - "시간 함수"
  - "mkgmtime 함수"
  - "_mkgmtime 함수"
  - "시간 변환"
  - "mkgmtime64 함수"
  - "_mkgmtime64 함수"
  - "_mkgmtime32 함수"
  - "시간, 변환"
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _mkgmtime, _mkgmtime32, _mkgmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가 나타내는 UTC 시간으로 변환는 `tm``struct` UTC 시간으로 표시는 `time_t` 유형입니다.  
  
## 구문  
  
```  
  
time_t _mkgmtime(  
   struct tm*   
timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm*   
timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm*   
timeptr  
);  
  
```  
  
#### 매개 변수  
 `timeptr`  
 UTC 시간으로에 대 한 포인터는 `struct``tm` 변환 합니다.  
  
## 반환 값  
 형식의 수량 `__time32_t` 또는 `__time64_t` 1970 년 1 월 1 일 utc \(협정 세계시\)로 자정 이후 경과 된 시간 \(초\)의 수를 나타내는 합니다. 날짜 범위를 벗어나면 \(설명 부분 참조\) 또는 입력을 올바른 시간으로 해석할 수 없는, 반환 값은\-1입니다.  
  
## 설명  
 `_mkgmtime32` 및 `_mkgmtime64` 함수는 UTC 시간을 변환 된 `__time32_t` 또는 `__time64_t` UTC 시간을 나타내는 형식입니다. UTC 시간을 현지 시간으로 변환 하려면 사용 `mktime`, `_mktime32`, 및 `_mktime64` 대신 합니다.  
  
 `_mkgmtime` 계산 되는 인라인 함수 이며 `_mkgmtime64`, 및 `time_t` 같습니다 `__time64_t`합니다. 컴파일러가를 해석 하는 경우 `time_t`이전 32 비트로 `time_t`, 를 정의할 수 있습니다 `_USE_32BIT_TIME_T`합니다. 응용 프로그램은 2038 년 1 월 18 일 후 실패할 수 있으므로 권장 되지 않습니다 \(32 비트의 최대 범위 `time_t`\), 64 비트 플랫폼에서 전혀 되어서는 안 됩니다.  
  
 에 전달 하는 구조 시간 바뀝니다 다음과 같이 동일한 방식으로 변경 되는 `_mktime` 함수:는 `tm_wday` 및 `tm_yday` 필드의 값을 기반으로 하는 새 값으로 설정 되어 `tm_mday` 및 `tm_year`합니다.`tm` 구조 시간을 지정하면 `tm_isdst` 필드를 다음과 같이 설정합니다.  
  
-   0은 표준 시간이 적용 중임을 나타냅니다.  
  
-   0보다 큰 값은 일광 절약 시간이 적용 중임을 나타냅니다.  
  
-   0보다 작은 값은 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 계산하도록 합니다.  
  
 C 런타임 라이브러리 TZ 환경 변수를 사용 하 여 올바른 일광 절약 시간을 결정 합니다. TZ 설정 되어 있지 않으면 운영 체제 국가별 올바른 일광 절약 시간 동작 하 게 하려면 쿼리 됩니다.`tm_isdst`는 필수 필드입니다. 을 설정 하지 값 정의 되지 않습니다에서 반환 값과 `mktime` 는 예측할 수 없습니다.  
  
 범위는 `_mkgmtime32` 함수는 1970 년 1 월 1 일 자정부터 23시 59분: 59 2038 년 1 월 18 일 UTC에 UTC입니다. 범위의 `_mkgmtime64` UTC 23시 59분: 59, 3000 년 12 월 31 일에 1970 년 1 월 1 일 자정 UTC에서 됩니다. 범위를 벗어난 날짜는 반환 값 – 1 발생합니다. 범위의 `_mkgmtime` 여부에 따라 달라 집니다 `_USE_32BIT_TIME_T` 정의 됩니다. 범위는의 \(기본값\) 정의 되지 않은 경우 `_mkgmtime64`고, 그렇지 않으면 32 비트 범위 제한의 범위는 `_mkgmtime32`합니다.  
  
 `gmtime` 및 `localtime` 변환에 대 한 단일 정적으로 할당 된 버퍼를 사용 합니다. 이 버퍼를 제공 하는 경우 `mkgmtime`, 이전 내용이 소멸 됩니다.  
  
## 예제  
  
```  
// crt_mkgmtime.c  
#include <stdio.h>  
#include <time.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t now, mytime, gmtime;  
    char buff[30];  
  
    time( & now );  
  
    _localtime64_s( &t1, &now );  
    _gmtime64_s( &t2, &now );  
  
    mytime = mktime(&t1);  
    gmtime = _mkgmtime(&t2);  
  
    printf("Seconds since midnight, January 1, 1970\n");  
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);  
  
    /* Use asctime_s to display these times. */  
  
    _localtime64_s( &t1, &mytime );  
    asctime_s( buff, sizeof(buff), &t1 );  
    printf( "Local Time: %s\n", buff );  
  
    _gmtime64_s( &t2, &gmtime );  
    asctime_s( buff, sizeof(buff), &t2 );  
    printf( "Greenwich Mean Time: %s\n", buff );  
  
}  
```  
  
## 샘플 출력  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 다음 예제는 요일 및 연간 일자의 계산 된 값으로 불완전 한 구조체 채우는 방법을 보여 줍니다.  
  
```  
// crt_mkgmtime2.c  
#include <stdio.h>  
#include <time.h>  
#include <memory.h>  
  
int main()  
{  
    struct tm t1, t2;  
    time_t gmtime;  
    char buff[30];  
  
    memset(&t1, 0, sizeof(struct tm));  
    memset(&t2, 0, sizeof(struct tm));  
  
    t1.tm_mon = 1;  
    t1.tm_isdst = 0;  
    t1.tm_year = 103;  
    t1.tm_mday = 12;  
  
    // The day of the week and year will be incorrect in the output here.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
    gmtime = _mkgmtime(&t1);  
  
    // The correct day of the week and year were determined.  
    asctime_s( buff, sizeof(buff), &t1);  
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",  
            buff, t1.tm_yday );  
  
}  
```  
  
## 출력  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)