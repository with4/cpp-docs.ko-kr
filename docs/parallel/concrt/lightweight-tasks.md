---
title: "간단한 작업 | Microsoft Docs"
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
  - "간단한 작업"
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 간단한 작업
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 동시성 런타임에서 간단한 작업이 차지하는 역할에 대해 설명합니다.  *간단한 작업*은 `concurrency::Scheduler` 또는 `concurrency::ScheduleGroup` 개체에서 직접 예약하는 작업입니다.  간단한 작업은 Windows API [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 함수에 제공하는 함수와 유사합니다.  따라서 간단한 작업은 동시성 런타임의 일정 예약 기능을 사용하기 위해 기존 코드를 조정할 때 유용합니다.  동시성 런타임 자체에서 간단한 작업을 사용하여 비동기 에이전트를 예약하고 비동기 메시지 블록 간에 메시지를 보냅니다.  
  
> [!TIP]
>  동시성 런타임에서 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다.  작업 스케줄러를 사용하면 응용 프로그램의 성능을 세부적으로 조정할 수 있으므로 동시성 런타임을 처음 사용하는 경우 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)에서 시작하는 것이 좋습니다.  
  
 간단한 작업은 비동기 에이전트 및 작업 그룹에 비해 오버헤드가 적습니다.  예를 들어 런타임에서는 간단한 작업이 끝날 때 사용자에게 알려 주지 않습니다.  또한 런타임에서는 간단한 작업에서 throw되는 예외를 catch하거나 처리하지 않습니다.  예외 처리 및 간단한 작업에 대한 자세한 내용은 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)를 참조하십시오.  
  
 대부분의 작업의 경우 복잡한 작업을 기본적인 작업으로 쉽게 분할할 수 있는 더 강력한 기능\(예: 작업 그룹, 병렬 알고리즘\)을 사용하는 것이 좋습니다.  작업 그룹에 대한 자세한 내용은 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)를 참조하십시오.  병렬 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
 간단한 작업을 만들려면 [concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md), [concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md) 또는 [concurrency::Scheduler::ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md) 메서드를 호출합니다.  간단한 작업이 끝나기를 기다리려면 부모 스케줄러가 종료할 때까지 기다리거나 [concurrency::event](../../parallel/concrt/reference/event-class.md) 개체와 같은 동기화 메커니즘을 사용합니다.  
  
## 예제  
 기존 코드를 조정하여 간단한 작업을 사용하는 방법을 보여 주는 예제를 보려면 [연습: 간단한 작업을 사용하기 위해 기존 코드 조정](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)을 참조하십시오.  
  
## 참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [연습: 간단한 작업을 사용하기 위해 기존 코드 조정](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)