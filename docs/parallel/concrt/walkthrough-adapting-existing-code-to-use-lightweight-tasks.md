---
title: "연습: 간단한 작업을 사용하기 위해 기존 코드 조정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "간단한 작업 사용[동시성 런타임]"
  - "간단한 작업, 사용[동시성 런타임]"
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 간단한 작업을 사용하기 위해 기존 코드 조정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 Windows API를 사용하는 기존 코드를 조정하여 간단한 작업을 사용할 스레드를 만들고 실행하는 방법을 보여 줍니다.  
  
 *간단한 작업*은 [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) 또는 [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체에서 직접 예약하는 작업입니다.  간단한 작업은 동시성 런타임의 일정 예약 기능을 사용하기 위해 기존 코드를 조정할 때 유용합니다.  
  
## 사전 요구 사항  
 이 연습을 시작하기 전에 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md) 항목의 내용을 읽어 보십시오.  
  
## 예제  
  
### 설명  
 다음 예제에서는 스레드를 만들고 실행하는 일반적인 Windows API 사용법을 보여 줍니다.  이 예제에서는 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 함수를 사용하여 별도의 스레드에서 `MyThreadFunction`을 호출합니다.  
  
### 코드  
 [!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]  
  
### 설명  
 이 예제의 결과는 다음과 같습니다.  
  
  **매개 변수 \= 50, 100** 다음 단계에서는 동시성 런타임을 사용하여 같은 작업을 수행하기 위해 코드 예제를 조정하는 방법을 보여 줍니다.  
  
### 간단한 작업을 사용하는 예제를 조정하려면  
  
1.  헤더 파일 concrt.h에 대한 `#include` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]  
  
2.  `concurrency` 네임스페이스에 대한 `using` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]  
  
3.  `__cdecl` 호출 규칙을 사용하고 `void`를 반환하도록 `MyThreadFunction` 선언을 변경합니다.  
  
     [!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]  
  
4.  작업이 끝났음을 주 응용 프로그램에 알리는 [concurrency::event](../../parallel/concrt/reference/event-class.md) 개체를 포함하도록 `MyData` 구조체를 수정합니다.  
  
     [!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]  
  
5.  `CreateThread`에 대한 호출을 [concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md) 메서드에 대한 호출로 대체합니다.  
  
     [!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]  
  
6.  `WaitForSingleObject`에 대한 호출을 [concurrency::event::wait](../Topic/event::wait%20Method.md) 메서드에 대한 호출로 대체하여 작업이 끝나기를 기다립니다.  
  
     [!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]  
  
7.  `CloseHandle`에 대한 호출을 제거합니다.  
  
8.  3단계와 일치하도록 `MyThreadFunction` 정의의 시그니처를 변경합니다.  
  
     [!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]  
  
9. `MyThreadFunction` 함수의 끝에서 [concurrency::event::set](../Topic/event::set%20Method.md) 메서드를 호출하여 작업이 끝났음을 주 응용 프로그램에 알립니다.  
  
     [!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]  
  
10. `MyThreadFunction`에서 `return` 문을 제거합니다.  
  
## 예제  
  
### 설명  
 다음 전체 예제에서는 간단한 작업을 사용하여 `MyThreadFunction` 함수를 호출하는 코드를 보여 줍니다.  
  
### 코드  
 [!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/CPP/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]  
  
### 설명  
  
## 참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Scheduler 클래스](../../parallel/concrt/reference/scheduler-class.md)