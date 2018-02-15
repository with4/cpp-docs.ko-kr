---
title: "_execle, _wexecle | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _execle
- _wexecle
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
- wexecle
- _execle
- _wexecle
dev_langs:
- C++
helpviewer_keywords:
- wexecle function
- execle function
- _wexecle function
- _execle function
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d463530f7c7248ffa07d95f6a5b409699245473a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="execle-wexecle"></a>_execle, _wexecle
새 자식 프로세스를 로드하고 실행합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
intptr_t _execle(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexecle(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const char *const *envp   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cmdname`  
 실행할 파일의 경로입니다.  
  
 `arg0, ... argn`  
 매개 변수에 대한 포인터 목록입니다.  
  
 `envp`  
 환경 설정에 대한 포인터 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 이러한 함수는 호출 프로세스에 값을 반환하지 않습니다. 반환 값이-1은 오류를 나타내며이 경우는 `errno` 전역 변수가 설정 됩니다.  
  
|`errno` 값|설명|  
|-------------------|-----------------|  
|`E2BIG`|인수 및 환경 설정에 필요한 공간의 크기가 32KB를 초과합니다.|  
|`EACCES`|지정한 파일이 잠금 또는 공유 위반이 되었습니다.|  
|`EINVAL`|잘못된 매개 변수입니다.|  
|`EMFILE`|너무 많은 파일이 열려 있습니다. 실행 파일인지 여부를 확인하려면 지정한 파일이 열려 있어야 합니다.|  
|`ENOENT`|파일 또는 경로를 찾을 수 없습니다.|  
|`ENOEXEC`|지정한 파일이 실행할 수 없거나 실행 파일 형식이 잘못되었습니다.|  
|`ENOMEM`|메모리가 부족하여 새 프로세스를 실행할 수 없습니다. 사용 가능한 메모리가 손상되었거나 잘못된 블록이 있습니다. 이는 호출 프로세스가 제대로 할당되지 않았음을 나타냅니다.|  
  
 이러한 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 이러한 각 함수는 새 프로세스를 로드 및 실행하고, 각 명령줄 인수를 별도의 매개 변수로 전달하고, 포인터 배열을 환경 설정으로 전달합니다.  
  
 `_execle` 함수는 자신의 매개 변수에 대한 유효성을 검사합니다. `cmdname` 또는 `arg0`이 null 포인터이거나 빈 문자열인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 -1을 반환합니다. 새 프로세스가 시작되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|선택적 헤더|  
|--------------|---------------------|---------------------|  
|`_execle`|\<process.h>|\<errno.h>|  
|`_wexecle`|\<process.h> 또는 \<wchar.h>|\<errno.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)