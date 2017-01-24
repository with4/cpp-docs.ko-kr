---
title: "abort | Microsoft Docs"
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
  - "abort"
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
  - "Abort"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "abort 함수"
  - "현재 프로세스 중단"
  - "프로세스, 중단"
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# abort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 프로세스를 중단하고 오류 코드를 반환합니다.  
  
> [!NOTE]
>  테스트 또는 디버깅 시나리오에서를 제외하고는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 종료하기 위해 이 메서드를 사용하지 마십시오.  프로그래밍 또는 UI 방식으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 닫는 것은 [Windows 8 응용 프로그램 인증 요구 사항](http://go.microsoft.com/fwlink/?LinkId=262889)에 따라 허용되지 않습니다.  자세한 내용은 [응용 프로그램 수명 주기\(Windows 스토어 응용 프로그램\)](http://go.microsoft.com/fwlink/?LinkId=262853)를 참조하십시오.  
  
## 구문  
  
```  
void abort( void );  
```  
  
## 반환 값  
 `abort`는 호출 프로세스에 컨트롤을 반환하지 않습니다.  기본적으로 중단 신호 처리기에 대해 점검하고 하나가 설정된 경우 `SIGABRT`을 발생시킵니다.  그런 다음 `abort`는 현재 프로세스를 종료하고 부모 프로세스 종료 코드를 반환합니다.  
  
## 설명  
 **Microsoft 전용**  
  
 기본적으로 디버그 런타임 라이브러리를 사용하여 응용 프로그램이 빌드되면 `abort` 루틴은 `SIGABRT`이 발생되기 전에 오류 메시지를 표시합니다.  콘솔 모드에서 실행되는 콘솔 응용 프로그램의 경우 `STDERR`로 메시지를 보냅니다.  창 모드로 실행 중인 Windows 데스크톱 응용 프로그램 및 콘솔 응용 프로그램은 메시지 상자에 메시지를 표시합니다.  메시지를 표시하지 않으려면 [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md)를 사용해서 `_WRITE_ABORT_MSG` 플래그를 지웁니다.  표시되는 메시지 버전은 사용하는 런타임 환경에 따라 달라집니다.  최신 버전의 Visual C\+\+를 사용하여 빌드한 응용 프로그램에 대한 메시지는 다음과 같습니다.  
  
 `R6010`  
  
 `- abort() has been called`  
  
 C 런타임 라이브러리의 이전 버전에서는 이 메시지가 표시되었습니다.  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 프로그램을 디버그 모드에서 컴파일하면 메시지 상자에 **중단**, **시도** 또는 **무시** 옵션이 표시됩니다.  사용자가 **중단**을 선택하면 프로그램이 즉시 종료되고 종료 코드 3을 반환합니다.  사용자가 **다시 시도**를 선택하면 가능한 경우 just\-in\-time 디버깅을 위해 디버거가 호출됩니다.  사용자가 **무시**를 선택하면 `abort`이 정상적인 처리를 계속합니다.  
  
 일반 정품 및 디버그 빌드 모두에서 `abort`이 중단 신호 처리기가 설정되어 있는지 여부를 확인합니다.  기본값이 아닌 신호 처리기가 설정된 경우 `abort`이 `raise(SIGABRT)`을 호출합니다.  [signal](../../c-runtime-library/reference/signal.md) 함수를 사용하여 중단 신호 처리기 함수를 `SIGABRT` 신호와 연결합니다.  예를 들어 리소스 정리 또는 정보 기록과 같은 사용자 지정 작업을 수행하고, 처리기 함수에서 고유의 오류 코드를 사용하여 응용 프로그램을 종료할 수 있습니다.  사용자 정의 신호 처리기를 정의되지 않은 경우 `abort`이 `SIGABRT` 신호를 발생시키지 않습니다.  
  
 기본적으로 데스크톱이나 콘솔 응용 프로그램의 디버그가 아닌 빌드에서 `abort`는 Windows 오류 보고 메커니즘을 호출합니다\(Dr.  다시 호출하여 오류를 Microsoft에 보고합니다.  `_set_abort_behavior`을 호출하고 `_CALL_REPORTFAULT` 플래그를 설정 및 마스크하여 이 동작을 사용하거나 사용하지 않을 수 있습니다.  플래그가 설정되면 Windows에는 "문제가 발생하여 프로그램이 올바르게 작동하지 못했습니다."와 같은 텍스트가 있는 메시지 상자가 표시됩니다. 사용자는 **디버그** 단추로 디버거를 호출하도록 선택하거나 **프로그램 닫기** 단추를 선택하여 운영 체제에서 정의한 오류 코드가 있는 응용 프로그램을 종료하도록 할 수 있습니다.  
  
 Windows 오류 보고 처리기가 호출되지 않은 경우 `abort`는 [\_exit](../../c-runtime-library/reference/exit-exit-exit.md)을 호출하여 종료 코드 3과 함께 프로세스를 종료하고 컨트롤을 부모 프로세스 또는 운영 체제로 반환합니다.  `_exit`은 스트림 버퍼를 플러시하지 않거나 `atexit`\/`_onexit` 처리를 플러시합니다.  
  
 CRT 디버깅에 대한 자세한 내용은 [CRT 디버깅 기술](../Topic/CRT%20Debugging%20Techniques.md)을 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`abort`|\<process.h\> 또는 \<stdlib.h\>|  
  
## 예제  
 다음 프로그램 파일을 열려고 시도하고 시도가 실패하면 중단합니다.  
  
```c  
// crt_abort.c  
// compile with: /TC  
// This program demonstrates the use of  
// the abort function by attempting to open a file  
// and aborts if the attempt fails.  
  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    FILE    *stream = NULL;  
    errno_t err = 0;  
  
    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );  
    if ((err != 0) || (stream == NULL))  
    {  
        perror( "File could not be opened" );  
        abort();  
    }  
    else  
    {  
        fclose( stream );  
    }  
}  
```  
  
  **파일을 열 수 없습니다. 해당 파일 또는 디렉터리가 아님**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [abort 사용](../../cpp/using-abort.md)   
 [abort 함수](../../c-language/abort-function-c.md)   
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [신호](../../c-runtime-library/reference/signal.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [\_DEBUG](../../c-runtime-library/debug.md)   
 [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md)