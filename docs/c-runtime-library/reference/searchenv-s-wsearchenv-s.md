---
title: _searchenv_s, _wsearchenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsearchenv_s
- _searchenv_s
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
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs: C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f1089aa1f772832417168a2262fa72069b3ede7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s
환경 경로를 사용하여 파일을 검색합니다. 이러한 버전의 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `filename`  
 검색할 파일의 이름입니다.  
  
 [in] `varname`  
 검색할 환경입니다.  
  
 [out] `pathname`  
 전체 경로를 저장할 버퍼입니다.  
  
 [in] `numberOfElements`  
 크기는 `pathname` 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
 `filename`이 빈 문자열이면 반환 값은 `ENOENT`입니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|반환 값|`pathname`의 내용|  
|----------------|---------------|----------------|------------------------|------------------|----------------------------|  
|any|any|`NULL`|any|`EINVAL`|N/A|  
|`NULL`|any|any|any|`EINVAL`|변경되지 않음|  
|any|any|any|<= 0|`EINVAL`|변경되지 않음|  
  
 이러한 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 발생합니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_searchenv_s` 루틴은 지정된 도메인에서 대상 파일을 검색합니다. `varname` 변수는 디렉터리 경로 목록을 지정하는 모든 환경 변수 또는 사용자 정의 변수(예: `PATH`, `LIB` 또는 `INCLUDE`)일 수 있습니다. `_searchenv_s`에서 대/소문자를 구분하므로 `varname`은 환경 변수의 대/소문자와 일치해야 합니다. `varname`이 프로세스의 환경에 정의된 환경 변수의 이름과 일치하지 않으면 함수는 0을 반환하며 `pathname` 변수는 변경되지 않습니다.  
  
 루틴은 먼저 현재 작업 디렉터리에서 파일을 검색합니다. 파일을 찾을 수 없는 경우 다음 위치로 환경 변수에 지정된 디렉터리를 확인합니다. 대상 파일이 이러한 디렉터리 중 하나에 있는 경우 새로 만든 경로가 `pathname`에 복사됩니다. `filename` 파일을 찾을 수 없는 경우 `pathname`에 빈 null 종료 문자열이 포함됩니다.  
  
 `pathname` 버퍼가 생성된 경로 이름의 전체 길이를 수용하려면 `_MAX_PATH`자 이상이어야 합니다. 그렇지 않으면 `_searchenv_s`가 `pathname` 버퍼를 오버런하여 예기치 않은 동작이 발생할 수 있습니다.  
  
 `_wsearchenv_s`는 `_searchenv_s`의 와이드 문자 버전이며, `_wsearchenv_s`에 대한 인수는 와이드 문자 문자열입니다. 그렇지 않으면 `_wsearchenv_s`과 `_searchenv_s`이 동일하게 작동합니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h>|  
|`_wsearchenv_s`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)