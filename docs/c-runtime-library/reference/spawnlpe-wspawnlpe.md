---
title: "_spawnlpe, _wspawnlpe | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_spawnlpe"
  - "_wspawnlpe"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "spawnlpe"
  - "_wspawnlpe"
  - "_spawnlpe"
  - "wspawnlpe"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_spawnlpe 함수"
  - "_wspawnlpe 함수"
  - "프로세스 만들기"
  - "프로세스, 만들기"
  - "프로세스, 새로 실행"
  - "spawnlpe 함수"
  - "wspawnlpe 함수"
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _spawnlpe, _wspawnlpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

새 프로세스를 만들고 실행합니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
intptr_t _spawnlpe(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnlpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### 매개 변수  
 `mode`  
 호출 프로세스의 실행 모드입니다.  
  
 `cmdname`  
 실행할 파일의 경로입니다.  
  
 `arg0, arg1, ... argn`  
 인수에 대한 포인터 목록입니다.  `arg0` 인수는 일반적으로 `cmdname`에 대한 포인터입니다.  `arg1` \- `argn` 인수는 새 인수 목록을 구성하는 문자열에 대한 포인터입니다.  `argn` 다음에는 인수 목록의 끝을 표시하는 `NULL` 포인터가 와야 합니다.  
  
 `envp`  
 환경 설정에 대한 포인터 배열입니다.  
  
## 반환 값  
 동기 `_spawnlpe` 또는 `_wspawnlpe`\(`mode`에 대해 지정된 `_P_WAIT`\)에서 반환되는 값은 새 프로세스의 종료 상태입니다.  비동기 `_spawnlpe` 또는 `_wspawnlpe`\(`mode`에 대해 지정된 `_P_NOWAIT` 또는 `_P_NOWAITO`\)에서 반환되는 값은 프로세스 핸들입니다.  프로세스가 정상적으로 종료되는 경우 종료 상태는 0입니다.  생성된 프로세스가 0이 아닌 인수를 사용하여 `exit` 루틴을 호출하는 경우 종료 상태를 0이 아닌 값으로 설정할 수 있습니다.  새 프로세스가 양수 값의 종료 상태를 명시적으로 설정하지 않은 경우, 양수 값의 종료 상태는 중단 또는 인터럽트로 인한 비정상적인 종료를 나타냅니다.  반환 값 \-1은 새 프로세스가 시작되지 않은 오류를 나타냅니다.  이 경우 `errno`는 다음 값 중 하나로 설정됩니다.  
  
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
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 이러한 각 함수는 새 프로세스를 만들어 실행하고, 각 명령줄 인수를 별도의 매개 변수로 전달하고, 포인터 배열을 환경 설정으로 전달합니다.  이러한 함수는 `PATH` 환경 변수를 사용하여 실행할 파일을 찾습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  `cmdname` 또는 `arg0`가 빈 문자열이나 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  새로운 프로세스가 생성되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_spawnlpe`|\<process.h\>|  
|`_wspawnlpe`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)의 예제를 참조하세요.  
  
## 해당 .NET Framework 항목  
  
-   [System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)