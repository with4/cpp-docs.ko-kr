---
title: "연습: COM 사용 응용 프로그램에서 동시성 런타임을 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 676601259e7f1a682a57430198d24bdbc744a360
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>연습: COM 사용 응용 프로그램에서 동시성 런타임 사용
이 문서에는 구성 요소 개체 모델 (COM)를 사용 하 여 응용 프로그램에서 동시성 런타임을 사용 하는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 시작 하기 전에 다음 문서를 읽어 보십시오.  
  
- [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
- [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)  
  
- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
- [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 COM에 대 한 자세한 내용은 참조 [구성 요소 개체 모델 (COM)](http://msdn.microsoft.com/library/windows/desktop/ms680573)합니다.  
  
## <a name="managing-the-lifetime-of-the-com-library"></a>COM 라이브러리의 수명 관리  
 Com 동시성 런타임과 함께 사용 하 여 다른 동시성 메커니즘으로 동일한 원칙 뒤 아니지만 다음 지침 효과적으로 이러한 라이브러리를 함께 사용 하 여 할 수 있습니다.  
  
-   스레드에서 호출 해야 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) COM 라이브러리를 사용 하기 전에.  
  
-   스레드를 호출할 수 `CoInitializeEx` 여러 번으로 모든 호출에 대 한 동일한 인수를 제공 합니다.  
  
-   각 호출에 대 한 `CoInitializeEx`, 스레드에서 호출 또한 해야 [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715)합니다. 즉,에 대 한 호출이 `CoInitializeEx` 및 `CoUninitialize` 균형을 맞춰야 합니다.  
  
-   으로 전환 하려면 하나의 스레드 아파트에서 다른 스레드 완전히 비워야 COM 라이브러리를 호출 하기 전에 `CoInitializeEx` 새 스레딩 사양입니다.  
  
 다른 COM 원칙이 COM 동시성 런타임과 함께 사용 하는 경우에 적용 됩니다. 예를 들어 응용 프로그램을 단일 스레드 아파트 (STA)에서 개체를 만들고 다른 아파트에 해당 개체를 마샬링하는 들어오는 메시지를 처리 하는 메시지 루프도 제공 해야 합니다. 또한 개체 간의 아파트 마샬링 성능을 저하 시킬 수 기억 합니다.  
  
### <a name="using-com-with-the-parallel-patterns-library"></a>COM을 사용 하 여 병렬 패턴 라이브러리  
 COM 구성 요소에 라이브러리 PPL (병렬 패턴), 예를 들어 작업 그룹 또는 병렬 알고리즘을 사용 하는 경우 호출 `CoInitializeEx` 각 작업 또는 반복 및 호출 하는 동안 COM 라이브러리를 사용 하기 전에 `CoUninitialize` 각 작업이 나 반복 완료 되기 전에 . 와 COM 라이브러리의 수명을 관리 하는 방법을 보여 주는 다음 예제는 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체입니다.  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 작업 또는 병렬 알고리즘 취소 될 때 또는 작업 본문에서 예외가 throw 할 때 COM 라이브러리 올바로 해제 되어 있는지 확인 해야 합니다. 호출 하는 작업을 보장 하려면 `CoUninitialize` 사용 하 여 종료 되기 전에 `try-finally` 블록 또는 *Resource Acquisition Is Initialization* (RAII) 패턴. 다음 예제에서는 `try-finally` 블록에서 예외가 throw 되 면 작업이 완료 되거나 취소 될 때 또는 COM 라이브러리를 해제 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 다음 예제에서는 RAII 패턴을 사용 하 여 정의 하는 `CCoInitializer` 지정 된 범위에서 COM 라이브러리의 수명을 관리 하는 클래스입니다.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 사용할 수는 `CCoInitializer` 클래스를 다음과 같이 작업 종료 시 COM 라이브러리를 자동으로 해제 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 동시성 런타임에서 취소에 대 한 자세한 내용은 참조 [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.  
  
### <a name="using-com-with-asynchronous-agents"></a>COM을 사용 하 여 비동기 에이전트  

 COM을 사용 하 여 비동기 에이전트와 함께 호출 `CoInitializeEx` 에서 COM 라이브러리를 사용 하기 전에 [concurrency::agent::run](reference/agent-class.md#run) 에이전트에 대 한 메서드. 그런 다음 호출 `CoUninitialize` 하기 전에 `run` 메서드 반환 합니다. COM 관리 루틴을 생성자 또는 소멸자의 에이전트를 사용 하지 않으며 재정의 하지 않는 [concurrency::agent::start](reference/agent-class.md#start) 또는 [concurrency:: agent:: 수행](reference/agent-class.md#done) 메서드 이러한 메서드는 때문에 보다 다른 스레드에서 호출는 `run` 메서드.  

  
 다음 예제에서는 명명 된 기본 에이전트 클래스를 `CCoAgent`에서 COM 라이브러리를 관리 하는 `run` 메서드.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 전체 예제는이 연습의 뒷부분에서 제공 됩니다.  
  
### <a name="using-com-with-lightweight-tasks"></a>COM을 사용 하 여 간단한 작업 사용  
 문서 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md) 동시성 런타임의 간단한 작업의 역할에 설명 합니다. 에 전달 하는 스레드 루틴와 마찬가지로 COM 간단한 작업으로 사용할 수 있습니다는 `CreateThread` Windows API에는 함수입니다. 다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## <a name="an-example-of-a-com-enabled-application"></a>COM 사용 응용 프로그램의 예  
 이 섹션에서는 전체 COM 사용 응용 프로그램을 사용 하는 `IScriptControl` n을 계산 하는 스크립트를 실행 하는 인터페이스<sup>번째</sup> 피보나치 수입니다. 이 예에서는 주 스레드의 스크립트를 먼저 호출 하 고 동시에 스크립트를 호출 하 PPL 및 에이전트를 사용 합니다.  
  
 다음과 같은 도우미 함수가 있다고 합시다 `RunScriptProcedure`의 프로시저를 호출 하는 `IScriptControl` 개체입니다.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 `wmain` 함수를 만듭니다는 `IScriptControl` 개체를 n를 계산 하는 스크립트 코드를 추가,<sup>번째</sup> 피보나치 수 차례로 호출은 `RunScriptProcedure` 함수 해당 스크립트를 실행 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### <a name="calling-the-script-from-the-ppl"></a>PPL에서 스크립트 호출  

 다음 함수를 `ParallelFibonacci`를 사용 하 여는 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 병렬로 스크립트를 호출 하는 알고리즘입니다. 이 함수는 사용 된 `CCoInitializer` 작업의 모든 반복 하는 동안 COM 라이브러리의 수명을 관리 하는 클래스입니다.  

  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 사용 하는 `ParallelFibonacci` 예제로 함수를 추가 하기 전에 다음 코드는 `wmain` 함수에서 반환 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### <a name="calling-the-script-from-an-agent"></a>에이전트에서 스크립트 호출  
 다음 예제와 `FibonacciScriptAgent` n을 계산 하는 스크립트 프로시저를 호출 하는 클래스<sup>번째</sup> 피보나치 수 있습니다. `FibonacciScriptAgent` 클래스 메시지 수신, 주 프로그램을 전달 하는 입력 스크립트 함수에 값을 사용 합니다. `run` 메서드는 작업 전반에 걸쳐 COM 라이브러리의 수명을 관리 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 다음 함수를 `AgentFibonacci`, 여러 개 만들어 `FibonacciScriptAgent` 개체 및 메시지 전달 여러 보낼 입력 값을 해당 개체를 사용 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 사용 하는 `AgentFibonacci` 예제로 함수를 추가 하기 전에 다음 코드는 `wmain` 함수에서 반환 합니다.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### <a name="the-complete-example"></a>전체 예제  
 다음 코드에서는 병렬 알고리즘 및 비동기 에이전트를 사용 하 여 피보나치 수를 계산 하는 스크립트 프로시저를 호출 하는 전체 예제를 보여 줍니다.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 이 예제에서는 다음 샘플 출력을 생성합니다.  
  
```Output  
Main Thread:  
fib(15) = 610  
 
Parallel Fibonacci:  
fib(15) = 610  
fib(10) = 55  
fib(16) = 987  
fib(18) = 2584  
fib(11) = 89  
fib(17) = 1597  
fib(19) = 4181  
fib(12) = 144  
fib(13) = 233  
fib(14) = 377  
 
Agent Fibonacci:  
fib(30) = 832040  
fib(22) = 17711  
fib(10) = 55  
fib(12) = 144  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `parallel-scripts.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 병렬 scripts.cpp /link ole32.lib**  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [PPL에서의 취소](cancellation-in-the-ppl.md)   
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)

