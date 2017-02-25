---
title: "프로세스 및 환경 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "환경 제어 루틴"
  - "부모 프로세스"
  - "프로세스 제어 루틴"
  - "프로세스, 관리 작업"
  - "프로세스, 시작"
  - "프로세스, 중지"
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 프로세스 및 환경 제어
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로세스 제어 루틴을 사용하여 시작, 중지 그리고 프로그램 내의 프로세스를 관리하십시오.  환경 제어 루틴을 이용하여 운영체제 환경의 정보를 얻고 변경하십시오.  
  
### 프로세스 및 환경 제어 기능  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[abort](../c-runtime-library/reference/abort.md)|버퍼를 플러시하거나 `atexit` 및 `_onexit`에 의해 등록된 함수를 호출하지 말고 프로세스를 중단합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|논리 오류를 테스트합니다.|[\<caps:sentence id\="tgt14" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug:: 어설션\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERT, \_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로|`assert`와 유사하지만, 런타임 라이브러리의 디버그 버전에서만 사용할 수 있습니다.|[\<caps:sentence id\="tgt17" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug:: 어설션\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|프로그램 종료 시 실행할 루틴을 예약합니다.|[\<caps:sentence id\="tgt20" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Windows 운영 체제 프로세스에서 새 스레드를 생성합니다.|[\<caps:sentence id\="tgt23" sentenceid\="221e38ecc6535bce91af4e1a19f464d1" class\="tgtSentence"\>System::Threading::Thread::Start\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[\_cexit](../c-runtime-library/reference/cexit-c-exit.md)|`exit` 종료 프로시저 \(예: 버퍼 플러시\) 를 실행한 뒤, 프로세스를 종료하지 않고 프로그램을 호출하기 위해 컨트롤을 반환합니다.|[\<caps:sentence id\="tgt26" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_c\_exit](../c-runtime-library/reference/cexit-c-exit.md)|`_exit` 종료 프로시저를 실행한 뒤, 프로세스를 종료하지 않고 프로그램을 호출하기 위해 컨트롤을 반환합니다.|[\<caps:sentence id\="tgt29" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_cwait](../c-runtime-library/reference/cwait.md)|다른 프로세스가 종료될 때까지 기다립니다.|[\<caps:sentence id\="tgt32" sentenceid\="d9c88c429eaacaa9f37d91d29bc6504e" class\="tgtSentence"\>System::Diagnostics::Process::WaitForExit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Windows 운영 체제 스레드를 종료합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_execl, \_wexecl](../c-runtime-library/reference/execl-wexecl.md)|인수 목록을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execle, \_wexecle](../c-runtime-library/reference/execle-wexecle.md)|인수 목록과 제공된 환경을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlp, \_wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|`PATH` 변수와 인수 목록을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlpe, \_wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|`PATH` 변수, 제공된 환경, 인수 목록을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execv, \_wexecv](../c-runtime-library/reference/execv-wexecv.md)|인수 배열을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execve, \_wexecve](../c-runtime-library/reference/execve-wexecve.md)|인수 배열과 제공된 환경을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvp, \_wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|`PATH` 변수와 인수 배열을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvpe, \_wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|`PATH` 변수, 제공된 환경, 인수 배열을 이용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` 및 `_onexit`에 의해 등록된 함수를 호출하고, 모든 버퍼를 플러시하고, 열려 있는 모든 파일을 닫고 프로세스를 종료합니다.|[\<caps:sentence id\="tgt64" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[\_exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` 또는 `_onexit` 또는 버퍼 플러시를 호출하지 않고 프로세스를 즉시 종료합니다.|[\<caps:sentence id\="tgt67" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|환경 변수의 값을 가져옵니다.|[\<caps:sentence id\="tgt70" sentenceid\="795988b9277d74ea3b722ecd42dcb29d" class\="tgtSentence"\>System.Environment::GetEnvironmentVariables\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[\_getpid](../c-runtime-library/reference/getpid.md)|프로세스 ID 번호를 가져옵니다.|[\<caps:sentence id\="tgt73" sentenceid\="745b82c461dc74b15540e9622f7cd7bd" class\="tgtSentence"\>System::Diagnostics::Process::Id\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|저장된 스택 환경을 복원하여, 로컬이 아닌 `goto`를 실행하는 데 사용합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|프로그램 종료 시 실행할 루틴을 예약합니다; Microsoft C\/C\+\+ 7.0 및 이전 버전 호환을 위해 사용합니다.|[\<caps:sentence id\="tgt81" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_pclose](../c-runtime-library/reference/pclose.md)|새 명령 프로세서를 기다렸다가 연결 파이프의 스트림을 닫습니다|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[perror, \_wperror](../c-runtime-library/reference/perror-wperror.md)|오류 메시지를 출력합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_pipe](../c-runtime-library/reference/pipe.md)|읽기 및 쓰기에 대한 파이프를 만듭니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)|파이프를 생성하고 명령을 실행합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md), [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|환경 변수의 값을 추가하거나 변경합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[raise](../c-runtime-library/reference/raise.md)|호출 프로세스에 신호를 보냅니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|스택 환경을 저장합니다; 로컬이 아닌 `goto`를 실행하기 위해 사용합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[신호](../c-runtime-library/reference/signal.md)|인터럽트 신호를 처리합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_spawnl, \_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|지정된 인수 목록을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|지정된 인수 목록 및 환경을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|`PATH` 변수 및 지정된 인수 목록을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlpe, \_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|`PATH` 변수, 지정된 환경 및 인수 목록을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|지정된 인수 배열을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|지정된 환경 및 인수 배열을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|`PATH` 변수 및 지정된 인수 배열을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvpe, \_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|`PATH` 변수, 지정된 환경 및 인수 배열을 사용하여 새 프로세스를 생성하고 실행합니다.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)|운영 체제 명령을 실행합니다.|[System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Windows 운영 체제에서, 스폰된 프로세스는 스포닝 프로세스와 같습니다.  모든 프로세스는 프로세스 ID가 알려진 다른 프로세스를 기다리기 위해 `_cwait`를 사용할 수 있습니다.  
  
 `_exec`과 `_spawn` 사이의 차이점은, `_spawn` 함수는 새 프로세스로부터 호출 프로세스에게 컨트롤을 반환할 수 있다는 것입니다.  `_spawn` 함수에서는, `_P_OVERLAY`가 지정되지 않은 경우 호출 프로세스와 새 프로세스가 모두 메모리 안에 있습니다.  `_exec` 함수에서는, 새 프로세스는 호출 프로세스를 덮어쓰기 때문에 새 프로세스의 실행을 시작하려는 시도에서 오류가 발생하지 않는 한 컨트롤은 호출 프로세스에 반환될 수 없습니다.  
  
 `_exec` 함수군 내 함수들 사이의 차이점은 `_spawn` 함수군 내의 함수와 마찬가지로, 다음 표와 같이 새 프로세스로 실행될 파일을 위치시키는 메서드, 새 프로세스로 전달되는 인수의 양식 및 환경을 설정하는 메서드에 관련됩니다.  인수의 수가 상수이거나 컴파일 시 알려진 경우 인수 목록을 전달하는 함수를 사용합니다.  인수의 수가 실행 시간에 결정되는 경우 인수를 포함한 배열을 가리키는 포인터를 전달하는 함수를 사용합니다.  다음 표의 정보는 `_spawn` 및 `_exec` 함수의 와이드 문자 대응에도 적용됩니다.  
  
### \_exec 및 \_spawn 함수군  
  
|함수|PATH 변수를 사용하여 파일의 위치를 지정합니다.|인수 전달 규칙|환경 설정|  
|--------|----------------------------------|--------------|-----------|  
|`_execl, _spawnl`|아니요|List|호출 프로세스에서 상속합니다.|  
|`_execle, _spawnle`|아니요|List|마지막 인수로 전달된 환경 표를 가리키는 포인터입니다.|  
|`_execlp, _spawnlp`|예|List|호출 프로세스에서 상속합니다.|  
|`_execlpe, _spawnlpe`|예|List|마지막 인수로 전달된 환경 표를 가리키는 포인터입니다.|  
|`_execv, _spawnv`|아니요|배열|호출 프로세스에서 상속합니다.|  
|`_execve, _spawnve`|아니요|배열|마지막 인수로 전달된 환경 표를 가리키는 포인터입니다.|  
|`_execvp, _spawnvp`|예|배열|호출 프로세스에서 상속합니다.|  
|`_execvpe, _spawnvpe`|예|배열|마지막 인수로 전달된 환경 표를 가리키는 포인터입니다.|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)