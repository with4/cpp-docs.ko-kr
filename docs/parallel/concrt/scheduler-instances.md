---
title: "스케줄러 인스턴스 | Microsoft Docs"
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
  - "스케줄러 인스턴스"
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 스케줄러 인스턴스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 동시성 런타임에서 스케줄러 인스턴스의 역할과 [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) 및 [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) 클래스를 사용하여 스케줄러 인스턴스를 만들고 관리하는 방법에 대해 설명합니다.  스케줄러 인스턴스는 명시적 일정 예약 정책을 특정 유형의 작업 부하와 연결하려는 경우 유용합니다.  예를 들어 하나의 스케줄러 인스턴스를 만들어 높은 스레드 우선 순위에서 일부 작업을 실행하고 기본 스케줄러를 사용하여 보통 스레드 우선 순위에서 다른 작업을 실행할 수 있습니다.  
  
> [!TIP]
>  동시성 런타임에서 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다.  작업 스케줄러를 사용하면 응용 프로그램의 성능을 세부적으로 조정할 수 있으므로 동시성 런타임을 처음 사용하는 경우 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)에서 시작하는 것이 좋습니다.  
  
##  <a name="top"></a> 단원  
  
-   [Scheduler 및 CurrentScheduler 클래스](#classes)  
  
-   [스케줄러 인스턴스 만들기](#creating)  
  
-   [스케줄러 인스턴스의 수명 관리](#managing)  
  
-   [메서드 및 기능](#features)  
  
-   [예제](#example)  
  
##  <a name="classes"></a> Scheduler 및 CurrentScheduler 클래스  
 작업 스케줄러를 사용하면 응용 프로그램에서 하나 이상의 *스케줄러 인스턴스*를 사용하여 작업을 예약할 수 있습니다.  [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) 클래스는 스케줄러 인스턴스를 나타내고 작업 예약과 관련된 기능을 캡슐화합니다.  
  
 스케줄러에 연결된 스레드를 *실행 컨텍스트* 또는 *컨텍스트*라고 합니다.  언제든지 하나의 스케줄러가 현재 컨텍스트에서 활성화될 수 있습니다.  활성 스케줄러는 *현재 스케줄러*라고도 합니다.  동시성 런타임은 [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) 클래스를 사용하여 현재 스케줄러에 액세스할 수 있습니다.  한 컨텍스트에 대한 현재 스케줄러는 다른 컨텍스트의 현재 스케줄러와 다를 수 있습니다.  런타임에서는 현재 스케줄러를 프로세스 수준으로 표현하지 않습니다.  
  
 일반적으로 `CurrentScheduler` 클래스는 현재 스케줄러에 액세스할 때 사용됩니다.  `Scheduler` 클래스는 현재 스케줄러가 아닌 스케줄러를 관리해야 하는 경우에 유용합니다.  
  
 다음 단원에서는 스케줄러 인스턴스를 만들고 관리하는 방법에 대해 설명합니다.  이러한 작업을 보여 주는 전체 예제를 보려면 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="creating"></a> 스케줄러 인스턴스 만들기  
 다음과 같은 세 가지 방법을 사용하여 `Scheduler` 개체를 만들 수 있습니다.  
  
-   스케줄러가 없는 경우 병렬 알고리즘과 같은 런타임 기능을 사용하여 작업을 수행할 때 런타임에서 자동으로 기본 스케줄러를 만듭니다.  기본 스케줄러는 병렬 작업을 시작하는 컨텍스트의 현재 스케줄러가 됩니다.  
  
-   [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md) 메서드는 특정 정책을 사용하고 해당 스케줄러를 현재 컨텍스트와 연결하는 `Scheduler` 개체를 만듭니다.  
  
-   [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) 메서드는 특정 정책을 사용하지만 현재 컨텍스트와 연결하지 않는 `Scheduler` 개체를 만듭니다.  
  
 런타임에서 기본 스케줄러를 만들 수 있으면 모든 동시 작업에서 같은 스케줄러를 공유할 수 있습니다.  일반적으로 PPL\([병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md)\) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)에서 제공하는 기능은 병렬 작업을 수행하는 데 사용됩니다.  따라서 정책 또는 수명을 제어하기 위해 스케줄러로 직접 작업할 필요가 없습니다.  PPL 또는 에이전트 라이브러리를 사용하는 경우 런타임에서는 기본 스케줄러가 없으면 새로 만들어 각 컨텍스트의 현재 스케줄러로 설정합니다.  스케줄러를 만들고 현재 스케줄러로 설정하면 런타임에서 해당 스케줄러를 사용하여 작업을 예약합니다.  특정한 일정 예약 정책이 필요한 경우에만 추가 스케줄러 인스턴스를 만듭니다.  스케줄러와 연결된 정책에 대한 자세한 내용은 [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)을 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="managing"></a> 스케줄러 인스턴스의 수명 관리  
 런타임에서는 참조 횟수 메커니즘을 사용하여 `Scheduler` 개체의 수명을 제어합니다.  
  
 `CurrentScheduler::Create` 메서드 또는 `Scheduler::Create` 메서드를 사용하여 `Scheduler` 개체를 만드는 경우 런타임에서는 해당 스케줄러의 초기 참조 횟수를 1로 설정합니다.  [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md) 메서드를 호출하면 런타임에서 참조 횟수를 증가시킵니다.  `Scheduler::Attach` 메서드는 `Scheduler` 개체를 현재 컨텍스트와 함께 연결합니다.  그러면 이 개체가 현재 스케줄러로 설정됩니다.  `CurrentScheduler::Create` 메서드를 호출하는 경우 런타임에서는 `Scheduler` 개체를 만들어 현재 컨텍스트에 연결하고 참조 횟수를 1로 설정합니다.  [concurrency::Scheduler::Reference](../Topic/Scheduler::Reference%20Method.md) 메서드를 사용하여 `Scheduler` 개체의 참조 횟수를 증가시킬 수도 있습니다.  
  
 [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) 메서드를 호출하여 현재 스케줄러를 분리하거나, [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md) 메서드를 호출하면 런타임에서 참조 횟수를 감소시킵니다.  참조 횟수가 0에 도달하면 예약된 모든 작업이 끝난 후 런타임에서 `Scheduler` 개체를 소멸시킵니다.  실행 중인 작업은 현재 스케줄러의 참조 횟수를 증가시킬 수 있습니다.  따라서 참조 횟수가 0에 도달하는 경우 작업에서 참조 횟수를 증가시키면 런타임에서는 참조 횟수가 다시 0이 되고 모든 작업이 끝날 때까지 `Scheduler` 개체를 소멸시키지 않습니다.  
  
 런타임에서는 각 컨텍스트에 대한 `Scheduler` 개체의 내부 스택을 유지 관리합니다.  `Scheduler::Attach` 또는 `CurrentScheduler::Create` 메서드를 호출하는 경우 런타임에서는 해당 `Scheduler` 개체를 현재 컨텍스트의 스택에 넣습니다.  그러면 이 개체가 현재 스케줄러로 설정됩니다.  `CurrentScheduler::Detach`를 호출하면 런타임에서는 현재 컨텍스트의 스택에서 현재 스케줄러를 꺼내고 이전 스케줄러를 현재 스케줄러로 설정합니다.  
  
 런타임에서는 스케줄러 인스턴스의 수명을 관리하는 몇 가지 방법을 제공합니다.  다음 표에서는 스케줄러를 만들거나 현재 컨텍스트에 연결하는 각 메서드에 대해 현재 컨텍스트에서 스케줄러를 해제하거나 분리하는 메서드를 보여 줍니다.  
  
|만들기 또는 연결 메서드|해제 또는 분리 메서드|  
|-------------------|------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 적절하지 않은 해제 또는 분리 메서드를 호출하면 런타임에서 지정되지 않은 동작이 발생합니다.  
  
 예를 들어 PPL과 같이 런타임에서 자동으로 기본 스케줄러를 만드는 기능을 사용할 경우에는 이 스케줄러를 해제하거나 분리하지 않습니다.  런타임에서는 자신이 만드는 스케줄러의 수명을 관리합니다.  
  
 런타임에서는 모든 작업이 끝나기 전에 `Scheduler` 개체를 소멸시키지 않으므로 [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md) 메서드 또는 [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md) 메서드를 사용하면 `Scheduler` 개체가 소멸되는 경우 알림을 받을 수 있습니다.  이 방법은 `Scheduler` 개체에 예약된 모든 작업이 끝날 때까지 기다려야 하는 경우에 유용합니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="features"></a> 메서드 및 기능  
 이 단원에서는 `CurrentScheduler` 및 `Scheduler` 클래스의 중요한 메서드에 대해 요약하여 설명합니다.  
  
 `CurrentScheduler` 클래스를 현재 컨텍스트에서 사용할 스케줄러를 만들기 위한 도우미로 간주하십시오.  `Scheduler` 클래스를 사용하면 다른 컨텍스트에 속한 스케줄러를 제어할 수 있습니다.  
  
 다음 표에서는 `CurrentScheduler` 클래스에 정의된 중요한 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[Create](../Topic/CurrentScheduler::Create%20Method.md)|지정된 정책을 사용하는 `Scheduler` 개체를 만들고 현재 컨텍스트와 연결합니다.|  
|[Get](../Topic/CurrentScheduler::Get%20Method.md)|현재 컨텍스트와 연결된 `Scheduler` 개체에 대한 포인터를 검색합니다.  이 메서드는 `Scheduler` 개체의 참조 횟수를 증가시키지 않습니다.|  
|[분리](../Topic/CurrentScheduler::Detach%20Method.md)|현재 컨텍스트에서 현재 스케줄러를 분리하고 이전 스케줄러를 현재 스케줄러로 설정합니다.|  
|[RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|현재 스케줄러가 소멸되면 런타임에서 설정하는 이벤트를 등록합니다.|  
|[CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|현재 스케줄러에 [concurrency::Concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체를 만듭니다.|  
|[ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|현재 스케줄러의 일정 큐에 간단한 작업을 추가합니다.|  
|[GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md)|현재 스케줄러와 연결된 정책의 복사본을 검색합니다.|  
  
 다음 표에서는 `Scheduler` 클래스에 정의된 중요한 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[Create](../Topic/Scheduler::Create%20Method.md)|지정된 정책을 사용하는 `Scheduler` 개체를 만듭니다.|  
|[연결](../Topic/Scheduler::Attach%20Method.md)|`Scheduler` 개체를 현재 컨텍스트와 함께 연결합니다.|  
|[참고 항목](../Topic/Scheduler::Reference%20Method.md)|`Scheduler` 개체의 참조 카운터를 증가시킵니다.|  
|[Release](../Topic/Scheduler::Release%20Method.md)|`Scheduler` 개체의 참조 카운터를 감소시킵니다.|  
|[RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|`Scheduler` 개체가 소멸되면 런타임에서 설정하는 이벤트를 등록합니다.|  
|[CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|`Scheduler` 개체에 [concurrency::Concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체를 만듭니다.|  
|[ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md)|`Scheduler` 개체에서 간단한 작업을 예약합니다.|  
|[GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md)|`Scheduler` 개체와 연결된 정책의 복사본을 검색합니다.|  
|[SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|런타임에서 기본 스케줄러를 만들 때 사용할 정책을 설정합니다.|  
|[ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|기본 정책을 `SetDefaultSchedulerPolicy`를 호출하기 전의 활성 정책으로 복원합니다.  이 호출 후에 기본 스케줄러가 만들어진 경우 런타임에서는 기본 정책 설정을 사용하여 스케줄러를 만듭니다.|  
  
 \[[맨 위](#top)\]  
  
##  <a name="example"></a> 예제  
 스케줄러 인스턴스를 만들고 관리하는 방법을 보여 주는 기본 예제를 보려면 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)를 참조하십시오.  
  
## 참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)   
 [일정 그룹](../../parallel/concrt/schedule-groups.md)