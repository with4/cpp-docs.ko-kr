---
title: "getenv, _wgetenv | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99d9104959dccf4a6879c4e929a1cdc281317171
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv
현재 환경에서 값을 가져옵니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)를 참조하세요.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `varname`  
 환경 변수 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 `varname`이 포함된 환경 테이블 항목에 대한 포인터를 반환합니다. 반환된 포인터를 사용하여 환경 변수의 값을 수정하는 것은 안전하지 않습니다. `_putenv` 함수를 사용하여 환경 변수 값을 수정합니다. `varname`이 환경 테이블에 없을 경우 반환 값은 `NULL`입니다.  
  
## <a name="remarks"></a>설명  
 `getenv` 함수는 `varname`애 대한 환경 변수 목록을 검색합니다. `getenv`는 Windows 운영 체제에서 대/소문자를 구분하지 않습니다. `getenv` 및 `_putenv`는 전역 변수 `_environ`이 가리키는 환경의 복사본을 사용하여 환경에 액세스합니다. `getenv`는 운영 체제에서 프로세스에 대해 만드는 환경 "세그먼트"가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 따라서 [main](../../cpp/main-program-startup.md) 또는 [wmain](../../cpp/main-program-startup.md)에 대해 `envp` 인수를 사용하는 프로그램은 잘못된 정보를 검색할 수 있습니다.  
  
 `varname`가 `NULL`인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `NULL`을 반환합니다.  
  
 `_wgetenv`는 `getenv`의 와이드 문자 버전이고, `_wgetenv`의 인수와 반환 값은 와이드 문자 문자열입니다. `_wenviron` 전역 변수는 `_environ`의 와이드 문자 버전입니다.  
  
 MBCS 프로그램(예: SBCS ASCII 프로그램)에서 환경은 멀티바이트 문자열로 구성되기 때문에, `_wenviron`은 처음에 `NULL`입니다. 그런 다음 `_wputenv` 또는 `_wgetenv`의 첫 번째 호출에서 (MBCS) 환경이 이미 있는 경우 해당 와이드 문자열 환경이 만들어지고 `_wenviron`이 해당 환경을 가리킵니다.  
  
 마찬가지로, 유니코드(`_wmain`) 프로그램에서는 환경이 와이드 문자열로 구성되기 때문에 `_environ`은 처음에 `NULL`입니다. 그다음에 `_putenv` 또는 `getenv`의 첫 번째 호출에서 (유니코드) 환경이 이미 있는 경우 해당 MBCS 환경이 만들어지고 `_environ`에 의해 가리킵니다.  
  
 환경의 두 개의 복사본(MBCS 및 유니코드)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이에 따라 실행 시간이 늦어집니다. 예를 들어 `_putenv`를 호출할 때마다 `_wputenv`에 대한 호출도 자동으로 실행되어 두 환경 문자열이 일치하게 됩니다.  
  
> [!CAUTION]
>  드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 이러한 두 환경 버전이 정확히 일치하지 않을 수도 있습니다. 이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문입니다. 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.  
  
> [!NOTE]
>  함수의 `_putenv` 및 `_getenv` 패밀리는 스레드로부터 안전하지 않습니다. `_getenv`는 `_putenv`가 문자열을 수정하는 동안 문자열 포인터를 반환할 수 있으므로 임의의 오류를 발생시킵니다. 이러한 함수에 대한 호출은 동기화해야 합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 `TZ` 환경 변수 값을 확인하거나 변경하려면 필요에 따라 `getenv`, `_putenv` 및 `_tzset`를 사용합니다. `TZ`에 대한 자세한 내용은 [_tzset](../../c-runtime-library/reference/tzset.md) 및 [_daylight, timezone 및 _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`getenv`|\<stdlib.h>|  
|`_wgetenv`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
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
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [환경 상수](../../c-runtime-library/environmental-constants.md)