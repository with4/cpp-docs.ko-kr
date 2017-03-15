---
title: "동시성 런타임에서 예외 처리 | Microsoft Docs"
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
  - "간단한 작업, 예외 처리[동시성 런타임]"
  - "예외 처리[동시성 런타임]"
  - "구조적 작업 그룹, 예외 처리[동시성 런타임]"
  - "에이전트, 예외 처리[동시성 런타임]"
  - "작업 그룹, 예외 처리[동시성 런타임]"
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# 동시성 런타임에서 예외 처리
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임에서는 C\+\+ 예외 처리를 사용하여 다양한 유형의 오류를 이해합니다.  이러한 오류에는 잘못된 런타임 사용, 리소스 획득 실패와 같은 런타임 오류, 작업과 작업 그룹에 제공하는 작업 함수에서 발생하는 오류 등이 있습니다.  작업과 작업 그룹에서 예외를 throw하면 런타임에서는 해당 예외를 저장하고, 작업 또는 작업 그룹이 끝날 때까지 기다리는 컨텍스트로 예외를 마샬링합니다.  간단한 작업 및 에이전트와 같은 구성 요소의 경우 런타임에서는 예외를 자동으로 관리하지 않습니다.  이러한 경우에는 사용자 고유의 예외 처리 메커니즘을 구현해야 합니다.  이 항목에서는 작업, 작업 그룹 간단한 작업 및 비동기 에이전트에서 throw하는 예외를 런타임에서 처리하는 방법과 응용 프로그램에서 예외에 응답하는 방법을 설명합니다.  
  
## 주요 사항  
  
-   작업과 작업 그룹에서 예외를 throw하면 런타임에서는 해당 예외를 저장하고, 작업 또는 작업 그룹이 끝날 때까지 기다리는 컨텍스트로 예외를 마샬링합니다.  
  
-   가능 하면  `try` \/ `catch` 블록과 [concurrency::task::get](../Topic/task::get%20Method.md) 및  [concurrency::task::wait](../Topic/task::wait%20Method.md) 을 호출하여 복구할 수 있는 오류를 처리합니다.  작업에서 예외를 throw 한 작업의 연속 또는 기본 응용 프로그램 중 하나에서 예외가 잡히지 않아 런타임 응용 프로그램을 종료 합니다.  
  
-   작업 기반의 계속이 항상 실행됩니다. 선행 작업이 성공적으로 완료된지 여부와 관계없이 예외를 throw하거나 취소됩니다.  선행 작업이 발생하거나 취소하면 값에 따라 연속 실행되지 않습니다.  
  
-   작업 기반 연속 항상 실행되기 때문에, 연속 체인의 끝에 작업 기반 지속을 추가할지 여부를 고려합니다.  코드에서 모든 예외를 보장하는 데 도움이 됩니다.  
  
-   [concurrency::task::get](../Topic/task::get%20Method.md) 를 호출할 때 런타임에서  [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md)를  throw하고 해당작업이 취소됩니다.  
  
-   런타임에서 간단한 작업 및 에이전트에 대한 예외를 관리를 하지 않습니다.  
  
##  <a name="top"></a> 이 문서에서 다루는 내용  
  
-   [작업 및 연속 작업](#tasks)  
  
-   [작업 그룹 및 병렬 알고리즘](#task_groups)  
  
-   [런타임에서 Throw되는 예외](#runtime)  
  
-   [여러 예외](#multiple)  
  
-   [취소](#cancellation)  
  
-   [간단한 작업](#lwts)  
  
-   [비동기 에이전트](#agents)  
  
##  <a name="tasks"></a> 작업 및 연속 작업  
 이 단원에서는 런타임이 [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) 개체에 의해 throw 되는 예외를 처리하는 방법을 설명합니다.  자동화 개체 모델과 작업에 대한 자세한 내용은 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)를 참조하십시오.  
  
 `task` 개체에 전달하는 작업 함수의 본문에서 예외를 throw하는 경우 런타임에서는 해당 예외를 저장하고, [concurrency::task::get](../Topic/task::get%20Method.md) 또는 [concurrency::task::wait](../Topic/task::wait%20Method.md)를 호출하는 컨텍스트로 예외를 마샬링합니다.  문서 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)는 값 기반 연속성을 제외한 값 기반을 설명합니다. 그러나 요약하기 위해 값 기반 연속성이  `T` 형식의 매개변수를 사용하고, 작업 기반 연속성은  `task<T>`  형식의 매개 변수를 사용합니다.  작업 기반의 연속은 선행 작업에서 발생하는 모든 예외를 처리 할 수 있습니다.  다음 예제는 이 동작을 보여 줍니다.  
  
 [!code-cpp[concrt-eh-task#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_1.cpp)]  
  
 작업 기반의 연속은 선행 작업에서 발생하는 모든 예외를 처리 할 수 있습니다.  작업 기반의 계속이 항상 실행됩니다. 작업이 성공적으로 완료된지 여부와 관계없이 예외를 throw하거나 취소됩니다.  작업에서 예외를 throw 하는 경우 작업 기반 연속 실행 되도록 예약됩니다.  다음 예제에서는 항상 throw 하는 작업을 보여줍니다.  작업은 두 개의 연속을 갖습니다; 값 기반과 작업 기반.  작업 기반 예외는 항상 실행되고 따라서 선행 작업에서 throw 되는 예외를 catch 할 수 있습니다.  예가 모든 연속이 마무리되는 것을 기다릴 때, 예외는 작업 예외가  `task::get`  또는  `task::wait` 가 호출될 때 항상 처리되기 때문에 다시 throw됩니다.  
  
 [!code-cpp[concrt-eh-continuations#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_2.cpp)]  
  
 연속 작업을 사용하여 처리할 수 있는 예외를 catch 하는 것이 좋습니다.  작업 기반 연속 항상 실행되기 때문에, 연속 체인의 끝에 작업 기반 지속을 추가할지 여부를 고려합니다.  코드에서 모든 예외를 보장하는 데 도움이 됩니다.  다음 예제에서는 기본 값에 따른 연속 체인을 보여줍니다.  체인의 세 번째 작업이 발생, 따라서 그 뒤에 이어지는 값 기반의 연속이 실행되지 않습니다.  그러나 마지막 연속 작업 기반이며 따라서 항상 실행합니다.  마지막이 연속 세 번째 작업에서 throw 되는 예외를 처리합니다.  
  
 가장 구체적인 예외를 catch 하는 것이 좋습니다.  특정 예외를 catch 하지 않은 경우 이 마지막 작업 연속을 생략할 수 있습니다.  예외가 처리 되지 않은 상태로 유지되고 응용 프로그램을 종료할 수 있습니다.  
  
 [!code-cpp[concrt-eh-task-chain#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_3.cpp)]  
  
> [!TIP]
>  [concurrency::task\_completion\_event::set\_exception](../../parallel/concrt/reference/task-completion-event-class.md)메소드를 사용하여  작업 완료 이벤트와 예외를 연결할 수 있습니다.  문서 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)는 [concurrency::task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md)클래스를 보다 더 자세히 설명합니다.  
  
 [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md)는   `task` 에 관련 된 중요한 런타임 예외 형식입니다.  런타임은  `task::get` 을 호출할 때  `task_canceled` 을 처리하고 해당 작업이 취소됩니다. \(반대로  `task::wait` 는  [task\_status::canceled](../Topic/task_group_status%20Enumeration.md)을 반환하고 throw 하지 않습니다.\) 당신은 `task::get`를 호출 할 때 작업 기반 연속의 예외를 catch하고 처리할 수 있습니다.  작업 취소에 대한 자세한 내용은 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)를 참조하십시오.  
  
> [!CAUTION]
>  코드에서  `task_canceled` 를 절대 처리하지 않습니다.  대신 [concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md)을 호출합니다.  
  
 작업에서 예외를 throw 한 작업의 연속 또는 기본 응용 프로그램 중 하나에서 예외가 잡히지 않아 런타임 응용 프로그램을 종료 합니다.  응용 프로그램이 충돌 하는 경우 Visual Studio c \+ \+ 예외가 throw 될 때 중단 되도록 구성할 수 있습니다.  처리 되지 않은 예외의 위치를 진단 한 후 작업 기반 연속 처리에 사용합니다.  
  
 이 문서에서 [런타임에서 Throw 예외](#runtime) 섹션은 자세히 런타임 예외를 사용하여 작업하는 방법에 설명합니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="task_groups"></a> 작업 그룹 및 병렬 알고리즘  
 이 단원에서는 작업 그룹에서 throw된 예외를 런타임에서 처리하는 방법에 대해 설명합니다.  또한 이 단원은 [concurrency::Concurrency::parallel\_for](../Topic/parallel_for%20Function.md)와 같이 작업 그룹을 기반으로 하는 병렬 알고리즘에도 적용됩니다.  
  
> [!CAUTION]
>  예외가 종속 작업에 미치는 효과를 이해해야 합니다.  작업 또는 병렬 알고리즘과 예외 처리를 사용하는 방법에 대한 권장 사례에 대하여, 병렬 패턴 라이브러리 항목의 모범 사례 섹션의 [취소 및 예외 처리가 개체 소멸에 미치는 영향 이해](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) 섹션을 확인하십시오.  
  
 작업 그룹에 대한 자세한 내용은 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)를 참조하십시오.  병렬 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
 [concurrency::Concurrency::task\_group](../Topic/task_group%20Class.md) 또는 [concurrency::Concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체에 전달하는 작업 함수의 본문에서 예외를 throw하면 런타임에서는 해당 예외를 저장하고, [concurrency::Concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::Concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::Concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) 또는 [concurrency::Concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)를 호출하는 컨텍스트로 예외를 마샬링합니다.  또한 런타임에서는 자식 작업 그룹의 작업을 포함하여 작업 그룹에 있는 모든 활성 작업을 중지하고 아직 시작되지 않은 작업을 취소합니다.  
  
 다음 예제에서는 예외를 throw하는 작업 함수의 기본 구조를 보여 줍니다.  이 예제에서는 `task_group` 개체를 사용하여 두 `point` 개체의 값을 병렬로 출력합니다.  `print_point` 작업 함수는 `point` 개체의 값을 콘솔에 출력합니다.  입력 값이 `NULL`인 경우 작업 함수에서 예외가 throw됩니다.  런타임에서는 이 예외를 저장하고 `task_group::wait`를 호출하는 컨텍스트로 마샬링합니다.  
  
 [!code-cpp[concrt-eh-task-group#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_4.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **X \= 15, Y \= 30**  
**예외 발생: 포인터가 NULL입니다.** 작업 그룹에서 예외 처리를 사용하는 전체 예제를 보려면 [방법: 예외 처리를 사용하여 병렬 루프 중단](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)을 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="runtime"></a> 런타임에서 Throw되는 예외  
 호출 하는 런타임 예외가 발생할 수 있습니다.  [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) 및  [concurrency::operation\_timed\_out](../../parallel/concrt/reference/operation-timed-out-class.md)을 제외하고 대부분의 예외 형식은 프로그래밍 오류를 나타냅니다.  일반적으로 이러한 오류는 복구할 수 없으므로 응용 프로그램 코드에 의해 처리되거나 catch되지 않아야 합니다.  프로그래밍 오류를 진단해야 하는 경우에만 응용 프로그램 코드에서 복구할 수 없는 오류를 처리하거나 catch하는 것이 좋습니다.  그러나 런타임에 정의되어 있는 예외 형식을 이해하면 프로그래밍 오류를 진단하는 데 도움이 될 수 있습니다.  
  
 런타임에서 throw되는 예외에 대한 예외 처리 메커니즘은 작업 함수에서 throw되는 예외의 경우와 같습니다.  예를 들어 [concurrency::receive](../Topic/receive%20Function.md) 함수는 지정된 기간 내에 메시지를 받지 못하면 `operation_timed_out`을 throw합니다.  작업 그룹에 전달하는 작업 함수에서 `receive`가 예외를 throw하는 경우 런타임에서는 해당 예외를 저장하고 `task_group::wait`, `structured_task_group::wait`, `task_group::run_and_wait` 또는 `structured_task_group::run_and_wait`를 호출하는 컨텍스트로 마샬링합니다.  
  
 다음 예제에서는 [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘을 사용하여 두 작업을 병렬로 실행합니다.  첫 번째 작업에서는 5초 동안 기다린 후 메시지 버퍼에 메시지를 보냅니다.  두 번째 작업에서는 `receive` 함수를 사용하여 첫 번째 작업의 메시지 버퍼에서 메시지를 받을 때까지 3초 동안 기다립니다.  `receive` 함수는 지정된 기간 내에 메시지를 받지 못하면 `operation_timed_out`을 throw합니다.  
  
 [!code-cpp[concrt-eh-time-out#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_5.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **작업 시간이 초과된 경우** 응용 프로그램이 비정상적으로 종료되지 않도록 하려면 코드에서 런타임을 호출할 때 예외를 처리해야 합니다.  또한 타사 라이브러리와 같이 동시성 런타임을 사용하는 외부 코드를 호출할 때도 예외를 처리하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="multiple"></a> 여러 예외  
 작업 또는 병렬 알고리즘이 여러 예외를 받으면 런타임에서는 이러한 예외 중 하나만 호출 컨텍스트로 마샬링합니다.  런타임에서는 어떤 예외를 마샬링하는지에 대해 보증하지 않습니다.  
  
 다음 예제에서는 `parallel_for` 알고리즘을 사용하여 숫자를 콘솔에 출력합니다.  여기에서는 입력 값이 일부 최소값보다 작거나 최대값보다 크면 예외가 throw됩니다.  이 예제에서는 여러 작업 함수에서 예외를 throw할 수 있습니다.  
  
 [!code-cpp[concrt-eh-multiple#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_6.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **8**  
**2**  
**9**  
**3**  
**10**  
**4**  
**5**  
**6**  
**7**  
**예외 발견:\-5: 값이 최소값 보다 작습니다.** \[[맨 위](#top)\]  
  
##  <a name="cancellation"></a> 취소  
 모든 예외가 오류를 나타내는 것은 아닙니다.  예를 들어 검색 알고리즘은 예외 처리를 사용하여 결과를 발견하면 관련 작업을 중지할 수 있습니다.  코드에서 취소 메커니즘을 사용하는 방법에 대한 자세한 내용은 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="lwts"></a> 간단한 작업  
 간단한 작업은 [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) 개체에서 직접 예약하는 작업입니다.  간단한 작업은 일반적인 작업보다 오버헤드가 적습니다.  그러나 런타임에서는 간단한 작업에서 throw되는 예외를 catch하지 않습니다.  대신 처리되지 않은 예외 처리기에 의해 예외가 catch되어 기본적으로 프로세스가 종료됩니다.  그러므로 응용 프로그램에서 적절한 오류 처리 메커니즘을 사용해야 합니다.  간단한 작업에 대한 자세한 내용은 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="agents"></a> 비동기 에이전트  
 간단한 작업과 마찬가지로 런타임에서는 비동기 에이전트에서 throw되는 예외를 관리하지 않습니다.  
  
 다음 예제에서는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)에서 파생되는 클래스에서 예외를 처리하는 한 가지 방법을 보여 줍니다.  이 예제에서는 `points_agent` 클래스를 정의합니다.  `points_agent::run` 메서드는 메시지 버퍼에서 `point` 개체를 읽고 콘솔에 출력합니다.  `run` 메서드는 `NULL` 포인터를 받으면 예외를 throw합니다.  
  
 `run` 메서드는 `try`\-`catch` 블록의 모든 작업을 포함합니다.  `catch` 블록은 예외를 메시지 버퍼에 저장합니다.  응용 프로그램에서는 에이전트가 끝난 후 이 버퍼를 읽어 해당 에이전트에서 오류가 발생했는지 여부를 검사합니다.  
  
 [!code-cpp[concrt-eh-agents#1](../../parallel/concrt/codesnippet/CPP/exception-handling-in-the-concurrency-runtime_7.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **X: 10 Y: 20**  
**X: 20 Y: 30**  
**에이전트에서 오류가 발생 했습니다: 포인트는 NULL이 아니어야 합니다.**  
**에이전트의 상태: 완료** `try`\-`catch` 블록은 `while` 루프 외부에 있으므로 에이전트는 첫 번째 오류가 발생하면 처리를 종료합니다.  `try`\-`catch` 블록이 `while` 루프 내부에 있었다면 오류가 발생한 후에도 에이전트가 계속 실행됩니다.  
  
 이 예제에서는 다른 구성 요소에서 에이전트가 실행될 때 오류가 발생하는지 모니터링할 수 있도록 메시지 버퍼에 예외를 저장합니다.  여기에서는 [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md) 개체를 사용하여 오류를 저장합니다.  에이전트가 여러 예외를 처리하는 경우 `single_assignment` 클래스는 첫 번째로 전달되는 메시지만 저장합니다.  마지막 예외만 저장하려면 [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 클래스를 사용하고,  모든 예외를 저장하려면 [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) 클래스를 사용해야 합니다.  이러한 메시지 블록에 대한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
 비동기 에이전트에 대한 자세한 내용은 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="summary"></a> 요약  
 \[[맨 위](#top)\]  
  
## 참고 항목  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)