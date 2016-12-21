---
title: "스케줄러 정책 | Microsoft Docs"
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
  - "스케줄러 정책"
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
caps.latest.revision: 12
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 스케줄러 정책
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 동시성 런타임에서 스케줄러 정책의 역할에 대해 설명합니다.  *스케줄러 정책*은 스케줄러에서 작업을 관리할 때 사용하는 전략을 제어합니다.  예를 들어,  `THREAD_PRIORITY_NORMAL` 을 실행하는 일부 작업과  `THREAD_PRIORITY_HIGHEST` 을 실행하는 다른 작업에 필요한 응용 프로그램을 고려합니다.  두 가지 스케줄러 인스턴스를 만들 수 있습니다:  `ContextPriority`  정책을  `THREAD_PRIORITY_NORMAL` 로, 같은 정책을 지정하는 또다른 개체를  `THREAD_PRIORITY_HIGHEST` 로 지정합니다.  
  
 스케줄러 정책을 사용하면 사용 가능한 처리 리소스를 나누고 고정된 리소스 집합을 각 스케줄러에 할당할 수 있습니다.  예를 들어 프로세서를 최대 네 개로 확장하는 병렬 알고리즘을 가정해 봅니다.  작업에서 최대 네 개의 프로세서를 동시에 사용하도록 제한하는 스케줄러 정책을 만들 수 있습니다.  
  
> [!TIP]
>  동시성 런타임에서 기본 스케줄러를 제공합니다.  따라서 응용 프로그램에서 만들 필요가 없습니다.  작업 스케줄러를 사용하면 응용 프로그램의 성능을 세부적으로 조정할 수 있으므로 동시성 런타임을 처음 사용하는 경우 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)에서 시작하는 것이 좋습니다.  
  
 [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md), [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) 또는 [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) 메서드를 사용하여 스케줄러 인스턴스를 만드는 경우 스케줄러의 동작을 지정하는 키\-값 쌍 컬렉션이 들어 있는 [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) 개체를 제공합니다.  `SchedulerPolicy` 생성자는 다양한 수의 인수를 사용합니다.  첫 번째 인수는 지정할 정책 요소의 수입니다.  나머지 인수는 각 정책 요소의 키\/값 쌍입니다.  다음 예제에서는 세 개의 정책 요소를 지정하는 `SchedulerPolicy` 개체를 만듭니다.  런타임에서는 지정되지 않은 정책 키의 해당 기본값을 사용합니다.  
  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/CPP/scheduler-policies_1.cpp)]  
  
 [concurrency::PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md) 열거형은 작업 스케줄러와 연결된 정책 키를 정의합니다.  다음 표에서는 정책 키 및 런타임에서 각 정책 키에 사용하는 기본값에 대해 설명합니다.  
  
|정책 키|설명|기본값|  
|----------|--------|---------|  
|`SchedulerKind`|작업을 예약할 때 일반 스레드를 사용할지 아니면 UMS 스레드를 사용할지를 지정하는 [concurrency::SchedulerType](../Topic/SchedulerType%20Enumeration.md) 값입니다.|`ThreadScheduler`\(정상적인 스레드 사용\).  이 키에 유효한 값입니다.|  
|`MaxConcurrency`|스케줄러에서 사용하는 최대 동시성 리소스 수를 지정하는 `unsigned int` 값입니다.|[concurrency::MaxExecutionResources](../Topic/MaxExecutionResources%20Constant.md)|  
|`MinConcurrency`|스케줄러에서 사용하는 최소 동시성 리소스 수를 지정하는 `unsigned int` 값입니다.|`1`|  
|`TargetOversubscriptionFactor`|각 처리 리소스에 할당할 스레드의 수를 지정하는 `unsigned int` 값입니다.|`1`|  
|`LocalContextCacheSize`|각 가상 프로세서의 로컬 큐에 캐시할 수 있는 최대 컨텍스트 수를 지정하는 `unsigned int` 값입니다.|`8`|  
|`ContextStackSize`|각 컨텍스트에 대해 예약할 스택 크기\(KB\)를 지정하는 `unsigned int` 값입니다.|`0`\(기본 스택 크기 사용\)|  
|`ContextPriority`|각 컨텍스트의 스레드 우선 순위를 지정하는 `int` 값입니다.  이 값은 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 또는 `INHERIT_THREAD_PRIORITY`에 전달할 수 있는 임의의 값이 될 수 있습니다.|`THREAD_PRIORITY_NORMAL`|  
|`SchedulingProtocol`|사용할 예약 알고리즘을 지정하는 [concurrency::SchedulingProtocolType](../Topic/SchedulingProtocolType%20Enumeration.md) 값입니다.|`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`|통계에 기반한 진행 정보에 따라 리소스를 다시 분산시킬지 여부를 지정하는 [concurrency::DynamicProgressFeedbackType](../Topic/DynamicProgressFeedbackType%20Enumeration.md) 값입니다.<br /><br /> **참고** 런타임에서 사용하기 위해 예약되어 있기 때문에  `ProgressFeedbackDisabled`  에 이 정책을 설정하지 마십시오.|`ProgressFeedbackEnabled`|  
  
 각 스케줄러는 작업을 예약할 때 자체의 정책을 사용합니다.  한 스케줄러와 연결된 정책은 다른 스케줄러의 동작에 영향을 주지 않습니다.  또한 `Scheduler` 개체를 만든 후에는 스케줄러 정책을 변경할 수 없습니다.  
  
> [!IMPORTANT]
>  런타임에서 만든 스레드에 대한 특성을 제어할 때는 스케줄러 정책만 사용하십시오.  정의되지 않은 동작이 발생할 수 있기 때문에 런타임에 의해 생성 된 스레드의 스레드 선호도 또는 우선 순위를 변경하지 마십시오.  
  
 기본 스케줄러를 명시적으로 만들지 않으면 런타임에서 기본 스케줄러가 자동으로 만들어집니다.  응용 프로그램에서 기본 스케줄러를 사용하되 해당 스케줄러에서 사용할 정책을 지정하려는 경우 병렬 작업을 예약하기 전에 [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) 메서드를 호출합니다.  `Scheduler::SetDefaultSchedulerPolicy` 메서드를 호출하지 않으면 런타임에서는 이 표의 기본 정책 값을 사용합니다.  
  
 스케줄러 정책의 복사본을 검색하려면 [concurrency::CurrentScheduler::GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md) 및 [concurrency::Scheduler::GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md) 메서드를 사용합니다.  이러한 메서드로부터 받는 정책 값은 스케줄러를 만들 때 지정하는 정책 값과 다를 수 있습니다.  
  
## 예제  
 특정 스케줄러 정책을 사용하여 스케줄러의 동작을 제어하는 예제를 보려면 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) 및 [방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)를 참조하십시오.  
  
## 참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)