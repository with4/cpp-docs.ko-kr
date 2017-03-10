---
title: "프로세스 및 환경 제어 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d5198dcef7d24d2755c21b90802b19e809c5b8da
ms.lasthandoff: 02/24/2017

---
# <a name="process-and-environment-control"></a>프로세스 및 환경 제어
프로세스 제어 루틴을 사용하여 프로그램 내에서 프로세스를 시작, 중지 및 관리합니다. 환경 제어 루틴을 사용하여 운영 체제 환경에 대한 정보를 가져오고 변경합니다.  
  
### <a name="process-and-environment-control-functions"></a>프로세스 및 환경 제어 함수  
  
|루틴|기능|.NET Framework의 해당 값|  
|-------------|---------|-------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|버퍼를 플러시하거나 `atexit` 및`_onexit`에 의해 등록된 함수를 호출하지 않고 프로세스를 중단합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|논리 오류를 테스트합니다.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로|`assert`와 유사하지만 런타임 라이브러리의 디버그 버전에서만 사용할 수 있습니다.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|프로그램 종료 시 실행 루틴을 예약합니다.|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Windows 운영 체제 프로세스에서 새 스레드를 만듭니다.|[System::Threading::Thread::Start](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|`exit` 종료 프로시저(예: 버퍼 플러시)를 수행한 후 프로세스를 종료하지 않고 호출 프로그램으로 제어권을 반환합니다.|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|`_exit` 종료 프로시저를 수행한 후 프로세스를 종료하지 않고 호출 프로그램으로 제어권을 반환합니다.|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_cwait](../c-runtime-library/reference/cwait.md)|다른 프로세스가 종료될 때까지 기다립니다.|[System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Windows 운영 체제 스레드를 종료합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|인수 목록을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|인수 목록 및 지정된 환경을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|`PATH` 변수 및 인수 목록을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|`PATH` 변수, 지정된 환경 및 인수 목록을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|인수 배열을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|인수 배열 및 지정된 환경을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|`PATH` 변수 및 인수 배열을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|`PATH` 변수, 지정된 환경 및 인수 배열을 사용하여 새 프로세스를 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` 및 `_onexit`에 의해 등록된 함수를 호출하고, 모든 버퍼를 플러시하고, 열려 있는 모든 파일을 닫고, 프로세스를 종료합니다.|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` 또는 `_onexit`를 호출하지 않고 버퍼도 플러시하지 않고 프로세스를 즉시 종료합니다.|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|환경 변수 값을 가져옵니다.|[System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[_getpid](../c-runtime-library/reference/getpid.md)|프로세스 ID 번호를 가져옵니다.|[System::Diagnostics::Process::Id](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|저장된 스택 환경을 복원하고 비로컬 `goto`를 실행하는 데 사용합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|프로그램 종료 시 실행 루틴을 예약합니다. Microsoft C/C++ 버전 7.0 및 이전 버전과의 호환성을 위해 사용합니다.|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_pclose](../c-runtime-library/reference/pclose.md)|새 명령 프로세서가 실행될 때까지 기다렸다가 연결된 파이프에서 스트림을 닫습니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|오류 메시지를 출력합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_pipe](../c-runtime-library/reference/pipe.md)|읽기 및 쓰기용 파이프를 만듭니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|파이프를 만들고 명령을 실행합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|환경 변수의 값을 추가하거나 변경합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[raise](../c-runtime-library/reference/raise.md)|호출 프로세스로 신호를 보냅니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|스택 환경을 저장하고 비로컬 `goto`를 실행하는 데 사용합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[signal](../c-runtime-library/reference/signal.md)|인터럽트 신호를 처리합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|새 프로세스를 만들고 지정된 인수 목록을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|새 프로세스를 만들고 지정된 인수 목록 및 환경을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|새 프로세스를 만들고 `PATH` 변수 및 지정된 인수 목록을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|새 프로세스를 만들고 `PATH` 변수, 지정된 환경 및 인수 목록을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|새 프로세스를 만들고 지정된 인수 배열을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|새 프로세스를 만들고 지정된 환경 및 인수 배열을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|새 프로세스를 만들고 `PATH` 변수 및 지정된 인수 배열을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|새 프로세스를 만들고 `PATH` 변수, 지정된 환경 및 인수 배열을 사용하여 실행합니다.|[System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|운영 체제 명령을 실행합니다.|[System::Diagnostics::ProcessStartInfo 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Windows 운영 체제에서 생성된 프로세스는 생성하는 프로세스와 동급입니다. 모든 프로세스에서 `_cwait`를 사용하여 프로세스 ID가 알려진 다른 프로세스를 대기할 수 있습니다.  
  
 `_exec` 및 `_spawn` 패밀리 간의 차이는 `_spawn` 함수가 새 프로세스에서 호출 프로세스로 제어권을 반환할 수 있다는 것입니다. `_spawn` 함수에서 호출 프로세스 및 새 프로세스는 `_P_OVERLAY`가 지정되지 않는 한, 둘 다 메모리에 위치합니다. `_exec` 함수에서 새 프로세스는 호출하는 프로세스를 오버레이하므로 새 프로세스의 실행을 시작하려는 시도 중에 오류가 발생하지 않는 한, 제어권이 호출하는 프로세스로 반환될 수 없습니다.  
  
 `_exec` 제품군의 함수와 `_spawn` 제품군의 함수 간 차이는 다음 표에 나온 것처럼 새 프로세스로 실행될 파일을 찾는 방법, 인수가 새 프로세스로 전달되는 방식 및 환경을 설정하는 방법과 관련이 있습니다. 인수 개수가 일정하거나 컴파일 타임에 알려질 경우 인수 목록을 전달하는 함수를 사용합니다. 인수 개수가 런타임에 결정될 경우에는 인수를 포함하는 배열에 대한 포인터를 전달하는 함수를 사용합니다. 다음 표의 정보는 `_spawn` 및 `_exec` 함수의 와이드 문자 방식에도 적용됩니다.  
  
### <a name="spawn-and-exec-function-families"></a>_spawn 및 _exec 함수 패밀리  
  
|함수|PATH 변수를 사용하여 파일 찾기|인수 전달 규칙|환경 설정|  
|---------------|--------------------------------------|----------------------------------|--------------------------|  
|`_execl, _spawnl`|아니요|목록|호출하는 프로세스에서 상속됨|  
|`_execle, _spawnle`|아니요|목록|마지막 인수로 전달되는 새 프로세스의 환경 테이블에 대한 포인터|  
|`_execlp, _spawnlp`|예|목록|호출하는 프로세스에서 상속됨|  
|`_execlpe, _spawnlpe`|예|목록|마지막 인수로 전달되는 새 프로세스의 환경 테이블에 대한 포인터|  
|`_execv, _spawnv`|아니요|배열|호출하는 프로세스에서 상속됨|  
|`_execve, _spawnve`|아니요|배열|마지막 인수로 전달되는 새 프로세스의 환경 테이블에 대한 포인터|  
|`_execvp, _spawnvp`|예|배열|호출하는 프로세스에서 상속됨|  
|`_execvpe, _spawnvpe`|예|배열|마지막 인수로 전달되는 새 프로세스의 환경 테이블에 대한 포인터|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
