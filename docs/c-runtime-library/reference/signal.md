---
title: "신호 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "signal"
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
  - "signal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "신호 함수"
ms.assetid: 094118de-d789-4063-b4f4-cffcc80bf29d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# 신호
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

신호 처리 중단을 설정합니다.  
  
> [!IMPORTANT]
>  테스트 또는 디버깅 시나리오에서를 제외하고는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 종료하기 위해 이 메서드를 사용하지 마십시오.  프로그래밍 또는 UI 방식으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 닫는 것은 [Windows 8 응용 프로그램 인증 요구 사항](http://go.microsoft.com/fwlink/?LinkId=262889)의 섹션 3.6에 따라서 허용되지 않습니다.  자세한 내용은 [응용 프로그램 수명 주기\(Windows 스토어 응용 프로그램\)](http://go.microsoft.com/fwlink/?LinkId=262853)를 참조하십시오.  
  
## 구문  
  
```  
void (__cdecl *signal(  
   int sig,   
   void (__cdecl *func ) (int [, int ] )))   
   (int);  
```  
  
#### 매개 변수  
 `sig`  
 신호 값입니다.  
  
 `func`  
 실행될 함수입니다.  첫 번째 매개 변수는 신호 값이고 두 번째 매개 변수는 첫 번째 매개 변수가 SIGFPE일 때 사용할 수 있는 하위 코드입니다.  
  
## 반환 값  
 `signal` 는 주어진 신호와 연관된 `func` 의 이전 값을 반환합니다.  예를 들어, `func` 의 이전 값이 `SIG_IGN`였을 경우, 반환 값은 또한 `SIG_IGN`입니다.  `SIG_ERR` 의 반환 값은 오류를 나타냅니다; 이 경우, `errno` 는 `EINVAL` 에 설정합니다.  
  
 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 `signal` 함수는 프로세스가 운영 체제에서 인터럽트 신호를 처리하기 위해 여러 가지 방법 중 하나를 선택하도로고 합니다.  `sig` 인수는 `signal` 가 응답는 인터럽트 입니다; 신호에 정의 된 다음 매니페스트 상수 중 하나 여야 합니다.  
  
|`sig` 값|설명|  
|-------------|--------|  
|`SIGABRT`|Abnormal termination|  
|`SIGFPE`|부동 소수점 오류|  
|`SIGILL`|잘못된 명령|  
|`SIGINT`|CTRL \+ C 신호|  
|`SIGSEGV`|잘못된 저장소 액세스|  
|`SIGTERM`|종료 요청|  
  
 `sig` 가 이 위의 값이 아닐 경우, 잘못 된 매개 변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 정의된 대로 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `SIG_ERR`을 반환합니다.  
  
 기본적으로, `signal` 은 `sig`의 값에 관계없이 종료 코드 3 값에 호출 프로그램을 종료합니다.  
  
> [!NOTE]
>  `SIGINT` 는 Win32 응용 프로그램에 대해 지원되지 않습니다.  CTRL \+ C 인터럽트가 발생할 때, Win32 운영 체제는 특히 해당 인터럽트를 처리하기 위해 새 스레드를 생성합니다.  UNIX와 같이 단일 스레드 응용 프로그램을 생성하여 다중 스레드 및 예기치 않은 동작이 발생할 수 있습니다.  
  
 `func` 인수는 신호 처리기를 작성하는 주소이거나 미리 정의 된 상수 `SIG_DFL` 중 하나이거나 SIGNAL.H에 정의된 `SIG_IGN` 입니다.  만약 `func` 이 함수이면, 주어진 신호에 대해 신호 처리기에서 함께 설치됩니다.  신호 처리기의 프로토타입은 필요 하나 정식 인수, `int` 형의 `sig`가 필요합니다.  운영 체제 시스템은 중단이 발생할 때 `sig` 를 통해 실제 인수를 제공합니다; 인수는 인터럽트를 생성하는 신호입니다.  따라서 인터럽트 발생을 결정하고 적절한 조치를 취하는 신호 처리기에서 \(앞의 표에 나열된\) 여섯개의 매니페스트 상수를 사용할 수 있습니다.  예를 들어, `signal` 를 두번 호출하여 두 개의 서로 다른 신호를 동일한 처리기에 할당하고, `sig` 인수를 처리기에서 수신 신호에 따라 다른 작업에서 테스트합니다.  
  
 부동 소수점 예외\(`SIGFPE`\)를 테스트하는 경우, `func` 는 FLOAT.H에 정의된 `FPE_xxx` 형태의 매니페스트 상수 중 하나인 두 번째 선택적 인수를 취하는 함수를 가리킵니다.  `SIGFPE` 신호가 발생할 때, 부동 소수점 예외의 종류를 확인하고 적절 한 조치를 취할 수 있는 두 번째 인수의 값을 테스트할 수 있습니다.  이 인수와 가능한 값은 Microsoft 확장입니다.  
  
 부동 소수점 예외 값에 대한, `func` 의 값은 신호가 수신 될 때 다시 설정되지 않습니다.  부동 소수점 예외를 복구하려면, 부동 소수점 작업을 가리키기 위해 try\/절 제외를 사용합니다.  [setjmp](../../c-runtime-library/reference/setjmp.md) 와 [longjmp](../../c-runtime-library/reference/longjmp.md)를 사용하여 복구하는 것이 가능합니다.  두 경우 모두에서 프로세스 호출은 실행을 다시 시작하고 정의되지 않은 프로세스의 부동 소수점 상태를 남깁니다.  
  
 신호 처리기가 반환하면 프로세스 호출은 인터럽트 신호를 받은 직후 실행을 다시 시작합니다.  신호 또는 운영 모드의 종류에 관계없이 사실입니다.  
  
 지정된 함수가 실행되기 전에 `func` 의 값을 `SIG_DFL` 에 설정합니다.  `signal` 지정자를 호출하지 않는 한, 다음 인터럽트 신호는 `SIG_DFL`에서 설명된 대로 처리됩니다.  호출된 함수에서 신호를 다시 설정 하려면 이 기능을 사용할 수 있습니다.  
  
 일반적으로 신호 처리기 루틴 인터럽트를 발생 하는 경우 비동기적으로 호출되므로, 신호 처리기 함수는 런타임 작업이 불완전하며 알 수 없는 상태에 있을 때, 컨트롤을 얻을 수 있습니다.  다음에 사용자 신호 처리기 루틴에서 사용할 수 있는 기능을 결정하는 제한 사항이 요약되어 있습니다.  
  
-   STDIO.H I\/O 루틴 \(예를 들어, `printf` 또는 `fread`\) 이나 하위 문제를 만들지 마시오.  
  
-   힙 루틴 또는 힙 루틴이 사용하는 루틴을 호출 하지 마십시오 \(예를 들어, `malloc`, `_strdup`, 또는 `_putenv`\).  자세한 내용은 [malloc](../../c-runtime-library/reference/malloc.md)를 참조하십시오.  
  
-   시스템 호출을 생성하는 함수를 사용하지 마십시오 \(예를 들어, `_getcwd` 또는 `time`\).  
  
-   부동 소수점 예외에 의해 인터럽트가 발생되지 않는 한, `longjmp` 를 사용하지 마십시오.\(즉, `sig` 는 `SIGFPE`입니다\).  이 경우에, 먼저 `_fpreset` 을 호출하여 부동 소수점 패키지를 먼저 초기화합니다.  
  
-   모든 오버레이 루틴을 사용하지 마십시오.  
  
 함수를 사용하여 `SIGFPE` 예외에 트래핑 하는 경우, 프로그램은 부동 소수점 코드를 포함 해야 합니다.  프로그램이 부동 소수점 코드를 갖고 있지 않고 런타임 라이브러리의 신호 처리 코드가 필요한 경우, 휘발성 더블을 선언하고 0으로 초기화합니다.  
  
```  
volatile double d = 0.0f;   
```  
  
 `SIGILL` 및 `SIGTERM` 신호는 Windows에서 생성되지 않습니다.  ANSI 호환성을 위해 포함됩니다.  따라서 이러한 신호를 `signal` 를 사용하여 신호 처리기를 설정할 수 있고 를 명시적으로 [발생](../../c-runtime-library/reference/raise.md)을 호출하여 이러한 신호를 생성할 수 있습니다.  
  
 신호 설정은 `_exec` 또는 `_spawn` 함수를 호출하여 생성된 프로세스에서 유지되지 않습니다.  신호 설정은 새 프로세스에서 기본 값으로 다시 설정됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`signal`|\<signal.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `signal` 를 사용하여 몇 가지 사용자 지정 동작을 `SIGABRT` 신호에 추가 하는 방법을 보여줍니다.  중단 동작에 대한 자세한 내용은 [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md)을 참조하십시오.  
  
```cpp  
// crt_signal.c  
// compile with: /EHsc /W4  
// Use signal to attach a signal handler to the abort routine  
#include <stdlib.h>  
#include <signal.h>  
#include <tchar.h>  
  
void SignalHandler(int signal)  
{  
    if (signal == SIGABRT) {  
        // abort signal handler code  
    } else {  
        // ...  
    }  
}  
  
int main()  
{  
    typedef void (*SignalHandlerPointer)(int);  
  
    SignalHandlerPointer previousHandler;  
    previousHandler = signal(SIGABRT, SignalHandler);  
  
    abort();  
}  
  
```  
  
  **다음과 같은 메시지가 표시되었습니다. "이 응용 프로그램에서 비정상적인 종료를 런타임에 요청했습니다."**  
**자세한 내용은 해당 응용 프로그램의 지원 팀에 문의하십시오.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_fpreset](../../c-runtime-library/reference/fpreset.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)