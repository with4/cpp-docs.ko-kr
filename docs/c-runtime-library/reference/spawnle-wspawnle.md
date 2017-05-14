---
title: _spawnle, _wspawnle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _spawnle
- _wspawnle
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- spawnle
- _spawnle
- wspawnle
- _wspawnle
dev_langs:
- C++
helpviewer_keywords:
- spawnle function
- processes, creating
- _wspawnle function
- processes, executing new
- process creation
- wspawnle function
- _spawnle function
ms.assetid: 80308892-2815-49b1-8cca-53894c366f5a
caps.latest.revision: 17
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
ms.openlocfilehash: 4607528d5e7d5bdeb71c560f8f5890fe469a531e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="spawnle-wspawnle"></a>_spawnle, _wspawnle
새 프로세스를 만들고 실행합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
intptr_t _spawnle(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnle(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mode`  
 호출 프로세스의 실행 모드입니다.  
  
 `cmdname`  
 실행할 파일의 경로입니다.  
  
 `arg0, arg1, ... argn`  
 인수에 대한 포인터 목록입니다. `arg0` 인수는 일반적으로 `cmdname`에 대한 포인터입니다. `arg1` - `argn` 인수는 새 인수 목록을 구성하는 문자열에 대한 포인터입니다. `argn`다음에는 인수 목록의 끝을 표시하는 `NULL` 포인터가 와야 합니다.  
  
 `envp`  
 환경 설정에 대한 포인터 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 동기 `_spawnle` 또는 `_wspawnle`(`mode`에 대해 지정된 `_P_WAIT`)에서 반환되는 값은 새 프로세스의 종료 상태입니다. 비동기 `_spawnle` 또는 `_wspawnle` (`_P_NOWAIT` 에 대해 지정된 `_P_NOWAITO` 또는 `mode`)에서 반환되는 값은 프로세스 핸들입니다. 프로세스가 정상적으로 종료되는 경우 종료 상태는 0입니다. 생성된 프로세스가 0이 아닌 인수를 가진 `exit` 루틴을 호출하는 경우에만 종료 상태를 0이 아닌 값으로 설정할 수 있습니다. 새 프로세스가 양수 값의 종료 상태를 명시적으로 설정하지 않은 경우, 양수 값의 종료 상태는 중단되거나 인터럽트된 비정상적인 종료를 나타냅니다. 반환 값이-1 (새 프로세스가 시작 되지 않습니다.) 오류를 나타냅니다. 이 경우 `errno` 는 다음 값 중 하나로 설정됩니다.  
  
 `E2BIG`  
 인수 목록이 1024바이트를 초과합니다.  
  
 `EINVAL`  
 `mode` 인수가 잘못되었습니다.  
  
 `ENOENT`  
 파일 또는 경로를 찾을 수 없습니다.  
  
 `ENOEXEC`  
 지정한 파일이 실행할 수 없거나 실행 파일 형식이 잘못되었습니다.  
  
 `ENOMEM`  
 메모리가 부족하여 새 프로세스를 실행할 수 없습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 이러한 각 함수는 각각의 명령줄 인수를 별도의 매개 변수로 전달하고 포인터 배열을 환경 설정에 전달하는 새 프로세스를 만들고 실행합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `cmdname` 또는 `arg0`이 빈 문자열이나 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL`로 설정하고 -1을 반환합니다. 새로운 프로세스가 생성되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_spawnle`|\<process.h>|  
|`_wspawnle`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
