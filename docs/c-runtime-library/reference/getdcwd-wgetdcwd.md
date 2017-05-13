---
title: "_getdcwd, _wgetdcwd | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd
- _wgetdcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 03791f920619b98beec3c1bbbd33b45b550eaf7a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd
지정한 드라이브의 현재 작업 디렉터리의 전체 경로를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `drive`  
 드라이브를 지정하는 음수가 아닌 정수입니다(0 = 기본 드라이브, 1 = A, 2 = B 등).  
  
 지정된 드라이브를 사용할 수 없는 경우 또는 드라이브 유형(예: 이동식, 고정, CD-ROM, RAM 디스크 또는 네트워크 드라이브)을 확인할 수 없는 경우 [Parameter Validation](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
 `buffer`  
 경로에 대한 저장소 위치 또는 **NULL**입니다.  
  
 **NULL** 이 지정된 경우 이 함수는 `maxlen` 을 사용하여 최소한 **malloc**크기의 버퍼를 할당하고 `_getdcwd` 의 반환 값은 할당된 버퍼에 대한 포인터입니다. `free` 를 호출하고 포인터에 전달하여 버퍼를 해제할 수 있습니다.  
  
 `maxlen`  
 경로의 최대 길이를 지정하는 0이 아닌 양의 정수: `char` 에 대한 `_getdcwd` 및 `wchar_t` 에 대한 `_wgetdcwd`  
  
 `maxlen` 이 0보다 크지 않은 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
## <a name="return-value"></a>반환 값  
 지정된 드라이브의 현재 작업 디렉터리의 전체 경로를 나타내는 문자열에 대한 포인터 또는 오류를 나타내는 `NULL`입니다.  
  
 `buffer` 가 `NULL` 로 지정되고 `maxlen` 문자를 할당할 메모리가 부족한 경우 오류가 발생하고 `errno` 가 `ENOMEM`으로 설정됩니다. null 종결 문자를 포함하는 경로의 길이가 `maxlen`을 초과하는 경우 오류가 발생하고 `errno` 가 `ERANGE`로 설정됩니다. 이러한 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_getdcwd` 함수는 지정된 드라이브에 있는 현재 작업 디렉터리의 전체 경로를 가져오고 `buffer`에 저장합니다. 현재 작업 디렉터리가 루트로 설정되는 경우 문자열이 백슬래시(\\)로 끝납니다. 현재 작업 디렉터리가 루트 이외의 디렉터리로 설정되는 경우 문자열은 백슬래시가 아닌 디렉터리의 이름으로 끝납니다.  
  
 `_wgetdcwd` 가 `_getdcwd`의 와이드 문자 버전이고 해당 `buffer` 매개 변수 및 반환 값이 와이드 문자열입니다. 그렇지 않으면 `_wgetdcwd` 과 `_getdcwd` 은 동일하게 작동합니다.  
  
 이 함수는 자체적으로 스레드로부터 안전하지 않는 **GetFullPathName**에 의존하지만 스레드로부터 안전합니다. 그러나 다중 스레드 응용 프로그램에서 이 함수와 **GetFullPathName**을 모두 호출하는 경우 스레드 안전성을 위반할 수 있습니다. 자세한 내용을 보려면 [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542) 로 이동한 다음 **GetFullPathName**입니다.  
  
 `_nolock` 접미사가 있는 이 함수의 버전은 이 함수와 동일하게 작동합니다. 단, 스레드로부터 안전하지 않고 다른 스레드의 간섭으로부터 보호받지 않습니다. 자세한 내용은 [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)을 참조하세요.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC` 이 정의될 때 `_getdcwd` 및 `_wgetdcwd` 에 대한 호출이 `_getdcwd_dbg` 및 `_wgetdcwd_dbg` 에 대한 호출에 의해 대체되므로 메모리 할당을 디버그할 수 있습니다. 자세한 내용은[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_getdcwd`|\<direct.h>|  
|`_wgetdcwd`|\<direct.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_getdrive](../../c-runtime-library/reference/getdrive.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
