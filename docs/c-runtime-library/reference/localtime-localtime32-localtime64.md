---
title: "localtime, _localtime32, _localtime64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs:
- C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 6dcb9a6f0d7187722a769a28cfb624e4621c181f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64
시간 값을 변환하고 현지 표준 시간대에 맞게 수정합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `timer`  
 저장된 시간에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 구조체 결과에 대한 포인터를 반환하거나 함수에 전달된 날짜가 다음과 같은 경우 `NULL`을 반환합니다.  
  
-   1970년 1월 1일 자정 이전  
  
-   2038년 1월 19일 03:14:07(UTC) 이후(`_time32` 및 `time32_t` 사용)  
  
-   3000년 12월 31일 23:59:59(UTC) 이후(`_time64` 및 `__time64_t` 사용)  
  
 `__time64_t` 구조체를 사용하는 `_localtime64`는 3000년 12월 31일 23:59:59(UTC - 협정 세계시)까지 날짜를 표현할 수 있습니다. 반면, `_localtime32`는 2038년 1월 18일 23:59:59(UTC)까지의 날짜를 나타냅니다.  
  
 `localtime`는 `_localtime64`로 계산되는 인라인 함수이며 `time_t`는 `__time64_t`와 동일합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면 `localtime`가 `_localtime32`로 계산됩니다. 2038년 1월 18일 이후에는 응용 프로그램에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.  
  
 구조체 형식 [tm](../../c-runtime-library/standard-types.md)의 필드는 다음 값을 저장하며, 각 값은 `int`입니다.  
  
 `tm_sec`  
 초 후 1 분 (0-59).  
  
 `tm_min`  
 분 후에 시간 (0-59).  
  
 `tm_hour`  
 자정 이후의 시간 (0-23).  
  
 `tm_mday`  
 날짜 (1-31)입니다.  
  
 `tm_mon`  
 월 (0-11; 1 월 = 0).  
  
 `tm_year`  
 연도(현재 연도 - 1900).  
  
 `tm_wday`  
 요일 (0-6; 일요일 = 0).  
  
 `tm_yday`  
 연간 일자 (0-365; 1 월 1 일 = 0).  
  
 `tm_isdst`  
 일광 절약 시간이 적용되면 양수, 일광 절약 시간이 적용되지 않으면 0, 일광 절약 시간의 상태를 알 수 없으면 음수입니다. `TZ` 환경 변수가 설정된 경우 C 런타임 라이브러리에서는 DST(일광 절약 시간) 계산을 구현하기 위해 미국에 적절한 규칙이 사용된다고 가정합니다.  
  
## <a name="remarks"></a>설명  
 `localtime` 함수는 [time_t](../../c-runtime-library/standard-types.md) 값으로 저장된 시간을 변환하고 그 결과를 `tm` 형식의 구조체에 저장합니다. `long` 값 `timer`는 1970년 1월 1일 자정(00:00:00)(UTC) 이후 경과된 초를 나타냅니다. 이 값은 일반적으로 `time` 함수에서 가져옵니다.  
  
 `gmtime`, `mktime`, `mkgmtime` 및 `localtime`의 32비트 및 64비트 버전은 모두 변환을 위해 스레드당 단일 `tm` 구조체를 사용합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.  
  
 `localtime`은 사용자가 먼저 전역 환경 변수 `TZ`를 설정한 경우 현지 표준 시간대에 맞게 수정됩니다. `TZ`를 설정하면 세 가지 다른 환경 변수(`_timezone`, `_daylight` 및 `_tzname`)도 자동으로 설정됩니다. `TZ` 변수를 설정하지 않으면 `localtime`은 제어판의 날짜/시간 응용 프로그램에 지정된 표준 시간대 정보를 사용하려고 시도합니다. 이 정보를 가져올 수 없으면 기본적으로 태평양 표준 시간대를 의미하는 PST8PDT가 사용됩니다. 이러한 변수에 대한 설명은 [_tzset](../../c-runtime-library/reference/tzset.md)을 참조하세요. `TZ`는 Microsoft 확장이며 `localtime`의 ANSI 표준 정의의 일부가 아닙니다.  
  
> [!NOTE]
>  대상 환경에서는 일광 절약 시간이 적용되는지 확인해야 합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `timer`가 null 포인터이거나 timer 값이 음수인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이 함수는 `NULL`을 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`localtime`|\<time.h>|  
|`_localtime32`|\<time.h>|  
|`_localtime64`|\<time.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
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
Tue Feb 12 10:05:58 AM  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
