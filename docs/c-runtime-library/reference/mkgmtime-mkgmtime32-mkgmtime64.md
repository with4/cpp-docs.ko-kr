---
title: _mkgmtime, _mkgmtime32, _mkgmtime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
dev_langs: C++
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6353229aecc273daac03635f73761345171bd30e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64
`tm struct`로 표시되는 UTC 시간을 `time_t` 형식으로 표시되는 UTC 시간으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      time_t _mkgmtime(  
   struct tm* timeptr  
);  
__time32_t _mkgmtime32(  
   struct tm* timeptr  
);  
__time64_t _mkgmtime64(  
   struct tm* timeptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timeptr`  
 변환할 UTC 시간에 대한 포인터(`struct tm`)입니다.  
  
## <a name="return-value"></a>반환 값  
 1970년 1월 1일 자정 이후 경과된 UTC(협정 세계시) 형식의 시간(초)을 나타내는 `__time32_t` 또는 `__time64_t` 형식의 수량입니다. 날짜 범위를 벗어나면 (설명 부분 참조) 또는 입력 유효한 시간으로 해석할 수 없습니다, 반환 값은-1입니다.  
  
## <a name="remarks"></a>설명  
 `_mkgmtime32` 및 `_mkgmtime64` 함수는 UTC 시간을 UTC 형식의 시간을 나타내는 `__time32_t` 또는 `__time64_t` 형식으로 변환합니다. 현지 시간을 UTC 시간으로 변환하려면 `mktime`, `_mktime32` 및 `_mktime64`를 대신 사용합니다.  
  
 `_mkgmtime`은 `_mkgmtime64`로 계산되는 인라인 함수이며 `time_t`는 `__time64_t`와 동일합니다. 컴파일러에서 `time_t` 를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 하지만 날짜가 2038년 1월 18일(32비트 `time_t`의 최대 범위) 이후가 되면 응용 프로그램에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식 자체가 허용되지 않습니다.  
  
 전달되는 시간 구조는 `_mktime` 함수를 사용하는 경우 변경되는 것과 같은 방식으로 다음과 같이 변경됩니다. `tm_wday` 및 `tm_yday` 필드는 `tm_mday` 및 `tm_year`의 값에 따라 새 값으로 설정됩니다. `tm` 구조 시간을 지정하면 `tm_isdst` 필드를 다음과 같이 설정합니다.  
  
-   0은 표준 시간이 적용 중임을 나타냅니다.  
  
-   0보다 큰 값은 일광 절약 시간이 적용 중임을 나타냅니다.  
  
-   0보다 작은 값은 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 계산하도록 합니다.  
  
 C 런타임 라이브러리는 TZ 환경 변수를 사용하여 올바른 일광 절약 시간을 결정합니다. TZ가 설정되어 있지 않으면 운영 체제를 쿼리하여 올바른 국가별 일광 절약 시간 동작을 가져옵니다. `tm_isdst`는 필수 필드입니다. 이 필드를 설정하지 않으면 해당 값이 정의되지 않고 `mktime`의 반환 값을 예측할 수 없습니다.  
  
 `_mkgmtime32` 함수의 범위는 1970년 1월 1일 자정(UTC)에서 2038년 1월 18일 오후 11시 59분 59초(UTC)까지입니다. `_mkgmtime64`의 범위는 1970년 1월 1일 자정(UTC)에서 3000년 12월 31일 오후 11시 59분 59초(UTC)까지입니다. 범위를 벗어난 날짜는-1의 반환 값에 발생합니다. `_mkgmtime`의 범위는 `_USE_32BIT_TIME_T` 정의 여부에 따라 달라집니다. _USE_32BIT_TIME_T를 정의하지 않으면(기본값) 범위는 `_mkgmtime64`의 범위가 됩니다. 그렇지 않은 경우 범위는 `_mkgmtime32`의 32비트 범위로 제한됩니다.  
  
 `gmtime` 및 `localtime`은 변환을 위해 고정적으로 할당된 단일 버퍼를 사용합니다. 이 버퍼를 `mkgmtime`에 제공하면 이전 내용이 제거됩니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Seconds since midnight, January 1, 1970  
My time: 1171588492  
GM time (UTC): 1171588492  
  
Local Time: Thu Feb 15 17:14:52 2007  
  
Greenwich Mean Time: Fri Feb 16 01:14:52 2007  
```  
  
 다음 예제에서는 계산된 요일과 날짜 값을 사용하여 불완전한 구조체를 채우는 방법을 보여 줍니다.  
  
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
  
## <a name="output"></a>출력  
  
```  
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003  
 t.tm_yday = 0  
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003  
 t.tm_yday = 42  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)