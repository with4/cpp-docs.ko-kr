---
title: _makepath, _wmakepath | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c339ce6ad67186dc7a4f43d7006c5beb047c8f90
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404954"
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath

구성 요소에서 경로 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>매개 변수

*경로* 전체 경로 버퍼입니다.

*드라이브* (A, B, 및 등)는 문자를 포함 합니다. 해당 원하는 드라이브 및 선택적 후행 콜론 하 합니다. **_makepath** 누락 된 경우 복합 경로에 콜론이 자동으로 삽입 합니다. 경우 *드라이브* 은 **NULL** 빈 문자열을 가리키는 복합에 표시 된 드라이브 문자 없음 또는 *경로* 문자열입니다.

*dir* 드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로 포함 합니다. 후행 슬래시는 선택 사항이 슬래시 (/) 또는 백슬래시 (\\) 또는 둘 다에서 사용 하는 단일 *dir* 인수입니다. 후행 슬래시(/ 또는 \\)가 지정되지 않은 경우 자동으로 삽입됩니다. 경우 *dir* 은 **NULL** 복합에 디렉터리 경로가 없는 빈 문자열 가리키면 삽입 되어 또는 *경로* 문자열입니다.

*fname* 파일 확장명 없이 기본 파일 이름을 포함 합니다. 경우 *fname* 은 **NULL** 또는 빈 문자열인 경우 파일 이름이 없습니다 가리키는 복합에 삽입 됩니다 *경로* 문자열입니다.

*ext* 선행 마침표 (.)가 있거나 없는 실제 파일 이름 확장명을 포함 합니다. **_makepath** 에 나타나지 않도록 하는 경우에 기간을 자동으로 삽입 *ext*합니다. 경우 *ext* 은 **NULL** 또는 빈 문자열이 면 확장명이 없는 가리키는 복합에 삽입 됩니다 *경로* 문자열입니다.

## <a name="remarks"></a>설명

**_makepath** 함수에서 해당 결과 저장 하는 개별 구성 요소에서 복합 경로 문자열을 만들고 *경로*합니다. *경로* 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장명 포함 될 수 있습니다. **_wmakepath** 의 와이드 문자 버전이 **_makepath**;에 대 한 인수 **_wmakepath** 는 와이드 문자 문자열입니다. **_wmakepath** 및 **_makepath** 동일 하 게 작동 합니다.

**보안 정보** null로 끝나는 문자열을 사용하세요. 버퍼 오버런을 방지 하려면 null로 끝나는 문자열의 크기 넘지 않아야는 *경로* 버퍼입니다. **_makepath** 보장 하지는 복합 경로 문자열의 길이 초과 하지 않는 **_MAX_PATH**합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*경로* 인수 전체 경로 포함할 수 있을 만큼 큰 빈 버퍼를 가리켜야 합니다. 복합 *경로* 미만 이어야 합니다는 **_MAX_PATH** Stdlib.h에 정의 된 상수입니다.

경로 이면 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 또한 **errno** 로 설정 된 **EINVAL**합니다. **NULL** 값 다른 모든 매개 변수에 대해 허용 됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
