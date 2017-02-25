---
title: "연습: COM 사용 응용 프로그램에서 동시성 런타임 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "동시성 런타임, COM과 함께 사용"
  - "COM, 동시성 런타임과 함께 사용"
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 연습: COM 사용 응용 프로그램에서 동시성 런타임 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 COM\(Component Object Model\)을 사용하는 응용 프로그램에서 동시성 런타임을 활용하는 방법을 보여 줍니다.  
  
## 사전 요구 사항  
 이 연습을 시작하기 전에 다음 문서를 읽어 보십시오.  
  
-   [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)  
  
-   [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
-   [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 COM에 대한 자세한 내용은 [COM\(Component Object Model\)](http://msdn.microsoft.com/library/windows/desktop/ms680573)을 참조하십시오.  
  
## COM 라이브러리의 수명 관리  
 동시성 런타임과 함께 COM을 사용할 경우 다른 동시성 메커니즘과 동일한 원칙을 따르게 되지만 다음 지침을 참고하면 이러한 라이브러리를 효율적으로 같이 사용하는 데 도움이 됩니다.  
  
-   스레드는 COM 라이브러리를 사용하기 전에 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)를 호출해야 합니다.  
  
-   스레드는 호출할 때마다 동일한 인수를 제공하기만 하면 `CoInitializeEx`를 여러 번 호출할 수 있습니다.  
  
-   `CoInitializeEx`를 호출할 때마다 스레드는 [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715)도 호출해야 합니다.  즉, `CoInitializeEx`와 `CoUninitialize`에 대한 호출이 균형을 이루어야 합니다.  
  
-   특정 스레드 아파트에서 다른 아파트로 전환하려면 스레드가 새 스레딩 사양에 따라 `CoInitializeEx`를 호출하기 전에 COM 라이브러리를 완전히 해제해야 합니다.  
  
 동시성 런타임과 함께 COM을 사용하는 경우 다른 COM 원칙이 적용됩니다.  예를 들어 STA\(단일 스레드 아파트\)에서 개체를 만들고 해당 개체를 다른 아파트로 마샬링하는 응용 프로그램에서는 들어오는 메시지를 처리할 메시지 루프도 제공해야 합니다.  아파트 간에 개체를 마샬링하면 성능이 저하될 수도 있습니다.  
  
### 병렬 패턴 라이브러리와 함께 COM 사용  
 PPL\(병렬 패턴 라이브러리\)의 구성 요소\(예: 작업 그룹 또는 병렬 알고리즘\)와 함께 COM을 사용하는 경우 각 작업 또는 반복 도중 COM 라이브러리를 사용하기 전에 `CoInitializeEx`를 호출하고, 각 작업 또는 반복 완료 전에 `CoUninitialize`를 호출합니다.  다음 예제에서는 [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체를 사용하여 COM 라이브러리의 수명을 관리하는 방법을 보여 줍니다.  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 작업 또는 병렬 알고리즘이 취소되거나 작업 본문에서 예외를 throw할 때 COM 라이브러리가 올바로 해제되는지 확인해야 합니다.  작업 종료 전에 작업에서 `CoUninitialize`를 호출하도록 하려면 `try-finally` 블록 또는 *RAII\(Resource Acquisition Is Initialization\)* 패턴을 사용합니다.  다음 예제에서는 작업이 완료되거나 취소되는 경우 또는 예외가 되는 경우에 COM 라이브러리를 해제하기 위해 `try-finally` 블록을 사용합니다.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 다음 예제에서는 해당 범위에서 COM 라이브러리의 수명을 관리하는 `CCoInitializer` 클래스를 정의하기 위해 RAII 패턴을 사용합니다.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 작업 종료 시 COM 라이브러리가 자동으로 해제되도록 하기 위해 다음과 같이 `CCoInitializer` 클래스를 사용할 수 있습니다.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 동시성 런타임에서의 취소에 대한 자세한 내용은 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)를 참조하십시오.  
  
### 비동기 에이전트와 함께 COM 사용  
 비동기 에이전트와 함께 COM을 사용하는 경우 에이전트의 [concurrency::agent::run](../Topic/agent::run%20Method.md) 메서드에서 COM 라이브러리를 사용하기 전에 `CoInitializeEx`를 호출합니다.  그런 다음 `run` 메서드가 반환하기 전에 `CoUninitialize`를 호출합니다.  COM 관리 루틴을 에이전트의 생성자 또는 소멸자에서 사용하지 마십시오. 또한 [concurrency::agent::start](../Topic/agent::start%20Method.md)나 [concurrency::agent::done](../Topic/agent::done%20Method.md) 메서드는 `run` 메서드가 아닌 다른 스레드에서 호출되므로 이러한 메서드를 재정의하지 마십시오.  
  
 다음 예제에서는 `CCoAgent`라는 기본 에이전트 클래스를 보여 줍니다. 이 클래스는 `run` 메서드에서 COM 라이브러리를 관리합니다.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 전체 예제는 이 연습의 뒷부분에 나와 있습니다.  
  
### 간단한 작업과 함께 COM 사용  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md) 문서에서는 동시성 런타임에서 간단한 작업이 차지하는 역할에 대해 설명합니다.  Windows API의 `CreateThread` 함수에 전달하는 스레드 루틴을 사용할 때와 같은 방법으로 COM을 간단한 작업과 함께 사용할 수 있습니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## COM 사용 응용 프로그램 예제  
 이 단원에서는 `IScriptControl` 인터페이스를 사용하여 n번째 피보나치 수를 계산하는 스크립트를 실행하는 COM 사용 응용 프로그램을 전체적으로 보여 줍니다.  이 예제는 먼저 주 스레드에서 스크립트를 호출한 다음 PPL과 에이전트를 사용하여 스크립트를 동시에 호출합니다.  
  
 `IScriptControl` 개체에 있는 프로시저를 호출하는 다음 도우미 함수 `RunScriptProcedure`를 살펴봅니다.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 `wmain` 함수는 `IScriptControl` 개체를 만들고, n번째 피보나치 수를 계산하는 스크립트 코드를 이 개체에 추가한 다음 `RunScriptProcedure` 함수를 호출하여 해당 스크립트를 실행합니다.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### PPL에서 스크립트 호출  
 다음 함수 `ParallelFibonacci`에서는 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘을 사용하여 스크립트를 병렬로 호출합니다.  이 함수는 `CCoInitializer` 클래스를 사용하여 작업이 반복될 때마다 COM 라이브러리의 수명을 관리합니다.  
  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 `ParallelFibonacci` 함수를 예제와 함께 사용하려면 `wmain` 함수 반환 이전에 다음 코드를 추가합니다.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### 에이전트에서 스크립트 호출  
 다음 예제에서는 n번째 피보나치 수를 계산하기 위해 스크립트 프로시저를 호출하는 `FibonacciScriptAgent` 클래스를 보여 줍니다.  `FibonacciScriptAgent` 클래스는 메시지 전달을 사용하여 스크립트 함수 입력 값을 주 프로그램으로부터 받습니다.  `run` 메서드는 작업 전반에 걸쳐 COM 라이브러리의 수명을 관리합니다.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 다음 함수 `AgentFibonacci`에서는 `FibonacciScriptAgent` 개체를 여러 개 만들고 메시지 전달을 사용하여 여러 입력 값을 해당 개체로 보냅니다.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 `AgentFibonacci` 함수를 예제와 함께 사용하려면 `wmain` 함수 반환 이전에 다음 코드를 추가합니다.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### 전체 예제  
 다음 코드는 병렬 알고리즘 및 비동기 에이전트를 사용하여 피보나치 수를 계산하는 스크립트 프로시저를 호출하는 예제를 전체적으로 보여 줍니다.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/CPP/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **메인 스레드:**  
**fib\(15\) \= 610**  
**병렬 피보나치 수:**  
**fib\(15\) \= 610**  
**fib\(10\) \= 55**  
**fib\(16\) \= 987**  
**fib\(18\) \= 2584**  
**fib\(11\) \= 89**  
**fib\(17\) \= 1597**  
**fib\(19\) \= 4181**  
**fib\(12\) \= 144**  
**fib\(13\) \= 233**  
**fib\(14\) \= 377**  
**피보나치 에이전트:**  
**fib\(30\) \= 832040**  
**fib\(22\) \= 17711**  
**fib\(10\) \= 55**  
**fib\(12\) \= 144**   
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `parallel-scripts.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-scripts.cpp \/link ole32.lib**  
  
## 참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)