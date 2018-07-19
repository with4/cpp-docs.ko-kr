---
title: _fullpath, _wfullpath | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fullpath
- _wfullpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b472987b0cac41c57e5fd22b2eedecef522613b4
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451682"
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath

지정된 상대 경로 이름의 절대 또는 전체 경로 이름을 만듭니다.

## <a name="syntax"></a>구문

```C
char *_fullpath(
   char *absPath,
   const char *relPath,
   size_t maxLength
);
wchar_t *_wfullpath(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength
);
```

### <a name="parameters"></a>매개 변수

*absPath*<br/>
절대 또는 전체 경로 이름을 포함 하는 버퍼에 대 한 포인터 또는 **NULL**합니다.

*relPath*<br/>
상대 경로 이름입니다.

*MaxLength*<br/>
절대 경로 이름 버퍼의 최대 길이 (*absPath*). 이 길이 바이트 단위에 대 한 **_fullpath** 는 와이드 문자 (**wchar_t**)에 대 한 **_wfullpath**합니다.

## <a name="return-value"></a>반환 값

이러한 각 함수를 절대 경로 이름을 포함 하는 버퍼에 대 한 포인터를 반환 (*absPath*). 오류가 발생 하는 경우 (값에 전달 하는 경우에 예를 들어 *relPath* 유효 하지 않거나 찾을 수 없는 드라이브 문자가 포함 된 경우 또는 작성된 된 절대 경로 이름 길이 (*absPath*) 보다 크면 *maxLength*)를 반환 하 고 **NULL**합니다.

## <a name="remarks"></a>설명

**_fullpath** 함수 확장에서 상대 경로 이름을 *relPath* 완전히 정규화 된 또는 절대 경로와 저장소의 이름을이 *absPath*합니다. 경우 *absPath* 은 **NULL**, **malloc** 경로 이름을 저장할 충분 한 길이의 버퍼를 할당 하는 데 사용 됩니다. 호출자가 이 버퍼를 해제해야 합니다. 상대 경로 이름은 현재 위치에서 시작되는 또 다른 위치에 대한 경로를 지정합니다(예: 현재 작업 디렉터리: "."). 절대 경로 이름은 파일 시스템의 루트에서 원하는 위치에 도달하는 데 필요한 전체 경로를 설명하는 상태 경로 이름의 확장입니다. 와 달리 **_makepath**, **_fullpath** 상대 경로 대 한 절대 경로 이름을 가져오는 데 사용할 수 있습니다 (*relPath*)를 포함 하는 ". /"또는"... / "이름에 있습니다.

예를 들어 C 런타임 루틴을 사용하려면 루틴 선언이 들어 있는 헤더 파일을 응용 프로그램에 포함해야 합니다. 각 헤더 파일의 include 문은 응용 프로그램 작업 디렉터리를 기준으로 한 상대적 방식으로 파일 위치를 참조합니다.

```C
#include <stdlib.h>
```

파일의 절대 경로(실제 파일 시스템 위치)가 다음과 같을 경우:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** 자동으로에서 현재 사용 중인 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하며 멀티 바이트 문자열 인수를 적절 하 게 처리 합니다. **_wfullpath** 의 와이드 문자 버전이 **_fullpath**;에 대 한 문자열 인수 **_wfullpath** 는 와이드 문자 문자열입니다. **_wfullpath** 및 **_fullpath** 점을 제외 하 고 동일 하 게 작동 **_wfullpath** 멀티 바이트 문자열을 처리 하지 않습니다.

경우 **_DEBUG** 및 **_CRTDBG_MAP_ALLOC** 는 둘 다 정의에 대 한 호출 **_fullpath** 및 **_wfullpath** 를호출하여대체 **_fullpath_dbg** 및 **_wfullpath_dbg** 메모리 할당 디버깅을 위해 합니다. 자세한 내용은 [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md)를 참조하세요.

이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)경우 *maxlen* 가 0 보다 작거나 같음. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **NULL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

경우는 *absPath* 버퍼가 **NULL**, **_fullpath** 호출 [malloc](malloc.md) 버퍼를 할당 하 고 무시는 *maxLength*  인수입니다. 호출자는 [free](free.md)를 사용하여 이 버퍼를 적절하게 할당 해제해야 합니다. 경우는 *relPath* 디스크 드라이브를 지정 하는 인수,이 드라이브의 현재 디렉터리의 경로와 결합 됩니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fullpath.c
// This program demonstrates how _fullpath
// creates a full path from a partial path.

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <direct.h>

void PrintFullPath( char * partialPath )
{
   char full[_MAX_PATH];
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )
      printf( "Full path is: %s\n", full );
   else
      printf( "Invalid path\n" );
}

int main( void )
{
   PrintFullPath( "test" );
   PrintFullPath( "\\test" );
   PrintFullPath( "..\\test" );
}
```

```Output
Full path is: C:\Documents and Settings\user\My Documents\test
Full path is: C:\test
Full path is: C:\Documents and Settings\user\test
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
