---
title: getenv, _wgetenv | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- getenv
- _wgetenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wgetenv
- getenv
- _tgetenv
dev_langs:
- C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2e68ca55d9e33995df583719e4797a6880d34ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv

현재 환경에서 값을 가져옵니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)를 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>매개 변수

*varname*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>반환 값

포함 된 환경 테이블 항목에 대 한 포인터를 반환 *varname*합니다. 반환된 포인터를 사용하여 환경 변수의 값을 수정하는 것은 안전하지 않습니다. 사용 하 여는 [_putenv](putenv-wputenv.md) 환경 변수의 값을 수정 하는 함수입니다. 반환 값은 **NULL** 경우 *varname* 환경 테이블에 없습니다.

## <a name="remarks"></a>설명

**getenv** 함수에 대 한 환경 변수 목록을 검색 *varname*합니다. **getenv** 대/소문자가 Windows 운영 체제에서 합니다. **getenv** 및 **_putenv** 전역 변수가 가리키는 환경의 복사본을 사용 하 여 **_environ** 환경에 액세스 합니다. **getenv** 환경 "세그먼트" 프로세스에 대 한 운영 체제에서 만든 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에만 작동 합니다. 따라서 사용 하는 프로그램의 *envp* 인수를 [주](../../cpp/main-program-startup.md) 또는 [wmain](../../cpp/main-program-startup.md) 잘못 된 정보를 검색할 수 있습니다.

경우 *varname* 은 **NULL**,이 함수가 잘못 된 매개 변수 처리기를 호출 하는에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **NULL**합니다.

**_wgetenv** 의 와이드 문자 버전이 **getenv**; 인수 및 반환 값의 **_wgetenv** 는 와이드 문자 문자열입니다. **_wenviron** 전역 변수는 와이드 문자 버전의 **_environ**합니다.

MBCS 프로그램 (예를 들어에 SBCS ASCII 프로그램)에서 **_wenviron** 은 처음 **NULL** 환경이 멀티 바이트 문자열로 구성 되기 때문에 있습니다. 그런 다음 첫 번째 호출 [_wputenv](putenv-wputenv.md), 또는 첫 번째 호출에서 **_wgetenv** (MBCS) 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고에 의해 가리킵니다 **_wenviron**합니다.

마찬가지로 유니코드에서 (**_wmain**) 프로그램 **_environ** 은 처음 **NULL** 환경이 와이드 문자열로 구성 되기 때문에 있습니다. 그런 다음 첫 번째 호출 **_putenv**, 첫 번째 호출 또는 **getenv** (유니코드) 환경이 이미 있는 경우 해당 MBCS 환경이 만들어지고에 의해 가리킵니다 **_ environ**합니다.

환경의 두 개의 복사본(MBCS 및 유니코드)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이에 따라 실행 시간이 늦어집니다. 호출할 때마다 예를 들어 **_putenv**에 대 한 호출 **_wputenv** 두 환경 문자열이 일치 되도록 자동으로 실행도 됩니다.

> [!CAUTION]
> 드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 이러한 두 환경 버전이 정확히 일치하지 않을 수도 있습니다. 이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문입니다. 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.

> [!NOTE]
> **_putenv** 및 **_getenv** 함수 패밀리는 스레드로부터 안전 하지 않습니다. **_getenv** 하는 동안 문자열 포인터를 반환할 수 **_putenv** 임의 오류가 발생 하는 문자열을 수정 합니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

확인 하거나의 값을 변경 하려면는 **TZ** 환경 변수를 사용 하 여 **getenv**, **_putenv** 및 **_tzset** 필요에 따라 합니다. 에 대 한 자세한 내용은 **TZ**, 참조 [_tzset](tzset.md) 및 [_daylight, timezone, 및 _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getenv.c
// compile with: /W3
// This program uses getenv to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *libvar;

   // Get the value of the LIB environment variable.
   libvar = getenv( "LIB" ); // C4996
   // Note: getenv is deprecated; consider using getenv_s instead

   if( libvar != NULL )
      printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects the environment
   // variable of the current process. The command processor's
   // environment is not changed.
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996
   // Note: _putenv is deprecated; consider using putenv_s instead

   // Get new value.
   libvar = getenv( "LIB" ); // C4996

   if( libvar != NULL )
      printf( "New LIB variable is: %s\n", libvar );
}
```

```Output
Original LIB variable is: C:\progra~1\devstu~1\vc\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[환경 상수](../../c-runtime-library/environmental-constants.md)<br/>
