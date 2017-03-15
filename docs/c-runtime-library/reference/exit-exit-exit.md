---
title: "exit, _Exit, _exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_exit"
  - "exit"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "Exit"
  - "_exit"
  - "process/exit"
  - "process/_Exit"
  - "stdlib/exit"
  - "stdlib/_Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit 함수"
  - "_exit 함수"
  - "프로세스, 종료"
  - "함수 호출, 종료"
  - "프로세스 종료, 호출"
ms.assetid: b1501fa6-27c2-478c-9e93-cc4fd802a01f
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# exit, _Exit, _exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

호출 프로세스를 종료합니다.`exit` 함수는 정리 후 종료합니다. `_exit` 및 `_Exit`는 즉시 종료합니다.  
  
> [!NOTE]
>  테스트 또는 디버깅 시나리오를 제외하고 UWP\(유니버설 Windows 플랫폼\) 앱 또는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱을 종료하기 위해 이 메서드를 사용하지 마세요. 프로그래밍 또는 UI 방식으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱을 닫을 수 없습니다. Windows 8 및 8.1 앱에 대한 자세한 내용은 [앱 수명 주기](http://go.microsoft.com/fwlink/?LinkId=262853)를 참조하세요. Windows 10 앱에 대한 자세한 내용은 [Windows 10 앱에 대한 방법 가이드](http://go.microsoft.com/fwlink/p/?linkid=619133)를 참조하세요.  
  
## 구문  
  
```  
void exit(   
   int const status   
);  
void _Exit(   
   int const status   
);  
void _exit(   
   int const status   
);  
```  
  
#### 매개 변수  
 `status`  
 종료 상태 코드입니다.  
  
## 설명  
 `exit`, `_Exit` 및 `_exit` 함수는 호출 프로세스를 종료합니다.`exit` 함수는 스레드 로컬 개체에 대해 소멸자를 호출한 다음 `atexit` 및 `_onexit`에 의해 등록된 함수를 LIFO\(후입선출\) 순서로 호출하고 프로세스를 종료하기 전에 모든 파일 버퍼를 플러시합니다.`_Exit` 및 `_exit` 함수는 스레드 로컬 개체를 삭제하거나 `atexit` 또는 `_onexit` 함수를 처리하지 않고 스트림 버퍼를 플러시하지 않은 상태로 프로세스를 종료합니다.  
  
 `exit`, `_Exit` 및 `_exit` 호출은 값을 반환하지 않지만 프로세스가 종료된 후 호스트 환경 또는 호출 대기 프로세스\(있는 경우\)에서 `status`의 낮은 순서 바이트를 사용할 수 있습니다. 일반적으로 호출자는 `status` 값을 0으로 설정하여 정상 종료를 나타내거나 다른 값으로 설정하여 오류를 나타냅니다.`status` 값은 운영 체제 일괄 처리 명령 `ERRORLEVEL`에 제공되며, 값 0을 나타내는 `EXIT_SUCCESS` 또는 값 1을 나타내는 `EXIT_FAILURE`의 두 상수 중 하나로 표현됩니다.  
  
 `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit` 및 `_c_exit` 함수는 다음과 같이 동작합니다.  
  
|함수|설명|  
|--------|--------|  
|`exit`|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|  
|`_Exit`|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|  
|`_exit`|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|  
|`quick_exit`|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|  
|`_cexit`|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|  
|`_c_exit`|최소 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|  
  
 `exit`, `_Exit` 또는 `_exit` 함수를 호출하는 경우 호출 시 존재하는 임시 또는 자동 개체에 대한 소멸자가 호출되지 않습니다. 자동 개체는 개체가 정적으로 선언되지 않은 함수에서 정의됩니다. 임시 개체는 컴파일러에 의해 생성된 개체입니다.`exit`, `_Exit` 또는 `_exit`를 호출하기 전에 자동 개체를 삭제하려면 다음과 같이 개체에 대한 소멸자를 명시적으로 호출합니다.  
  
```  
myObject.myClass::~myClass();  
```  
  
 `DLL_PROCESS_ATTACH`를 사용하여 `DllMain`에서 `exit`를 호출하지 마세요.`DLLMain` 함수를 종료하려는 경우 `DLL_PROCESS_ATTACH`에서 `FALSE`를 반환합니다.  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`exit`, `_Exit`, `_exit`|\<process.h\> 또는 \<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 예제  
  
```  
// crt_exit.c // This program returns an exit code of 1. The // error code could be tested in a batch file. #include <stdlib.h> int main( void ) { exit( 1 ); }  
```  
  
## 해당 .NET Framework 항목  
 [System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_cexit, \_c\_exit](../../c-runtime-library/reference/cexit-c-exit.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [quick\_exit](../../c-runtime-library/reference/quick-exit1.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)