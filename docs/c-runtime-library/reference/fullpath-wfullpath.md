---
title: "_fullpath, _wfullpath | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7641c3cdc2a437d2c65f964ca6b1220992d11bca
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath
지정된 상대 경로 이름의 절대 또는 전체 경로 이름을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
#### <a name="parameters"></a>매개 변수  
 `absPath`  
 절대 또는 전체 경로 이름이나 NULL이 포함된 버퍼에 대한 포인터입니다.  
  
 `relPath`  
 상대 경로 이름입니다.  
  
 `maxLength`  
 절대 경로 이름 버퍼(`absPath`)의 최대 길이입니다. 이 길이는 `_fullpath`의 바이트 수로, `wchar_t`의 경우에는 와이드 문자 수입니다(`_wfullpath`).  
  
## <a name="return-value"></a>반환 값  
 dlfjgks 각 함수는 절대 경로 이름(`absPath`)이 포함된 버퍼에 대한 포인터를 반환합니다. 오류가 있는 경우(예: `relPath`에서 전달된 값에 잘못되었거나 찾을 수 없는 드라이브 문자가 포함된 경우 또는 작성된 절대 경로 이름(`absPath`)의 길이가 `maxLength`보다 큰 경우) 함수는 `NULL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_fullpath` 함수 확장에서 상대 경로 이름을 `relPath` 완전히 정규화 된 또는 절대 경로와 저장소의 이름을이 `absPath`합니다. `absPath`가 NULL인 경우 `malloc`를 사용하여 경로 이름을 포함할 충분한 길이의 버퍼를 할당합니다. 호출자가 이 버퍼를 해제해야 합니다. 상대 경로 이름은 현재 위치에서 시작되는 또 다른 위치에 대한 경로를 지정합니다(예: 현재 작업 디렉터리: "."). 절대 경로 이름은 파일 시스템의 루트에서 원하는 위치에 도달하는 데 필요한 전체 경로를 설명하는 상태 경로 이름의 확장입니다. `_makepath`와 달리 `_fullpath`는 이름에 "./" 또는 "../"를 포함하는 상대 경로(`relPath`)의 절대 경로 이름을 가져오는 데 사용될 수 있습니다.  
  
 예를 들어 C 런타임 루틴을 사용하려면 루틴 선언이 들어 있는 헤더 파일을 응용 프로그램에 포함해야 합니다. 각 헤더 파일의 include 문은 응용 프로그램 작업 디렉터리를 기준으로 한 상대적 방식으로 파일 위치를 참조합니다.  
  
```  
#include <stdlib.h>  
```  
  
 파일의 절대 경로(실제 파일 시스템 위치)가 다음과 같을 경우:  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath`는 현재 사용 중인 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하며 멀티바이트 문자열 인수를 자동으로 적절히 처리합니다. `_wfullpath`는 `_fullpath`의 와이드 문자 버전이며, `_wfullpath`에 대한 문자열 인수는 와이드 문자열입니다. `_wfullpath` 및 `_fullpath`는 동일하게 작동합니다. 단, `_wfullpath`는 멀티바이트 문자열을 처리하지 않습니다.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC`가 둘 다 정의된 경우 `_fullpath` 및 `_wfullpath` 호출이 `_fullpath_dbg` 및 `_wfullpath_dbg` 호출로 대체되어 메모리 할당 디버깅을 허용합니다. 자세한 내용은 [_fullpath_dbg, _wfullpath_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)를 참조하세요.  
  
 `maxlen`이 null 포인터이거나 0과 같은 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `NULL`을 반환합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 `absPath` 버퍼가 `NULL`인 경우 `_fullpath`는 [malloc](../../c-runtime-library/reference/malloc.md)를 호출하여 버퍼를 할당하고 `maxLength` 인수를 무시합니다. 호출자는 [free](../../c-runtime-library/reference/free.md)를 사용하여 이 버퍼를 적절하게 할당 해제해야 합니다. `relPath` 인수로 디스크 드라이브를 지정하면 이 드라이브의 현재 디렉터리가 경로와 결합됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_fullpath`|\<stdlib.h>|  
|`_wfullpath`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
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
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)
