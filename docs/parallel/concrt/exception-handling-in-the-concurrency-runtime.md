---
title: "동시성 런타임에서 예외 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- lightweight tasks, exception handling [Concurrency Runtime]
- exception handling [Concurrency Runtime]
- structured task groups, exception handling [Concurrency Runtime]
- agents, exception handling [Concurrency Runtime]
- task groups, exception handling [Concurrency Runtime]
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72cde17c0bcb6a3582305167e6358f761c16f248
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-in-the-concurrency-runtime"></a>동시성 런타임에서 예외 처리
동시성 런타임은 c + + 예외 처리를 다양 한 종류의 오류 통신에 사용 합니다. 이러한 오류는 작업 및 작업 그룹에 제공 하는 작업 함수에 런타임과 리소스를 획득 하는 오류와 같은 런타임 오류가 발생 하는 오류를 잘못 사용을 포함 합니다. 작업 또는 작업 그룹이 예외를 throw 하면 런타임에서 해당 예외를 보유 하 고 작업 또는 작업 그룹이 완료 되기를 기다리는 컨텍스트에 마샬링합니다. 예: 간단한 작업 및 에이전트 구성 요소에 대 한 런타임 예외를 관리 하지 않습니다. 이러한 경우 예외 처리 메커니즘을 직접 구현 해야 합니다. 이 항목에는 런타임에 작업, 작업 그룹, 간단한 작업, 및 비동기 에이전트에 의해 throw 되는 예외를 처리 하는 방법 및 응용 프로그램에 예외에 응답 하는 방법을 설명 합니다.  
  
## <a name="key-points"></a>주요 사항  
  
-   작업 또는 작업 그룹이 예외를 throw 하면 런타임에서 해당 예외를 보유 하 고 작업 또는 작업 그룹이 완료 되기를 기다리는 컨텍스트에 마샬링합니다.  
  
-   가능 하면 서라운드를 호출할 때마다 [concurrency::task::get](reference/task-class.md#get) 및 [concurrency::task::wait](reference/task-class.md#wait) 와 `try` / `catch` 복구할 수 있는 오류를 처리 하는 블록 보낸 사람. 런타임에서 작업 예외를 throw 한 예외는 연속 또는 기본 응용 프로그램 중 하나는 작업으로는 포착 되지 경우 응용 프로그램을 종료 합니다.  
  
-   작업 기반 연속은 항상 실행 됩니다. 선행 작업이 성공적으로 완료에 예외가 발생 했습니다 또는 취소 되었는지 여부를 중요 하지 않습니다. 값 기반 연속은 선행 작업이 throw 되거나 취소 하는 경우 실행 되지 않습니다.  
  
-   항상 작업 기반 연속에서 실행 되므로 연속 체인의 끝에 작업 기반 연속을 추가 하려면 사용할지 고려 합니다. 이 코드는 모든 예외를 준수 한다고 보장할 수 있습니다.  
  
-   런타임에서 throw [concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md) 호출 하는 경우 [concurrency::task::get](reference/task-class.md#get) 해당 작업이 취소 되 고 있습니다.  

  
-   런타임에서 간단한 작업 및 에이전트에 대 한 예외를 관리 하지 않습니다.  
  
##  <a name="top"></a>이 문서에서  
  
- [작업 및 연속 작업](#tasks)  
  
- [작업 그룹 및 병렬 알고리즘](#task_groups)  
  
- [런타임에 의해 발생 한 예외](#runtime)  
  
- [여러 예외](#multiple)  
  
- [취소](#cancellation)  
  
- [간단한 작업](#lwts)  
  
- [비동기 에이전트](#agents)  
  
##  <a name="tasks"></a>작업 및 연속 작업  
 이 섹션에서는 런타임에 의해 throw 되는 예외를 처리 하는 방법을 설명 [concurrency:: task](../../parallel/concrt/reference/task-class.md) 개체 및 작업의 연속입니다. 작업 및 연속 모델에 대 한 자세한 내용은 참조 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.  
  
 에 전달 하는 작업 함수의 본문에서 예외를 throw 하는 경우는 `task` 개체 런타임에서 해당 예외를 저장 하 고 호출 하는 컨텍스트에 마샬링합니다 [concurrency::task::get](reference/task-class.md#get) 또는 [동시성:: task:: wait](reference/task-class.md#wait)합니다. 문서 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md) 설명 값 기반 연속을 요약 하면, 하지만 값 기반 연속과 작업 기반 형식의 매개 변수 `T` 형식의 매개 변수를 사용 하는 작업 기반 연속 및 `task<T>`. throw 하는 작업에 하나 이상의 값 기반 연속을 연속 작업 실행 되도록 예약 되지 않은 합니다. 다음은 이 동작에 대한 예입니다.  

  
 [!code-cpp[concrt-eh-task#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_1.cpp)]  
  
 작업 기반 연속을 사용 하면 선행 작업에서 throw 되는 모든 예외를 처리할 수 있습니다. 작업 기반 연속은 항상 실행 됩니다. 작업이 성공적으로 완료에 예외가 발생 했습니다 또는 취소 되었는지 여부를 중요 하지 않습니다. 작업에서 예외를 throw 하는 경우 작업 기반 연속 실행 되도록 예약 됩니다. 다음 예제에서는 항상 throw 되는 작업을 보여 줍니다. 작업에 두 개의 연속인; 하나는 값 기반 이며 다른 하나는 작업 기반 합니다. 작업 기반 예외가 항상 실행 하 고 따라서 선행 작업에서 throw 되는 예외를 catch 할 수 있습니다. 작업 예외 throw 항상는 않기 때문에 예외가 다시 throw 됩니다 예제에서는 두 연속 끝나기를 대기할 때 `task::get` 또는 `task::wait` 라고 합니다.  
  
 [!code-cpp[concrt-eh-continuations#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_2.cpp)]  
  
 작업 기반 연속을 사용 하 여 처리할 수 있는 예외를 catch 하는 것이 좋습니다. 항상 작업 기반 연속에서 실행 되므로 연속 체인의 끝에 작업 기반 연속을 추가 하려면 사용할지 고려 합니다. 이 코드는 모든 예외를 준수 한다고 보장할 수 있습니다. 다음 예제에서는 기본 값 기반 연속 체인을 보여 줍니다. 체인의 세 번째 작업에서 throw 하 고 따라서 그 뒤에 나오는 모든 값 기반 연속 실행 되지 않습니다. 그러나 최종 연속 작업 기반 이며 따라서 항상 실행 됩니다. 이 최종 연속 세 번째 작업에서 throw 되는 예외를 처리 합니다.  
  
 설정할 수 있는 가장 구체적인 예외를 catch 하는 것이 좋습니다. 특정 예외를 catch가 없는 경우이 최종 작업 기반 연속을 생략할 수 있습니다. 모든 예외는 처리 되지 않은 유지 되 고 응용 프로그램을 종료할 수 있습니다.  
  
 [!code-cpp[concrt-eh-task-chain#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_3.cpp)]  
  
> [!TIP]
>  사용할 수는 [concurrency::task_completion_event::set_exception](../../parallel/concrt/reference/task-completion-event-class.md) 작업 완료 이벤트와 예외를 연결 하는 방법이 있습니다. 문서 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md) 설명는 [concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) 클래스 보다 자세히 설명에서 합니다.  
  

 [concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md) 에 관련 된 중요 한 런타임 예외 형식 인지 `task`합니다. 런타임에서 throw `task_canceled` 호출 하는 경우 `task::get` 해당 작업이 취소 되 고 있습니다. (반대로 `task::wait` 반환 [task_status:: canceled](reference/concurrency-namespace-enums.md#task_group_status) 하며 throw 하지 않습니다.) Catch 하 고 호출 하는 경우 또는 작업 기반 연속에서이 예외를 처리 `task::get`합니다. 작업 취소에 대 한 자세한 내용은 참조 [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.  

  
> [!CAUTION]
>  코드에서 `task_canceled`를 throw하지 마세요. 호출 [concurrency:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) 대신 합니다.  
  
 런타임에서 작업 예외를 throw 한 예외는 연속 또는 기본 응용 프로그램 중 하나는 작업으로는 포착 되지 경우 응용 프로그램을 종료 합니다. 응용 프로그램의 작동이 중단 하는 경우에 c + + 예외가 throw 되 면 중단 하려면 Visual Studio를 구성할 수 있습니다. 처리 되지 않은 예외가의 위치를 진단 한 후 처리에 작업 기반 연속을 사용 합니다.  
  
 섹션 [런타임에서 예외를 Throw](#runtime) 이 문서에 자세히 런타임 예외를 사용 하는 방법에 설명 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="task_groups"></a>작업 그룹 및 병렬 알고리즘  

 이 섹션에서는 런타임 작업 그룹에 의해 throw 되는 예외를 처리 하는 방법을 설명 합니다. 이 섹션에도 적용 됩니다 병렬 알고리즘 같은 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for)작업 그룹을 기반으로 하기 때문에, 합니다.  
  
> [!CAUTION]
>  예외 종속 작업에 미치는 효과 이해 하 고 있는지 확인 합니다. 예외 처리 작업 또는 병렬 알고리즘을 사용 하는 방법에 대 한 모범된 사례에 대 한 참조는 [이해 어떻게 취소 및 예외 처리에 영향을 줄 개체 소멸](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) 유용한 정보는 병렬로 섹션 패턴 라이브러리 항목입니다.  
  
 작업 그룹에 대 한 자세한 내용은 참조 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다. 병렬 알고리즘에 대 한 자세한 내용은 참조 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  

 에 전달 하는 작업 함수의 본문에서 예외를 throw 하는 경우는 [concurrency:: task_group](reference/task-group-class.md) 또는 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 런타임은 해당 예외를 저장 하 고 마샬링합니다 개체 호출 하 여 컨텍스트로 [concurrency::task_group::wait](reference/task-group-class.md#wait), [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait), [run_and_wait](reference/task-group-class.md#run_and_wait), 또는 [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait)합니다. 또한 런타임 (자식 작업 그룹에 포함) 작업 그룹에 있는 모든 활성 작업을 중지 하 고 모든 작업을 아직 시작 되지 않은 무시 합니다.  

  
 다음 예제에서는 예외를 throw 하는 작업 함수의 기본 구조를 보여 줍니다. 이 예제에서는 사용는 `task_group` 두 값을 출력 하는 개체 `point` 병렬로 개체입니다. `print_point` 의 값을 인쇄 하는 작업 함수는 `point` 콘솔에는 개체입니다. 작업 함수는 입력된 값이 경우 예외를 throw `NULL`합니다. 런타임에서이 예외를 저장 하 고 호출 하는 컨텍스트에 마샬링합니다 `task_group::wait`합니다.  
  
 [!code-cpp[concrt-eh-task-group#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_4.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
X = 15, Y = 30Caught exception: point is NULL.  
```  
  
 작업 그룹에서 예외 처리를 사용 하는 전체 예제를 참조 하십시오. [하는 방법: 병렬 루프에서 중단을 사용 하 여 예외 처리](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="runtime"></a>런타임에 의해 발생 한 예외  
 런타임에 대 한 호출에서 예외가 발생할 수 있습니다. 대부분의 예외 종류를 제외 하 고 [concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md) 및 [concurrency::operation_timed_out](../../parallel/concrt/reference/operation-timed-out-class.md), 프로그래밍 오류를 나타냅니다. 이러한 오류는 일반적으로 복구할 수 및 따라서 발생 하거나 안 응용 프로그램 코드에서 처리 합니다. 만 catch 하거나는 프로그래밍 오류를 진단 하려는 경우 응용 프로그램 코드에서 복구할 수 없는 오류를 처리는 것이 좋습니다. 그러나 런타임에 의해 정의 된 예외 형식을 이해 프로그래밍 오류를 진단 하는 데 도움이 됩니다.  
  
 예외 처리 메커니즘은 작업 함수에서 throw 된 예외는 런타임에서 throw 된 예외에 대 한 같습니다. 예를 들어는 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 함수가 throw `operation_timed_out` 때 메시지를 지정된 된 기간 내에 수신 되지 않으면 합니다. 경우 `receive` 작업 그룹에 전달 하면, 런타임에서 해당 예외를 저장 하 고 호출 하는 컨텍스트에 마샬링합니다 작업 함수에서 예외를 throw `task_group::wait`, `structured_task_group::wait`, `task_group::run_and_wait`, 또는 `structured_task_group::run_and_wait`합니다.  
  
 다음 예제에서는 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 알고리즘 동시에 두 가지 작업을 실행 합니다. 첫 번째 작업은 5 초 동안 기다린 다음 메시지 버퍼에 메시지를 보냅니다. 두 번째 작업에서 사용 하는 `receive` 메시지를 받는 메시지 버퍼에서 3 초 동안 대기 하는 함수입니다. `receive` 함수가 throw `operation_timed_out` 기간 내에 메시지를 받지 않을 경우.  
  
 [!code-cpp[concrt-eh-time-out#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_5.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
The operation timed out.  
```  
  
 응용 프로그램의 비정상적인 종료를 방지 하려면 코드에서 런타임을 호출할 때 예외를 처리 해야 합니다. 또한 타사 라이브러리 예를 들어 동시성 런타임을 사용 하는 외부 코드를 호출 하는 경우 예외를 처리 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="multiple"></a>여러 예외  
 작업 또는 병렬 알고리즘을 여러 예외를 수신 하는 경우 런타임에서 호출 컨텍스트에 해당 예외 중 하나만 마샬링합니다. 런타임 예외 마샬링합니다 것을 보장 하지 않습니다.  
  
 다음 예제에서는 `parallel_for` 숫자를 콘솔에 인쇄 하는 알고리즘입니다. 입력된 값이 일부 최소 값 보다 작거나 최대값 보다 큰 경우 예외를 throw 합니다. 이 예제에서는 여러 작업 함수는 예외를 throw 합니다.  
  
 [!code-cpp[concrt-eh-multiple#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_6.cpp)]  
  
 다음이 예제에 대 한 샘플 출력을 보여 줍니다.  
  
```Output  
8293104567Caught exception: -5: the value is less than the minimum.  
```  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="cancellation"></a>취소  
 일부 예외는 오류를 나타냅니다. 예를 들어 검색 알고리즘 결과 발견 하면 연결된 된 작업을 중지 하려면 예외 처리를 사용할 수 있습니다. 코드에서 취소 메커니즘을 사용 하는 방법에 대 한 자세한 내용은 참조 [PPL에서의 취소](../../parallel/concrt/cancellation-in-the-ppl.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="lwts"></a>간단한 작업  
 간단한 작업에서 직접 예약 하는 작업은 한 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 개체입니다. 간단한 작업은 일반적인 작업 보다 오버 헤드가 적습니다. 그러나 런타임에 간단한 작업에서 throw 된 예외를 catch 하지 않습니다. 대신 예외는 기본적으로 프로세스를 종료 하는 처리 되지 않은 예외 처리기에 의해 검색 되었습니다. 따라서 응용 프로그램에서 적절 한 오류 처리 메커니즘을 사용 합니다. 간단한 작업에 대 한 자세한 내용은 참조 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="agents"></a>비동기 에이전트  
 런타임에서 간단한 작업과 마찬가지로 비동기 에이전트에서 throw 된 예외를 관리 하지 않습니다.  
  
 다음 예제에서 파생 된 클래스에서 예외를 처리 하는 방법을 보여 줍니다. [concurrency:: agent](../../parallel/concrt/reference/agent-class.md)합니다. 이 예에서는 정의 `points_agent` 클래스입니다. `points_agent::run` 메서드 읽기 `point` 메시지 버퍼에서 개체를 콘솔에 출력 합니다. `run` 수신 하는 경우 메서드는 예외를 throw 한 `NULL` 포인터입니다.  
  
 `run` 메서드에서 모든 작업을를 포함 한 `try` - `catch` 블록입니다. `catch` 블록은 예외 메시지 버퍼에 저장 합니다. 응용 프로그램 에이전트 완료 된 후 에이전트의이 버퍼에서 읽기만 하 여 오류가 발생 했는지 여부를 확인 합니다.  
  
 [!code-cpp[concrt-eh-agents#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_7.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
X: 10 Y: 20  
X: 20 Y: 30  
error occurred in agent: point must not be NULL  
the status of the agent is: done  
```  
  
 때문에 `try` - `catch` 블록 밖에 있는 `while` 루프 에이전트 처리를 종료 한 첫 번째 오류를 발견 한 경우. 경우는 `try` - `catch` 블록 내부에서 발생는 `while` 루프 에이전트 오류가 발생 한 후 계속 합니다.  
  
 이 예제에서는 실행 될 때 다른 구성 요소 오류에 대 한 에이전트를 모니터링할 수 있도록 메시지 버퍼에 예외를 저장 합니다. 사용 하 여이 예제는 [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) 오류 저장할 개체입니다. 에이전트는 여러 예외를 처리 하는 경우에는 `single_assignment` 클래스에만 첫 번째 메시지 전달 되는 것을 저장 합니다. 만 마지막 예외를 저장 하기 위해 사용 하 여는 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 클래스입니다. 모든 예외를 저장 하기 위해 사용 하 여는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 클래스입니다. 이러한 메시지 블록에 대 한 자세한 내용은 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
 비동기 에이전트에 대 한 자세한 내용은 참조 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="summary"></a> 요약  
 [[맨 위로 이동](#top)]  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [PPL에서의 취소](cancellation-in-the-ppl.md)   
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

