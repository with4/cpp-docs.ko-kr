---
title: "_getcwd_dbg, _wgetcwd_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
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
ms.openlocfilehash: 9814916e32878a1e1a11f534fce64aeaf2f6a57e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg
[_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) 함수의 디버그 버전입니다(디버그 중에만 사용 가능).  
  
## <a name="syntax"></a>구문  
  
```  
char *_getcwd_dbg(   
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetcwd_dbg(   
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 경로의 저장소 위치입니다.  
  
 `maxlen`  
 경로의 최대 길이(문자 수)로 `char`의 경우 `_getcwd_dbg`자, `wchar_t`의 경우 `_wgetcwd_dbg`자입니다.  
  
 `blockType`  
 요청된 메모리 블록 형식으로 `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`입니다.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 `buffer`에 대한 포인터를 반환합니다. `NULL` 반환 값은 오류를 나타내고 `errno` 는 `ENOMEM`으로 설정되어 `maxlen` 바이트를 할당할 메모리가 부족함을 나타내거나( `NULL` 인수가 `buffer`로 지정된 경우) `ERANGE`로 설정되어 경로가 `maxlen` 자보다 긺을 나타냅니다.  
  
 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_getcwd_dbg` 및 `_wgetcwd_dbg` 함수는 동일 `_getcwd` 및 `_wgetcwd` 점을 제외 하 고, `_DEBUG` 는 디버그 버전의를 사용 하 여 이러한 함수를 정의 `malloc` 및 `_malloc_dbg` 메모리를 할당 하는 경우 `NULL` 첫 번째 매개 변수로 전달 됩니다. 자세한 내용은 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)를 참조하세요.  
  
 대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 `_CRTDBG_MAP_ALLOC` 플래그를 정의할 수 있습니다. `_CRTDBG_MAP_ALLOC`을 정의하면 `_getcwd` 및 `_wgetcwd`에 대한 호출이 각각 `_getcwd_dbg` 및 `_wgetcwd_dbg`로 다시 매핑되고 `blockType`은 `_NORMAL_BLOCK`으로 설정됩니다. 따라서 힙 블록을 `_CLIENT_BLOCK`으로 표시하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
## <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_getcwd_dbg`|\<crtdbg.h>|  
|`_wgetcwd_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
