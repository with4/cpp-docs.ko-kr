---
title: gmtime, _gmtime32, _gmtime64 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28ce8b8e2367e1d4dd26672206557867c07827e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64

변환는 **time_t** 시간 값에는 **tm** 구조입니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>매개 변수

*sourceTime*<br/>
저장된 시간에 대한 포인터입니다. 시간은 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후 경과한 시간(초)으로 표현됩니다.

## <a name="return-value"></a>반환 값

[tm](../../c-runtime-library/standard-types.md) 형식의 구조체에 대한 포인터입니다. 계산 된 값을 보유 하는 반환 된 구조체의 필드는 *sourceTime* 인수 UTC 대신 현지 시간입니다. 형식의 각 구조 필드는 **int**다음과 같이 합니다.

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
|**tm_isdst**|항상 0에 대 한 **gmtime**합니다.|

32 비트 및 64 비트 버전의 두 **gmtime**, [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), 및 [localtime](localtime-localtime32-localtime64.md) 하나의 공통을 사용 하 여 모든 **tm**  구조 변환에 대 한 스레드당 합니다. 이러한 함수 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다. 경우 *sourceTime* , 1970 년 1 월 1 일 이전의 날짜를 나타내는 **gmtime** 반환 **NULL**합니다. 반환되는 오류가 없습니다.

**_gmtime64**를 사용 하는 **__time64_t** 구조, 23시 59분: 59 까지의 3000 년 12 월 31 일, UTC 표시 해야 하는 날짜를 사용 하면 반면 **_gmtime32** 만 23시 59분: 59 까지의 날짜를 나타냅니다 2038 년 1 월 18 일 UTC입니다. 1970년 1월 1일 자정은 두 함수 모두에 대한 날짜 범위의 하한입니다.

**gmtime** 으로 계산 되는 인라인 함수 이며 **_gmtime64**, 및 **time_t** 같습니다 **__time64_t** 하지 않는 한 **_USE_32BIT_TIME_ T** 정의 됩니다. 컴파일러가 해석 하도록을 강제 적용 해야 하는 경우 **time_t** 이전 32 비트로 **time_t**를 정의할 수 있습니다 **_USE_32BIT_TIME_T**, 이렇게 하면 하지만 **gmtime** 인라인 되도록 **_gmtime32** 및 **time_t** 로 정의 하려면 **__time32_t**합니다. 이 방법은 64비트 플랫폼에서 허용되지 않고 2038년 1월 18일 이후 응용 프로그램이 작동하지 않을 수 있기 때문에 권장되지 않습니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 *sourceTime* 가 null 포인터인 경우는 *sourceTime* 값이 음수인 경우에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는이 함수를 이러한 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) . 실행을 계속 허용 된 경우 함수는 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

## <a name="remarks"></a>설명

**_gmtime32** 함수 분할 하는 *sourceTime* 값 형식의 정적으로 할당 된 구조에 저장 합니다 **tm**시간에 정의 된 합니다. 8. 값 *sourceTime* 에 대 한 호출에서 가져온 일반적으로 [시간](time-time32-time64.md) 함수입니다.

> [!NOTE]
> 대부분의 경우 대상 환경에서는 일광 절약 시간이 적용되는지 확인하려고 합니다. C 런타임 라이브러리에서는 DST(일광 절약 시간) 계산 구현을 위한 미국 규칙이 사용된다고 가정합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<time.h>|\<ctime > 또는 \<. h >|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
