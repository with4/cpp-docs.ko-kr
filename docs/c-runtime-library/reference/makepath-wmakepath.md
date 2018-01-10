---
title: "_makepath, _wmakepath | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b811d4c851ae3c4949378512f5117d0809e8f1e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath
구성 요소에서 경로 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
#### <a name="parameters"></a>매개 변수  
 `path`  
 전체 경로 버퍼입니다.  
  
 `drive`  
 원하는 드라이브에 따른 문자(A, B 등) 및 후행 콜론(선택 사항)을 포함합니다. `_makepath`는 복합 경로에 콜론이 누락된 경우 자동으로 삽입합니다. `drive`가 `NULL` 또는 빈 문자열을 가리키는 경우 복합 `path` 문자열에 드라이브 문자가 나타나지 않습니다.  
  
 `dir`  
 드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다. 후행 슬래시는 선택 사항이며 슬래시(/)와 백슬래시(\\) 중 하나 또는 둘 다를 단일 `dir` 인수에 사용할 수 있습니다. 후행 슬래시(/ 또는 \\)가 지정되지 않은 경우 자동으로 삽입됩니다. `dir`이 `NULL`이거나 빈 문자열을 가리키는 경우 복합 `path` 문자열에 디렉터리 경로가 삽입되지 않습니다.  
  
 `fname`  
 파일 확장명 없이 기본 파일 이름을 포함합니다. `fname`이 `NULL`이거나 빈 문자열을 가리키는 경우 복합 `path` 문자열에 파일 이름이 삽입되지 않습니다.  
  
 `ext`  
 앞에 마침표(.)가 있거나 없는 실제 파일 확장명을 포함합니다. `_makepath`는 `ext`에 마침표가 나타나지 않는 경우 자동으로 삽입합니다. `ext`가 `NULL`이거나 빈 문자열을 가리키는 경우 복합 `path` 문자열에 확장명이 삽입되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `_makepath` 함수는 개별 구성 요소에서 복합 경로 문자열을 만들고 결과를 `path`에 저장합니다. `path`는 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 확장명을 포함할 수 있습니다. `_wmakepath`는 `_makepath`의 와이드 문자 버전이며, `_wmakepath`에 대한 인수는 와이드 문자 문자열입니다. 그렇지 않으면 `_wmakepath`과 `_makepath`이 동일하게 작동합니다.  
  
 **보안 정보** null로 끝나는 문자열을 사용하세요. 버퍼 오버런을 방지하기 위해 null로 끝나는 문자열은 `path` 버퍼의 크기를 초과할 수 없습니다. `_makepath`는 복합 경로 문자열의 길이가 `_MAX_PATH`를 초과하지 않도록 보장하지 않습니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 `path` 인수는 전체 경로를 포함할 수 있도록 충분히 큰 빈 버퍼를 가리켜야 합니다. 복합 `path`는 Stdlib.h에 정의된 `_MAX_PATH` 상수보다 크지 않아야 합니다.  
  
 경로가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 또한 `errno`는 `EINVAL`로 설정됩니다. `NULL` 값은 다른 모든 매개 변수에 대해 허용됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h>|  
|`_wmakepath`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
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
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
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
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)