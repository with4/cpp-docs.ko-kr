---
title: system, _wsystem | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- system
- _wsystem
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tsystem
- _wsystem
dev_langs:
- C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3d46fd4b4df463bfce940360744a0a548652e2b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="system-wsystem"></a>system, _wsystem
명령을 실행합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `command`  
 실행할 명령입니다.  
  
## <a name="return-value"></a>반환 값  
 `command`가 `NULL`이고 명령 인터프리터가 발견되면 0이 아닌 값을 반환합니다. 명령 인터프리터가 없으면 0을 반환하고 `errno`를 `ENOENT`로 설정합니다. `command`가 `NULL`, `system`이 아닐 경우 명령 인터프리터에 의해 반환되는 값을 반환합니다. 명령 인터프리터가 값 0을 반환할 때만 값 0을 반환합니다. 반환 값은-1은 오류를 나타내며 및 `errno` 다음 값 중 하나로 설정 됩니다.  
  
 `E2BIG`  
 인수 목록(시스템에 따라 다름)이 너무 큽니다.  
  
 `ENOENT`  
 명령 인터프리터를 찾을 수 없습니다.  
  
 `ENOEXEC`  
 명령 인터프리터 파일 형식이 올바르지 않아서 실행할 수 없습니다.  
  
 `ENOMEM`  
 메모리가 부족하여 명령을 실행할 수 없습니다. 사용 가능한 메모리가 손상되었거나 잘못된 블록이 있습니다. 이는 호출 프로세스가 제대로 할당되지 않았음을 나타냅니다.  
  
 이러한 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `system` 함수는 `command`를 명령 인터프리터로 전달합니다. 그러면 문자열이 운영 체제 명령으로 실행됩니다. `system`은 `COMSPEC` 및 `PATH` 환경 변수를 사용하여 명령 인터프리터 파일 CMD.exe를 찾습니다. `command`가 `NULL`일 경우 함수는 명령 인터프리터가 존재하는지 확인합니다.  
  
 `fflush`을 호출하기 전에 `_flushall` 또는 `system`을 사용하여 스트림을 명시적으로 비우거나 닫아야 합니다.  
  
 `_wsystem`은 `system`의 와이드 문자 버전이며, `command`에 대한 `_wsystem` 인수는 와이드 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`system`|\<process.h> 또는 \<stdlib.h>|  
|`_wsystem`|\<process.h>, \<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 이 예제에서는 `system`을 사용하여 텍스트 파일을 입력합니다.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## <a name="input-crtsystemtxt"></a>입력: crt_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>출력  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)