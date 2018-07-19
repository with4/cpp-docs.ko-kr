---
title: localtime_s, _localtime32_s, _localtime64_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs:
- C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 513bfe5baa16c9cae5052da084c65f580aad7f2e
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255810"
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s

변환는 **time_t** 시간 값에는 **tm** 구조체와 현지 표준 시간대에 대 한 수정 합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t localtime_s(
   struct tm* const tmDest,
   time_t const* const sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   __time32_t const* sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   __time64_t const* sourceTime
);
```

### <a name="parameters"></a>매개 변수

*tmDest*<br/>
입력할 시간 구조체에 대한 포인터입니다.

*sourceTime*<br/>
저장된 시간에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 이러한 오류의 목록은 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*tmDest*|*sourceTime*|반환 값|값을 *tmDest*|잘못된 매개 변수 처리기 호출|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|모두|**EINVAL**|수정 안 됨|예|
|하지 **NULL** (올바른 메모리를 가리킴)|**NULL**|**EINVAL**|모든 필드가 -1로 설정됨|예|
|하지 **NULL** (올바른 메모리를 가리킴)|보다 작거나 0 보다 크고 **_MAX__TIME64_T**|**EINVAL**|모든 필드가 -1로 설정됨|아니요|

처음 두 오류 조건의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다. 실행을 계속 허용 된, 이러한 함수 설정 **errno** 를 **EINVAL** 다음 다시 돌아와 **EINVAL**합니다.

## <a name="remarks"></a>설명

**_localtime32_s** 함수 변환으로 저장 하는 한 번은 [time_t](../../c-runtime-library/standard-types.md) 값 형식의 구조에 결과 저장 하 고 [tm](../../c-runtime-library/standard-types.md)합니다. **긴** 값 *sourceTime* 자정 이후 경과 된 초를 나타냅니다 (00: 00:00), 1970 년 1 월 1 일 UTC입니다. 이 값에서 가져온 일반적으로 [시간](time-time32-time64.md) 함수입니다.

**_localtime32_s** 사용자 먼저 전역 환경 변수를 설정 하는 경우 현지 표준 시간대에 대 한 수정 **TZ**합니다. 때 **TZ** 설정 되어 다른 세 가지 변수 (**_timezone**, **_daylight**, 및 **_tzname**)도 자동으로 설정 됩니다. 경우는 **TZ** 변수를 설정 하지 않으면 **localtime32_s** 제어판의 날짜/시간 응용 프로그램에 지정 된 표준 시간대 정보를 사용 하려고 시도 합니다. 이 정보를 가져올 수 없으면 기본적으로 태평양 표준 시간대를 의미하는 PST8PDT가 사용됩니다. 이러한 변수에 대한 설명은 [_tzset](tzset.md)을 참조하세요. **TZ** Microsoft 확장 이며 ANSI 표준 정의의 일부가 아닌 **localtime**합니다.

> [!NOTE]
> 대상 환경에서는 일광 절약 시간이 적용되는지 확인해야 합니다.

**_localtime64_s**를 사용 하 여 **__time64_t** 구조을 사용 하면 날짜 23시 59분: 59 까지의 1 월 18 일 3001, 협정 세계시 (UTC)를 표현할 수 있지만 **_localtime32_s** 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다.

**localtime_s** 계산 되는 인라인 함수 인지 **_localtime64_s**, 및 **time_t** 같습니다 **__time64_t**합니다. 컴파일러가 해석 하도록 하는 경우 **time_t** 이전 32 비트로 **time_t**를 정의할 수 있습니다 **_USE_32BIT_TIME_T**합니다. 이렇게 하면이로 인해 **localtime_s** 로 평가 되려면 **_localtime32_s**합니다. 2038년 1월 18일 이후에는 응용 프로그램에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.

필드는 구조체 형식의 [tm](../../c-runtime-library/standard-types.md) 각각 나타내는 다음 값을 저장 한 **int**합니다.

|필드|설명|
|-|-|
|**tm_sec**|초 후 1 분 (0-59).|
|**tm_min**|분 후에 시간 (0-59).|
|**tm_hour**|자정 이후의 시간 (0-23).|
|**tm_mday**|날짜 (1-31)입니다.|
|**tm_mon**|월 (0-11; 1 월 = 0).|
|**tm_year**|연도(현재 연도 - 1900).|
|**tm_wday**|요일 (0-6; 일요일 = 0).|
|**tm_yday**|연간 일자 (0-365; 1 월 1 일 = 0).|
|**tm_isdst**|일광 절약 시간이 적용되면 양수, 일광 절약 시간이 적용되지 않으면 0, 일광 절약 시간의 상태를 알 수 없으면 음수입니다.|

경우는 **TZ** 환경 변수는 설정, C 런타임 라이브러리 간주 규칙 미국에 적합 한 일광 절약 시간제 (DST)의 계산 구현을 위한 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<ctime > 또는 \<. h >|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

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
        newtime.tm_hour -= 12;        // to 12-hour clock.
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

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
