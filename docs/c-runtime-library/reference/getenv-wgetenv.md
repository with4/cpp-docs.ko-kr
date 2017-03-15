---
title: "getenv, _wgetenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getenv"
  - "_wgetenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wgetenv"
  - "getenv"
  - "_tgetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tgetenv 함수"
  - "_wgetenv 함수"
  - "환경 값"
  - "환경 변수"
  - "getenv 함수"
  - "tgetenv 함수"
  - "wgetenv 함수"
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# getenv, _wgetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 환경에서 값을 가져옵니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### 매개 변수  
 `varname`  
 환경 변수명  
  
## 반환 값  
 포함된 `varname` 환경 테이블 항목에 관한 포인터를 반환합니다.  반환된 포인터를 사용하여 환경 변수 값을 수정하는 것은 안전하지 않습니다.  이 `_putenv` 함수는 환경 변수의 값을 수정하는데 사용합니다.  반환 값은 `NULL` 입니다. 이는 `varname` 이 환경 테이블에 없을 경우입니다.  
  
## 설명  
 `getenv` 함수는 `varname` 에 대한 환경 변수 목록을 검색합니다.  `getenv` 는 Windows 운영 체제에서 대\/소문자가 구분 되지 않습니다.  `getenv` 와 `_putenv` 는 환경에 접근하기 위한 전역 변수 `_environ` 에 의해 포인터된 환경 복사본을 사용합니다.  `getenv` 는 운영체제에 의해 프로세스를 만드는 환경 "세그먼트"가 아닌 런타임 라이브러리에 접근할 수 있는 데이터 구조에서만 작동합니다.  따라서 프로그램은 `envp` 인수를 사용합니다. [main](../../cpp/main-program-startup.md) 또는 [wmain](../../cpp/main-program-startup.md) 은 잘못된 정보를 검색할 수 있습니다.  
  
 만일 `varname` 이 `NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `NULL`을 반환합니다.  
  
 `_wgetenv` 는 `getenv` 의 와이드 문자 버전입니다. `_wgetenv` 인수와 반환 값은 와이드 문자 문자열입니다.  `_wenviron` 전역 변수는 와이드 문자 버전인 `_environ`입니다.  
  
 MBCS 프로그램 \(예를 들어, ASCII SBCS 프로그램에서\) `_wenviron` 는 원래 `NULL` 입니다. 환경에서 멀티 바이트 문자 문자열 구성 되어 있기 때문입니다.  `_wputenv`를 처음 호출할 때 또는 MBCS 환경이 이미 있는 경우에는 `_wgetenv` 를 처음 호출할 때 해당 와이드 문자열 환경이 만들어지고 `_wenviron`에 의해 가르켜집니다.  
  
 유니코드와 유사한 \(`_wmain`\) 프로그램인, `_environ` 는 원래 `NULL` 입니다. 와이드 문자열 환경이 구성 되어 있기 때문입니다.  `_putenv`를 처음 호출할 때 또는 MBCS 환경이 이미 있는 경우에는 `getenv` 를 처음 호출할 때 해당 와이드 문자열 환경이 만들어지고, `_environ`에 의해 가르켜집니다.  
  
 환경 프로그램의 두개 복사본\(MBCS와 유니코드\)이 프로그램에서 동시에 존재할 때, 실행 시간을 더 늦춘 결과로서, 런타임 시스템은 두개의 복사본을 유지해야만 합니다.  예를 들어, `_putenv` 이 호출될 때마다, `_wputenv` 호출은 또한 자동으로 실행됩니다, 따라서 두개의 환경 문자열은 반응하게됩니다.  
  
> [!CAUTION]
>  경우에 따라서 런타임 시스템 유니코드 버전 및 환경, 멀티 바이트 버전을 모두 유지 관리 하는 경우 이러한 두 환경 버전은 정확하게 반응하지 않습니다.  멀티 바이트문자 문자열에 대한 고유 유니코드 문자열 매핑은 반드시 고유 하지 않기 때문에, 고유 유니코드 문자열로부터 매핑이 필요 이상으로 고유하지 않습니다.  자세한 내용은 [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md)를 참조하십시오.  
  
> [!NOTE]
>  `_putenv` 및 `_getenv` 함수 패밀리는 스레드로부터 안전 하지 않습니다.  `_putenv` 임의 오류가 발생 하 여 문자열을 수정하는 동안, `_getenv` 는 문자열 포인터를 반환합니다.  이러한 함수에 대한 호출은 동기화해야 합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 이 `TZ` 환경 변수의 값을 바꾸거나 확인하기 위하여, `getenv`, `_putenv` 및 `_tzset` 필요에 따라 사용합니다.  자세한 내용은 `TZ` [\_tzset](../../c-runtime-library/reference/tzset.md) 및 [\_daylight, 시간대 및 \_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`getenv`|\<stdlib.h\>|  
|`_wgetenv`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
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
  
  **원본 LIB 변수: C:\\progra~1\\devstu~1\\vc\\lib**  
**새 변수를 LIB: c:\\mylib;c:\\yourlib**   
## 해당 .NET Framework 항목  
 [System.Environment::GetEnvironmentVariables](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [환경 상수](../../c-runtime-library/environmental-constants.md)