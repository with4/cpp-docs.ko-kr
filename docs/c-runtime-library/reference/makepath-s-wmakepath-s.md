---
title: _makepath_s, _wmakepath_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wmakepath_s
- _makepath_s
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
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
dev_langs:
- C++
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a981e8758200e055693f24761238c98c3755311c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="makepaths-wmakepaths"></a>_makepath_s, _wmakepath_s

구성 요소에서 경로 이름을 만듭니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_makepath, _wmakepath](makepath-wmakepath.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>매개 변수

*path*<br/>
전체 경로 버퍼입니다.

*sizeInWords*<br/>
버퍼의 크기(워드)입니다.

*sizeInBytes*<br/>
버퍼의 크기(바이트)입니다.

*드라이브*<br/>
원하는 드라이브에 따른 문자(A, B 등) 및 후행 콜론(선택 사항)을 포함합니다. **_makepath_s** 누락 된 경우 복합 경로에 콜론이 자동으로 삽입 합니다. 경우 *드라이브* 은 **NULL** 빈 문자열을 가리키는 복합에 표시 된 드라이브 문자 없음 또는 *경로* 문자열입니다.

*dir*<br/>
드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다. 후행 슬래시는 선택 사항이 슬래시 (/) 또는 백슬래시 (\\) 또는 둘 다에서 사용 하는 단일 *dir* 인수입니다. 후행 슬래시(/ 또는 \\)가 지정되지 않은 경우 자동으로 삽입됩니다. 경우 *dir* 은 **NULL** 복합에 디렉터리 경로가 없는 빈 문자열 가리키면 삽입 되어 또는 *경로* 문자열입니다.

*fname*<br/>
파일 확장명 없이 기본 파일 이름을 포함합니다. 경우 *fname* 은 **NULL** 또는 빈 문자열인 경우 파일 이름이 없습니다 가리키는 복합에 삽입 됩니다 *경로* 문자열입니다.

*ext*<br/>
앞에 마침표(.)가 있거나 없는 실제 파일 확장명을 포함합니다. **_makepath_s** 에 나타나지 않도록 하는 경우에 기간을 자동으로 삽입 *ext*합니다. 경우 *ext* 은 **NULL** 또는 빈 문자열이 면 확장명이 없는 가리키는 복합에 삽입 됩니다 *경로* 문자열입니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*path*|*sizeInWords* / *sizeInBytes*|반환|내용을 *경로*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|모두|**EINVAL**|수정 안 됨|
|모두|<= 0|**EINVAL**|수정 안 됨|

위의 오류 조건이 발생하는 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수 반환 **EINVAL**합니다. **NULL** 매개 변수에 대해 허용 *드라이브*, *fname*, 및 *ext*합니다. 이러한 매개 변수가 null 포인터 또는 빈 문자열일 때 동작에 대한 자세한 내용은 설명 부분을 참조하십시오.

## <a name="remarks"></a>설명

**_makepath_s** 함수에서 해당 결과 저장 하는 개별 구성 요소에서 복합 경로 문자열을 만들고 *경로*합니다. *경로* 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장명 포함 될 수 있습니다. **_wmakepath_s** 의 와이드 문자 버전이 **_makepath_s**;에 대 한 인수 **_wmakepath_s** 는 와이드 문자 문자열입니다. **_wmakepath_s** 및 **_makepath_s** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*경로* 인수 전체 경로 포함할 수 있을 만큼 큰 빈 버퍼를 가리켜야 합니다. 복합 *경로* 미만 이어야 합니다는 **_MAX_PATH** Stdlib.h에 정의 된 상수입니다.

경로 이면 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 또한 **errno** 로 설정 된 **EINVAL**합니다. **NULL** 값 다른 모든 매개 변수에 대해 허용 됩니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
