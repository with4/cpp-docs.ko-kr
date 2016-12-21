---
title: "방법: 스케줄러 인스턴스 관리 | Microsoft Docs"
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
  - "스케줄러 인스턴스 관리[동시성 런타임]"
  - "스케줄러 인스턴스, 관리[동시성 런타임]"
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 스케줄러 인스턴스 관리
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스케줄러 인스턴스를 사용하면 특정한 일정 예약 정책을 다양한 유형의 업무와 연결할 수 있습니다.  이 항목에는 스케줄러 인스턴스를 만들고 관리하는 방법을 보여 주는 두 가지 기본 예제가 포함되어 있습니다.  
  
 이 예제에서는 기본 스케줄러 정책을 사용하는 스케줄러를 만듭니다.  사용자 지정 정책을 사용하는 스케줄러를 만드는 예제를 보려면 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)을 참조하십시오.  
  
### 응용 프로그램에서 스케줄러 인스턴스를 관리하려면  
  
1.  스케줄러에서 사용할 정책 값을 포함하는 [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) 개체를 만듭니다.  
  
2.  [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md) 메서드 또는 [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) 메서드를 호출하여 스케줄러 인스턴스를 만듭니다.  
  
     `Scheduler::Create` 메서드를 사용하는 경우에는 스케줄러를 현재 컨텍스트와 연결해야 할 때 [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md) 메서드를 호출합니다.  
  
3.  [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) 함수를 호출하여 신호를 받지 않는 자동 재설정 이벤트 개체에 대한 핸들을 만듭니다.  
  
4.  이전 단계에서 만든 이벤트 개체에 대한 핸들을 [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md) 메서드 또는 [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md) 메서드에 전달합니다.  이렇게 하면 스케줄러가 소멸될 때 설정할 이벤트가 등록됩니다.  
  
5.  현재 스케줄러로 예약할 작업을 수행합니다.  
  
6.  [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) 메서드를 호출하여 현재 스케줄러를 분리하고 이전 스케줄러를 현재 스케줄러로 복원합니다.  
  
     `Scheduler::Create` 메서드를 사용하는 경우에는 [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md) 메서드를 호출하여 `Scheduler` 개체의 참조 횟수를 감소시킵니다.  
  
7.  이벤트에 대한 핸들을 [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) 함수에 전달하여 스케줄러가 종료될 때까지 기다립니다.  
  
8.  [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) 함수를 호출하여 이벤트 개체에 대한 핸들을 닫습니다.  
  
## 예제  
 다음 코드에서는 스케줄러 인스턴스를 관리하는 두 가지 방법을 보여 줍니다.  각 예제에서는 먼저 기본 스케줄러를 사용하여 현재 스케줄러의 고유 식별자를 출력하는 작업을 수행합니다.  그런 다음 스케줄러 인스턴스를 사용하여 같은 작업을 다시 수행합니다.  마지막으로 기본 스케줄러를 현재 스케줄러로 복원하고 작업을 한 번 더 수행합니다.  
  
 첫 번째 예제에서는 [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) 클래스를 사용하여 스케줄러 인스턴스를 만들고 현재 컨텍스트와 연결합니다.  두 번째 예제에서는 [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) 클래스를 사용하여 같은 작업을 수행합니다.  일반적으로 `CurrentScheduler` 클래스는 현재 스케줄러로 작업할 때 사용됩니다.  `Scheduler` 클래스를 사용하는 두 번째 예제는 스케줄러가 현재 컨텍스트와 연결되는 시기를 제어하려는 경우 또는 특정 스케줄러를 특정 작업과 연결하려는 경우에 유용합니다.  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/CPP/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **CurrentScheduler 클래스를 사용하여...**  
**현재 스케줄러 id: 0**  
**만들고 스케줄러에 연결 중...**  
**현재 스케줄러 id: 1**  
**스케줄러를 분리 하는 중...**  
**현재 스케줄러 id: 0**  
**Scheduler 클래스를 사용하여...**  
**현재 스케줄러 id: 0**  
**스케줄러를 만드는 중...**  
**스케줄러를 붙이는 중...**  
**현재 스케줄러 id: 2**  
**스케줄러를 분리 하는 중...**  
**현재 스케줄러 id: 0**   
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는`scheduler-instance.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc scheduler\-instance.cpp**  
  
## 참고 항목  
 [스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)   
 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)