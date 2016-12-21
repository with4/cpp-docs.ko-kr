---
title: "_execl, _wexecl | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execl"
  - "_wexecl"
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
  - "_execl"
  - "_wexecl"
  - "wexecl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_execl 함수"
  - "_wexecl 함수"
  - "execl 함수"
  - "wexecl 함수"
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _execl, _wexecl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

새 자식 프로세스를 로드하고 실행합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### 매개 변수  
 `cmdname`  
 실행할 파일의 경로입니다.  
  
 `arg0`, `...``argn`  
 목록 매개 변수에 대한 포인터입니다.  
  
## 반환 값  
 성공하면 이러한 함수는 호출 프로세스에 값을 반환하지 않습니다.  반환 값 \-1은 오류를 나타내며, 이 경우 `errno` 전역 변수가 설정됩니다.  
  
|errno 값|설명|  
|-------------|--------|  
|`E2BIG`|인수 및 환경 설정에 필요한 공간의 크기가 32KB를 초과합니다.|  
|`EACCES`|지정한 파일이 잠금 또는 공유 위반이 되었습니다.|  
|`EINVAL`|잘못된 매개 변수 \(매개 변수 중 하나 이상을 포인터를 null 또는 빈 문자열\)입니다.|  
|`EMFILE`|실행 파일인지 여부를 확인하려면 지정한 파일이 열려 있어야 하지만, 열려 있는 파일이 너무 많습니다.|  
|`ENOENT`|파일 또는 경로는 찾을 수 없습니다.|  
|`ENOEXEC`|지정한 파일이 실행할 수 없거나 실행 파일 형식이 잘못되었습니다.|  
|`ENOMEM`|메모리가 부족하여 새 프로세스를 실행할 수 없습니다. 사용 가능한 메모리가 손상되었거나 잘못된 블록이 있습니다. 이는 호출 프로세스가 제대로 할당되지 않았음을 나타냅니다.|  
  
## 설명  
 각 함수는 별도의 매개 변수로써 각 명령룰 인수를 통과하는 새로운 프로세스로 로드하고 실행합니다.  첫 번째 인수는 명령 또는 실행 파일 이름 및 두 번째 인수는 첫 번째 동일하게 합니다.  이 `argv[0]` 에서 실행된 프로세스입니다.  세 번째 인수를 첫 번째 인수 `argv[1]`, 실행되는 프로세스입니다.  
  
 이러한 `_execl` 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  null 포인터 혹은 빈 문자열인 `cmdname` 혹은 `arg0` 어느쪽의 경우, 이들 함수는 계속 실행이 혀용되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로써 설명된 잘못된 매개변수 처리기를 호출하는데, 이들 함수는 `errno` 를 `EINVAL` 을 설정하고 \-1을 반환합니다.  새로운 프로세스는 실행되지 않습니다.  
  
## 요구 사항  
  
|Function|필수 헤더|선택적 헤더|  
|--------------|-----------|------------|  
|`_execl`|\<process.h\>|\<\<errno.h\>\>|  
|`_wexecl`|\<process.h\> 또는 \<wchar.h\>|\<\<errno.h\>\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)