---
title: _ftime_s, _ftime32_s, _ftime64_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
dev_langs:
- C++
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a23b31fb88b60b05e587bf62ab07ec7e72de869
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s, _ftime32_s, _ftime64_s

현재 시간을 가져옵니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _ftime_s( struct _timeb *timeptr );
errno_t _ftime32_s( struct __timeb32 *timeptr );
errno_t _ftime64_s( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>매개 변수

*timeptr*<br/>
에 대 한 포인터는 **_timeb**, **__timeb32**, 또는 **__timeb64** 구조입니다.

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드. 경우 *timeptr* 은 **NULL**, 반환 값은 **EINVAL**합니다.

## <a name="remarks"></a>설명

**_ftime_s** 함수는 현재 현지 시간을 가져오고에서 가리키는 구조에 저장 *timeptr*합니다. **_timeb**, **__timeb32**, 및 **__timeb64** 구조 SYS\Timeb.h에 정의 됩니다. 구조체에는 다음 표에 나와 있는 4개 필드가 포함됩니다.

|필드|설명|
|-|-|
|**dstflag**|현지 시간대에 현재 일광 절약 시간이 적용된 경우 0이 아닌 값. 일광 절약 시간을 결정하는 방법에 대한 자세한 내용은 [_tzset](tzset.md)를 참조하세요.|
|**millitm**|1초 미만의 시간(밀리초)입니다.|
|**time**|1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후의 시간(초)입니다.|
|**timezone**|서쪽으로 이동할 경우 UTC와 현지 시간 사이의 차이(분)입니다. 값 **표준 시간대** 전역 변수의 값에서 설정 **_timezone** (참조 **_tzset**).|

**_ftime64_s** 함수를 사용 하 여 **__timeb64** 구조을 사용 하면 파일을 만든 날짜와 23시 59분: 59 까지의 3000 년 12 월 31 일, UTC 표현할 수 있지만 **_ftime32_s** 만 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다. 1970년 1월 1일 자정은 이러한 모든 함수에 대한 날짜 범위의 하한입니다.

**_ftime_s** 함수는 동일 **_ftime64_s**, 및 **_timeb** 하지 않는 한 64 비트 시간을 포함 합니다. **_USE_32BIT_TIME_T** 은 정의 된 경우 이전 동작이 적용 됩니다. **_ftime_s** 32 비트 시간을 사용 하 고 **_timeb** 32 비트 시간을 포함 합니다.

**_ftime_s** 해당 매개 변수의 유효성을 검사 합니다. Null 포인터도 전달 되 면 *timeptr*의 설명 대로 잘못 된 매개 변수 처리기를 호출 하는 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_ftime_s**|\<sys/types.h> 및 \<sys/timeb.h>|
|**_ftime32_s**|\<sys/types.h> 및 \<sys/timeb.h>|
|**_ftime64_s**|\<sys/types.h> 및 \<sys/timeb.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
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
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
