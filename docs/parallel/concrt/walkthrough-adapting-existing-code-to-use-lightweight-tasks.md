---
title: "연습: 간단한 작업을 사용 하도록 기존 코드를 조정 | Microsoft Docs"
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
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a50ad04421d7b4bcdc4a2c98de8f5a57b255c75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>연습: 간단한 작업을 사용하기 위해 기존 코드 조정
이 항목에서는 Windows API를 사용 하 여 만들고 간단한 작업을 사용 하는 스레드를 실행 하는 기존 코드를 조정 하는 방법을 보여 줍니다.  
  
 A *간단한 작업* 에서 직접 예약 하는 작업은 한 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 또는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체입니다. 간단한 작업은 동시성 런타임의 일정 예약 기능을 사용하도록 기존 코드를 조정하는 경우에 유용합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 시작 하기 전에 항목을 읽어 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예제를 만들고 스레드를 실행 하는 Windows API의 일반적인 사용입니다. 사용 하 여이 예제는 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 함수를 호출 하는 `MyThreadFunction` 별도 스레드에서 합니다.  
  
### <a name="code"></a>코드  
 [!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]  
  
### <a name="comments"></a>설명  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Parameters = 50, 100  
```  
  
 다음 단계에는 동일한 작업을 수행 하도록 동시성 런타임을 사용 하도록 코드 예제를 조정 하는 방법을 보여 줍니다.  
  
### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>간단한 작업을 사용 하도록 예제를 조정 하려면  
  
1.  추가 `#include` 헤더 파일 concrt.h에 대 한 지시문입니다.  
  
 [!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]  
  
2.  추가 `using` 에 대 한 지시문은 `concurrency` 네임 스페이스입니다.  
  
 [!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]  
  
3.  선언을 변경 `MyThreadFunction` 사용 하는 `__cdecl` 호출 규칙 반환 하도록 `void`합니다.  
  
 [!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]  
  
4.  수정 된 `MyData` 구조를 포함 하도록는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 작업이 끝났음을 주 응용 프로그램에 알리는 개체입니다.  
  
 [!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]  
  
5.  호출을 `CreateThread` 을 호출 하 여는 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask) 메서드.  

  
 [!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]  
  

6.  호출을 `WaitForSingleObject` 을 호출 하 여는 [concurrency::event::wait](reference/event-class.md#wait) 메서드는 작업이 완료 되기를 기다려야 합니다.  

 [!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]  
  
7.  호출을 제거 `CloseHandle`합니다.  
  
8.  정의의 서명을 변경 `MyThreadFunction` 3 단계와 일치 하도록 합니다.  
  
 [!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]  
  
9. 끝에는 `MyThreadFunction` 함수를 호출 하는 [concurrency::event::set](reference/event-class.md#set) 메서드를 작업이 끝났음을 주 응용 프로그램에 알립니다.  
  
 [!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]  
  
10. 제거는 `return` 에서 문을 `MyThreadFunction`합니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 완성 된 예제에서는 코드를 호출 하는 간단한 작업을 사용 하 여 `MyThreadFunction` 함수입니다.  
  
### <a name="code"></a>코드  
 [!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]  
  
### <a name="comments"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Scheduler 클래스](../../parallel/concrt/reference/scheduler-class.md)
