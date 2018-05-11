---
title: _strtime, _wstrtime | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wstrtime
- _strtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
dev_langs:
- C++
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2881cc0b026225674096127eba165b622483de3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime

버퍼에 시간을 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_strtime(
   char *timestr
);
wchar_t *_wstrtime(
   wchar_t *timestr
);
template <size_t size>
char *_strtime(
   char (&timestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrtime(
   wchar_t (&timestr)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*timestr*<br/>
시간 문자열입니다.

## <a name="return-value"></a>반환 값

결과 문자열에 대 한 포인터를 반환 *timestr*합니다.

## <a name="remarks"></a>설명

**_strtime** 함수는 현재 현지 시간에서 가리키는 버퍼에 복사 *timestr*합니다. 시간 형식으로 지정 된 **hh: mm:** 여기서 **hh** 는 24 시간 표기법의 시간을 나타내는 두 자리 숫자로 **mm** 은 두 자리 시간과 를지난분을나타내는**ss** 은 두 자리 초를 나타내는입니다. 예를 들어 문자열 **18시 23분: 44** 23 분 및 44 지난 초 6 오후를 나타냅니다. 버퍼는 9바이트 이상이어야 합니다.

**_wstrtime** 의 와이드 문자 버전이 **_strtime**; 인수 및 반환 값의 **_wstrtime** 는 와이드 문자 문자열입니다. 이러한 함수 동일 하 게 작동 합니다. 경우 *timestr* 은 **NULL** 포인터 또는 *timestr* 형식이 잘못 되었습니다, 잘못 된에 설명 된 대로 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 예외는 이러한 함수 반환 NULL 및 set 계속 하도록 허용 된 경우 **errno** 를 **EINVAL** 경우 *timestr* NULL 되었거나 설정 **errno**를 **ERANGE** 경우 *timestr* 형식이 잘못 되었습니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_strtime**|\<time.h>|
|**_wstrtime**|\<time.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strtime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
   char tbuffer [9];
   _strtime( tbuffer ); // C4996
   // Note: _strtime is deprecated; consider using _strtime_s instead
   printf( "The current time is %s \n", tbuffer );
}
```

```Output
The current time is 14:21:44
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
