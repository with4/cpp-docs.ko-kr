---
title: "_spawnvpe, _wspawnvpe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_spawnvpe"
  - "_wspawnvpe"
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
  - "_spawnvpe"
  - "wspawnvpe"
  - "spawnvpe"
  - "_wspawnvpe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_spawnvpe 함수"
  - "_wspawnvpe 함수"
  - "프로세스 만들기"
  - "프로세스, 만들기"
  - "프로세스, 새로 실행"
  - "spawnvpe 함수"
  - "wspawnvpe 함수"
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _spawnvpe, _wspawnvpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

새 프로세스를 만들고 실행합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
intptr_t _spawnvpe(  
   int mode,  
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wspawnvpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### 매개 변수  
 `mode`  
 호출 프로세스의 실행 모드입니다.  
  
 `cmdname`  
 실행할 파일의 경로입니다.  
  
 `argv`  
 인수에 대한 포인터 배열입니다.  인수 `argv`\[0\]는 일반적으로 경로에 대 한 포인터 또는 프로그램 이름을 리얼 모드에서 보호 모드로 하고 `argv`\[1\]를 통해 `argv`\[`n`\]새 인수 목록 구성 문자열에 대 한 포인터입니다.  인수 `argv`\[`n` \+1\]은 인수 목록의 끝을 표시하는 `NULL` 포인터여야 합니다.  
  
 `envp`  
 환경 설정에 대한 포인터 배열입니다.  
  
## 반환 값  
 동기의 반환 값 `_spawnvpe` 또는 `_wspawnvpe` 은 \(\_`_P_WAIT` 지정된 `mode`\) 새 프로세스의 종료 상태입니다.  비동기 작업의 반환 값 `_spawnvpe` 또는 `_wspawnvpe` 은 \(`_P_NOWAIT` 또는 `_P_NOWAITO` 지정된 `mode`\) 프로세스 핸들입니다.  프로세스가 정상적으로 종료되는 경우 종료 상태는 0입니다.  생성된 프로세스가 0이 아닌 인수를 가진 `exit` 루틴을 호출하는 경우에만 종료 상태를 0이 아닌 값으로 설정할 수 있습니다.  새 프로세스가 양수 값의 종료 상태를 명시적으로 설정하지 않은 경우, 양수 값의 종료 상태는 중단되거나 인터럽트된 비정상적인 종료를 나타냅니다.  반환 값 \-1은 새 프로세스가 시작되지 않은 오류를 나타냅니다.  이 경우 `errno` 는 다음 값 중 하나로 설정됩니다.  
  
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
  
 이러한 반환 코드와 다른 반환코드에 대한 자세한 정보는 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 각각의 이러한 함수는 새 프로세스를 만들고 실행합니다, 명령줄 인수 포인터 배열과 환경 설정 포인터 배열을 실행합니다.  이러한 함수는 `PATH` 환경 변수를 사용하여 실행할 파일을 찾습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  `cmdname` 또는 `argv` 가 null 포인터인 경우 `argv` null 포인터를 가르키는 경우, 또는 `argv[0]` 이 빈 문자열인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못 된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  새로운 프로세스가 생성되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_spawnvpe`|\<stdio.h\> 또는 \<process.h\>|  
|`_wspawnvpe`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## 참고 항목  
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)