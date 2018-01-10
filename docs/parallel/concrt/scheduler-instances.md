---
title: "스케줄러 인스턴스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1688a2b689b3fc3391e617f3d65d3c681f05a84f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="scheduler-instances"></a>Scheduler 인스턴스
이 문서에서는 동시성 런타임 및 사용 하는 방법에 대 한 스케줄러 인스턴스의 역할과 설명는 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 및 [concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 만들고 관리 하는 클래스 스케줄러 인스턴스입니다. 스케줄러 인스턴스는 특정 유형의 작업 부하와 명시적 일정 예약 정책을 연결 하려는 경우에 유용 합니다. 예를 들어 높은 스레드 우선 순위로 일부 작업을 실행하기 위한 스케줄러 인스턴스를 하나 만들고, 기본 스케줄러를 사용하여 보통 스레드 우선 순위로 다른 작업을 실행할 수 있습니다.  
  
> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다. 작업 스케줄러를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 때문에로 시작 하는 것이 좋습니다는 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 하려는 경우 동시성 런타임으로 새입니다.  
  
##  <a name="top"></a> 섹션  
  
-   [스케줄러 및 CurrentScheduler 클래스](#classes)  
  
-   [스케줄러 인스턴스 만들기](#creating)  
  
-   [스케줄러 인스턴스 수명 관리](#managing)  
  
-   [메서드 및 기능](#features)  
  
-   [예제](#example)  
  
##  <a name="classes"></a>스케줄러 및 CurrentScheduler 클래스  
 작업 스케줄러를 사용 하면 하나 이상의 응용 프로그램 *스케줄러 인스턴스* 작업 일정을 예약할 합니다. [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 클래스는 스케줄러 인스턴스를 나타내고 작업 예약과 관련 된 기능을 캡슐화 합니다.  
  
 스케줄러에 연결 하는 스레드는 라고는 *실행 컨텍스트*, 또는 그냥 *컨텍스트*합니다. 언제 든 지 한 스케줄러를 현재 컨텍스트에서 활성화할 수 있습니다. 활성 스케줄러가 라고도 *현재 스케줄러*합니다. 동시성 런타임에서 사용 하 여는 [concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 를 현재 스케줄러에 대 한 액세스를 제공 하는 클래스입니다. 한 컨텍스트가 대 한 현재 스케줄러 다른 컨텍스트에 대 한 현재 스케줄러에서 다를 수 있습니다. 런타임에서 현재 스케줄러에 대 한 프로세스 수준의 표현을 제공 하지 않습니다.  
  
 일반적으로 `CurrentScheduler` 클래스 현재 스케줄러에 액세스 하는 데 사용 됩니다. `Scheduler` 클래스는 스케줄러를 현재 관리 해야 하는 경우 유용 합니다.  
  
 다음 섹션에는 만들고 스케줄러 인스턴스를 관리 하는 방법을 설명 합니다. 이러한 작업을 보여 주는 전체 예제를 참조 하십시오. [하는 방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="creating"></a>스케줄러 인스턴스 만들기  
 이러한 세 가지 방법으로 만들려는 `Scheduler` 개체:  
  
-   스케줄러가 없는 경우 런타임 기능을 예를 들어 병렬 알고리즘을 사용 하 여 작업을 수행 하는 경우 런타임은 기본 스케줄러를 만듭니다. 기본 스케줄러는 병렬 작업을 시작 하는 컨텍스트에 대 한 현재 스케줄러가 됩니다.  
  

-   [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) 메서드 만듭니다는 `Scheduler` 는 특정 정책을 사용 하 고 해당 스케줄러 현재 컨텍스트와 연결 하는 개체입니다.  
  
-   [concurrency::Scheduler::Create](reference/scheduler-class.md#create) 메서드 만듭니다는 `Scheduler` 개체는 특정 정책을 사용 하지만 현재 컨텍스트와 연결 하지는 않습니다.  

  
 런타임은 기본 스케줄러를 만들 수 있도록 하는 동일한 스케줄러를 공유 하는 모든 동시 작업 수 있습니다. 기능에서 제공 되는 일반적으로 [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 병렬 작업을 수행 하는 데 사용 됩니다. 따라서 정책 또는 수명을 제어 하기 위해 스케줄러를 직접 작업할 필요가 없습니다. PPL 또는 에이전트 라이브러리를 사용 하면 각 컨텍스트에 대 한 현재 스케줄러를 사용 하면 존재 하지 않는 경우 런타임은 기본 스케줄러를 만듭니다. 스케줄러 만들기 및 작업을 예약 하도록 해당 스케줄러 공용 언어 런타임은 다음 현재 스케줄러로 설정 합니다. 특정 일정 예약 정책이 필요한 경우에 추가 스케줄러 인스턴스를 만듭니다. 스케줄러와 연결 된 정책에 대 한 자세한 내용은 참조 하십시오. [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="managing"></a>스케줄러 인스턴스 수명 관리  
 런타임에서 참조 횟수 메커니즘의 수명을 제어를 사용 하 여 `Scheduler` 개체입니다.  
  

 사용 하는 경우는 `CurrentScheduler::Create` 메서드 또는 `Scheduler::Create` 만드는 메서드를 한 `Scheduler` 개체를 런타임에 하나에 해당 스케줄러의 초기 참조 횟수를 설정 합니다. 호출 하면 런타임에서 참조 횟수를 증가 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) 메서드. `Scheduler::Attach` 메서드 associates는 `Scheduler` 개체를 현재 컨텍스트와 함께 합니다. 따라서 현재 스케줄러 있습니다. 호출 하는 경우는 `CurrentScheduler::Create` 이 메서드는 런타임에서 생성 된 `Scheduler` 개체 및 현재 컨텍스트에 (및 참조 횟수를 하나로 설정). 사용할 수도 있습니다는 [concurrency::Scheduler::Reference](reference/scheduler-class.md#reference) 의 참조 횟수를 증가 하는 메서드는 `Scheduler` 개체입니다.  
  
 참조 횟수를 호출 하는 경우 런타임 감소는 [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) 현재 스케줄러를 분리 하는 메서드를 호출 하거나는 [concurrency::Scheduler::Release](reference/scheduler-class.md#release) 메서드. 런타임에서 소멸 참조 수가 0에 도달 하면는 `Scheduler` 개체 결국 작업 완료를 예약 합니다. 실행 중인 작업을 현재 스케줄러의 참조 횟수를 증가 수 있습니다. 따라서 참조 수가 0에 도달 하는 경우 참조 횟수를 증가 하는 작업의 런타임 제거 하지 않습니다는 `Scheduler` 참조 횟수가 다시 0이 되 고 모든 작업이 완료 될 때까지 개체입니다.  

  
 런타임에서의 내부 스택을 유지 `Scheduler` 각 컨텍스트에 대 한 개체입니다. 호출 하는 경우는 `Scheduler::Attach` 또는 `CurrentScheduler::Create` 메서드를 런타임 푸시 `Scheduler` 개체를 현재 컨텍스트에 대 한 합니다. 따라서 현재 스케줄러 있습니다. 호출 하는 경우 `CurrentScheduler::Detach`, 런타임은 현재 스케줄러 현재 컨텍스트에 대 한 스택에서 팝 하 고 이전과 현재 스케줄러로 설정 합니다.  
  
 런타임에서는 스케줄러 인스턴스의 수명을 관리 하는 여러 방법을 제공 합니다. 다음 표에서 해제 하거나 현재 컨텍스트에서 생성 하거나 스케줄러를 현재 컨텍스트에 연결 하는 각 방법에 대해 스케줄러를 분리 하는 적절 한 방법을 보여 줍니다.  
  
|만들기 또는 attach 메서드|임대 해제 또는 detach 메서드|  
|-----------------------------|------------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 호출 적절 하지 않은 임대 해제 또는 메서드는 런타임에서 지정 되지 않은 동작이 생성을 분리 합니다.  
  
 예를 들어 PPL, 기본 스케줄러를 만들려는 런타임 시키는 기능을 사용 하는 경우 해제 하지 않거나이 스케줄러를 분리 합니다. 런타임에서 생성 된 스케줄러의 수명을 관리 합니다.  
  

 런타임에서 소멸 시 키 지 않는 때문에 `Scheduler` 사용할 수 있는 모든 작업을 완료 하기 전에 개체를는 [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) 메서드 또는 [concurrency:: currentscheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) 알림을 받기를 끝내 메서드 때는 `Scheduler` 개체를 제거 합니다. 에 예약 된 모든 작업에 대 한 대기 해야 할 때 유용는 `Scheduler` 개체를 완료 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="features"></a>메서드 및 기능  
 이 섹션의 중요 한 메서드에 대해 요약 하는 `CurrentScheduler` 및 `Scheduler` 클래스입니다.  
  
 간주할는 `CurrentScheduler` 으로 현재 컨텍스트에서 사용 하기 위해 스케줄러를 만들기 위한 도우미 클래스입니다. `Scheduler` 클래스를 사용 하면 다른 컨텍스트에 속하는 스케줄러 제어할 수 있습니다.  
  
 다음 표에서 여 정의 된 중요 한 메서드는 `CurrentScheduler` 클래스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[만들기](reference/currentscheduler-class.md#create)|만듭니다는 `Scheduler` 지정 된 정책을 사용 하 고 현재 컨텍스트와 연결 하는 개체입니다.|  
|[Get](reference/currentscheduler-class.md#get)|검색에 대 한 포인터는 `Scheduler` 현재 컨텍스트와 연결 된 개체입니다. 이 메서드는 참조 수가 증가 하지 않습니다는 `Scheduler` 개체입니다.|  
|[Detach](reference/currentscheduler-class.md#detach)|현재 컨텍스트에서 현재 스케줄러를 분리 하 고 현재 스케줄러로 이전 하나를 설정 합니다.|  
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|런타임에서 현재 스케줄러에서 소멸 될 때 설정 하는 이벤트를 등록 합니다.|  
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|만듭니다는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 현재 스케줄러에는 개체입니다.|  
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|현재 스케줄러의 일정 큐에 간단한 작업을 추가합니다.|  
|[정책 가져오기](reference/currentscheduler-class.md#getpolicy)|연결 된 현재 스케줄러 정책의 복사본을 검색 합니다.|  
  
 다음 표에서 여 정의 된 중요 한 메서드는 `Scheduler` 클래스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[만들기](reference/scheduler-class.md#create)|만듭니다는 `Scheduler` 지정 된 정책을 사용 하는 개체입니다.|  
|[Attach](reference/scheduler-class.md#attach)|연결 된 `Scheduler` 개체를 현재 컨텍스트와 함께 합니다.|  
|[참조](reference/scheduler-class.md#reference)|참조 카운터가 증가 하는 `Scheduler` 개체입니다.|  
|[릴리스](reference/scheduler-class.md#release)|감소의 참조 카운터는 `Scheduler` 개체입니다.|  
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|런타임을 설정 하는 이벤트를 등록 하는 `Scheduler` 개체를 제거 합니다.|  
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|만듭니다는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체는 `Scheduler` 개체입니다.|  
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|간단한 작업을 예약 하는 `Scheduler` 개체입니다.|  
|[정책 가져오기](reference/scheduler-class.md#getpolicy)|연결 된 정책의 복사본을 검색 된 `Scheduler` 개체입니다.|  
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|기본 스케줄러를 만들 때 사용 하 여 런타임에 대 한 정책을 설정 합니다.|  
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|기본 정책을 호출 하기 전에 활성 상태 였던 책갈피로 복원 `SetDefaultSchedulerPolicy`합니다. 를이 호출 후 기본 스케줄러를 만드는 경우 런타임 기본 정책 설정과 사용 하 여 스케줄러를 만듭니다.|  

  
 [[맨 위로 이동](#top)]  
  
##  <a name="example"></a> 예제  
 만들고 스케줄러 인스턴스를 관리 하는 방법의 기본 예제를 참조 하십시오. [하는 방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)   
 [일정 그룹](../../parallel/concrt/schedule-groups.md)

