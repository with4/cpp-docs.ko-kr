---
title: "getenv_s, _wgetenv_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getenv_s"
  - "_wgetenv_s"
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
  - "getenv_s"
  - "_tgetenv_s"
  - "_wgetenv_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tgetenv_s 함수"
  - "_wgetenv_s 함수"
  - "환경 변수"
  - "getenv_s 함수"
  - "tgetenv_s 함수"
  - "wgetenv_s 함수"
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 42
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getenv_s, _wgetenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 환경에서 값을 가져옵니다.  이러한 버전의 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char* buffer,  
   size_t numberOfElements,  
   const char *varname   
);  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *varname   
);  
template <size_t size>  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char (&buffer)[size],  
   const char *varname   
); // C++ only  
template <size_t size>  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t (&buffer)[size],  
   const wchar_t *varname   
); // C++ only  
```  
  
#### 매개 변수  
 `pReturnValue`  
 필요한 버퍼 크기이거나, 변수가 없으면 0입니다.  
  
 `buffer`  
 환경 변수의 값을 저장할 버퍼입니다.  
  
 `numberOfElements`  
 `buffer`의 크기입니다.  
  
 `varname`  
 환경 변수 이름입니다.  
  
## 반환 값  
 성공하면 0이고, 그렇지 않으면 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|반환 값|  
|--------------------|--------------|------------------------|---------------|----------|  
|`NULL`|모두|any|모두|`EINVAL`|  
|모두|`NULL`|\>0|모두|`EINVAL`|  
|모두|any|모두|`NULL`|`EINVAL`|  
  
 이들 오류 조건은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
 또한 버퍼가 너무 작으면 이들 함수는 `ERANGE`를 반환합니다.  잘못된 매개 변수 처리기를 호출하지 않습니다.  `pReturnValue`에서 필요한 버퍼 크기를 작성하고 이를 통해 프로그램이 더 큰 버퍼를 사용하여 함수를 다시 호출할 수 있습니다.  
  
## 설명  
 `getenv_s` 함수는 `varname`애 대한 환경 변수 목록을 검색합니다.  `getenv_s`는 Windows 운영 체제에서 대\/소문자를 구분하지 않습니다.  `getenv_s` 및 `_putenv_s`는 전역 변수 `_environ`이 가리키는 환경의 복사본을 사용하여 환경에 액세스합니다.  `getenv_s`는 운영 체제에서 프로세스에 대해 만드는 환경 "세그먼트"가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다.  따라서 [main](../../cpp/main-program-startup.md) 또는 [wmain](../../cpp/main-program-startup.md)에 대해 `envp` 인수를 사용하는 프로그램은 잘못된 정보를 검색할 수 있습니다.  
  
 `_wgetenv_s`는 `getenv_s`의 와이드 문자 버전이고, `_wgetenv_s`의 인수와 반환 값은 와이드 문자 문자열입니다.  `_wenviron` 전역 변수는 `_environ`의 와이드 문자 버전입니다.  
  
 MBCS 프로그램\(예: SBCS ASCII 프로그램\)에서 환경은 멀티바이트 문자열로 구성되기 때문에, `_wenviron`은 처음에 `NULL`입니다.  그다음에 `_wputenv` 또는 `_wgetenv_s`의 첫 번째 호출에서 \(MBCS\) 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 `_wenviron`에 의해 가리킵니다.  
  
 마찬가지로, 유니코드 `(_wmain`\) 프로그램에서 환경이 와이드 문자 문자열로 구성되기 때문에 `_environ`은 처음에 `NULL`입니다.  그다음에 `_putenv` 또는 `getenv_s`의 첫 번째 호출에서 \(유니코드\) 환경이 이미 있는 경우 해당 MBCS 환경이 만들어지고 `_environ`에 의해 가리킵니다.  
  
 환경의 두 개의 복사본\(MBCS 및 유니코드\)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이로 인해 실행 시간이 늦어집니다.  예를 들어 `_putenv`를 호출할 때 `_wputenv`에 대한 호출도 자동으로 실행되어 두 환경 문자열이 일치하게 됩니다.  
  
> [!CAUTION]
>  드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 두 환경 버전이 정확히 일치하지 않을 수도 있습니다.  이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문에 발생합니다.  자세한 내용은 [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.  
  
> [!NOTE]
>  함수의 `_putenv_s` 및 `_getenv_s` 패밀리는 스레드로부터 안전하지 않습니다.  `_getenv_s`는 `_putenv_s`가 문자열을 수정하는 동안 문자열 포인터를 반환할 수 있고 이로 인해 임의 오류가 발생합니다.  이러한 함수에 대한 호출은 동기화해야 합니다.  
  
 C\+\+에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 `TZ` 환경 변수 값을 확인하거나 변경하려면 필요에 따라 `getenv_s`, `_putenv` 및 `_tzset`를 사용합니다.  `TZ`에 대한 자세한 내용은 [\_tzset](../../c-runtime-library/reference/tzset.md) 및 [\_daylight, \_dstbias, \_timezone 및 \_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`getenv_s`|\<stdlib.h\>|  
|`_wgetenv_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_getenv_s.c  
// This program uses getenv_s to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* libvar;  
   size_t requiredSize;  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
   if (requiredSize == 0)  
   {  
      printf("LIB doesn't exist!\n");  
      exit(1);  
   }  
  
   libvar = (char*) malloc(requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the value of the LIB environment variable.  
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects  
   // the environment variable of the current process. The command  
   // processor's environment is not changed.  
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
  
   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the new value of the LIB environment variable.   
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "New LIB variable is: %s\n", libvar );  
  
   free(libvar);  
}  
```  
  
  **원래 LIB 변수: c:\\vctools\\lib;c:\\vctools\\atlmfc\\lib;c:\\vctools\\PlatformSDK\\lib;c:\\vctools\\Visual Studio SDKs\\DIA Sdk\\lib;c:\\vctools\\Visual Studio SDKs\\BSC Sdk\\lib**  
**새 LIB 변수: c:\\mylib;c:\\yourlib**   
## 해당 .NET Framework 항목  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [환경 상수](../../c-runtime-library/environmental-constants.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [\_dupenv\_s, \_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)