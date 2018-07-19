---
title: _searchenv, _wsearchenv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _searchenv
- _wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
dev_langs:
- C++
helpviewer_keywords:
- _wsearchenv function
- files [C++], finding
- _searchenv function
- tsearchenv function
- environment paths, searching for files
- _tsearchenv function
- wsearchenv function
- searchenv function
- environment paths
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62e0fea9154801f850640234355af53dc1154160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408917"
---
# <a name="searchenv-wsearchenv"></a>_searchenv, _wsearchenv

환경 경로를 사용하여 파일을 검색합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)를 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _searchenv(
   const char *filename,
   const char *varname,
   char *pathname
);
void _wsearchenv(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname
);
template <size_t size>
void _searchenv(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
void _wsearchenv(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*filename* 검색할 파일의 이름입니다.

*varname* 검색할 환경입니다.

*pathname* 전체 경로를 저장할 버퍼입니다.

## <a name="remarks"></a>설명

**_searchenv** 일상적인 지정된 된 도메인에 대상 파일을 검색 합니다. *varname* 변수는 모든 환경 또는 사용자 정의 변수 될 수 있습니다-예를 들어 **경로**, **LIB**, 또는 **INCLUDE**-지정 하는 디렉터리 경로 목록입니다. 때문에 **_searchenv** 대/소문자 구분, *varname* 환경 변수의 대/소문자와 일치 해야 합니다.

루틴은 먼저 현재 작업 디렉터리에서 파일을 검색합니다. 파일을 찾을 수 없는 경우 환경 변수에 지정된 디렉터리에서 찾습니다. 새로 만든된 경로가에 복사 됩니다 대상 파일이 이러한 디렉터리 중 하나에 있으면 *pathname*합니다. 경우는 *filename* 파일을 찾지 *pathname* 빈 null로 끝나는 문자열을 포함 합니다.

*pathname* 버퍼 보다 길거나 같아야 **_MAX_PATH** 생성 된 경로 이름의 전체 길이 맞게 자입니다. 그렇지 않으면 **_searchenv** 오버런 수는 *pathname* 버퍼링 하 고 예기치 않은 동작이 발생할 합니다.

**_wsearchenv** 의 와이드 문자 버전이 **_searchenv**, 변수와 인수를 **_wsearchenv** 는 와이드 문자 문자열입니다. **_wsearchenv** 및 **_searchenv** 동일 하 게 작동 합니다.

경우 *filename* 이 빈 문자열인 경우 이러한 함수는 반환 **ENOENT**합니다.

경우 *filename* 또는 *pathname* 는 **NULL** 에 설명 된 대로 포인터, 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된, 하는 경우 이러한 함수가-1을 반환 하 고 설정 **errno** 를 **EINVAL**합니다.

에 대 한 자세한 내용은 **errno** 오류 코드 참조와 [errno 상수](../../c-runtime-library/errno-constants.md)합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv**|**_searchenv**|**_searchenv**|**_wsearchenv**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_searchenv**|\<stdlib.h>|
|**_wsearchenv**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_searchenv.c
// compile with: /W3
// This program searches for a file in
// a directory that's specified by an environment variable.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";

   // Search for file in PATH environment variable:
   _searchenv( searchfile, envvar, pathbuffer ); // C4996
   // Note: _searchenv is deprecated; consider using _searchenv_s
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 8\VC\BIN\CL.EXE
```

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)<br/>
