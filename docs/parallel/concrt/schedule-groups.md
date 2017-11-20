---
title: "일정 그룹 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 234288be0313c8e50fde08a3cb898f498ebe4174
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="schedule-groups"></a>일정 그룹
이 문서에서는 동시성 런타임의 일정 그룹의 역할에 설명 합니다. A *일정 그룹* 선호도 설정 하거나, 관련된 태스크를 함께 그룹화 합니다. 모든 스케줄러에는 하나 이상의 일정 그룹에 있습니다. 작업 간에 높은 수준의 국부성이 필요한 경우, 예를 들어 동일한 프로세서 노드에서 관련 작업 그룹을 실행하면 이점이 있는 경우 일정 그룹을 사용합니다. 반대로, 응용 프로그램에 특정 품질 요구 사항, 예를 들어 일련의 작업에 할당 되는 처리 리소스의 크기를 제한 하려는 경우 스케줄러 인스턴스를 사용 합니다. 스케줄러 인스턴스에 대 한 자세한 내용은 참조 [스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)합니다.  
  
> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다. 작업 스케줄러를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 때문에로 시작 하는 것이 좋습니다는 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 하려는 경우 동시성 런타임으로 새입니다.  
  
 모든 `Scheduler` 개체에 모든 일정 노드에 대 한 기본 일정 그룹입니다. A *일정 노드* 기본 시스템 토폴로지에 매핑됩니다. 중 더 큰에 런타임은 모든 프로세서 패키지에 대해 하나의 일정 노드 또는 Non-uniform NUMA (Memory Architecture) 노드를 만듭니다. 일정 그룹에 작업을 명시적으로 연결 하지 않는 경우 스케줄러 작업을 추가 하려면 어떤 그룹을 선택 합니다.  
  
 `SchedulingProtocol` 스케줄러 정책을 스케줄러 각 일정 그룹의 작업이 실행 되는 순서에 영향을 줍니다. 때 `SchedulingProtocol` 로 설정 된 `EnhanceScheduleGroupLocality` (기본값) 인 작업 스케줄러에서 작업은 현재 작업이 완료 되거나 협조적으로 양보 하는 일정 그룹에서 다음 작업을 선택 합니다. 사용 가능한 다음 그룹으로 이동 하기 전에 작업 스케줄러 작업에 대 한 현재 일정 그룹을 검색 합니다. 반대로, `SchedulingProtocol` 로 설정 된 `EnhanceForwardProgress`, 스케줄러는 각 태스크를 완료 하거나 생성 한 후 다음 일정 그룹으로 이동 합니다. 이러한 정책은 비교 하는 예제를 참조 하십시오. [하는 방법: 실행의 영향 범위 순서를 사용 하 여 일정 그룹](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)합니다.  
  

 런타임에서 사용 하는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 클래스 일정 그룹을 나타냅니다. 만들려는 `ScheduleGroup` 개체를 호출 하는 [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) 또는 [concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup) 메서드. 런타임에서 참조 횟수 메커니즘의 수명을 제어를 사용 하 여 `ScheduleGroup` 개체에서 마찬가지로 `Scheduler` 개체입니다. 만들 때 한 `ScheduleGroup` 개체 런타임에서 참조 카운터를 1로 설정 합니다. [concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference) 메서드는 참조 카운터 1 씩 증가 시킵니다. [concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release) 메서드 감소 씩 참조 카운터입니다.  
  
 동시성 런타임에서 다양 한 형식을 일정 그룹과 함께 개체를 연결할 수 있습니다. 예를 들어는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 클래스와 메시지 블록 클래스와 같은 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency:: join](../../parallel/concrt/reference/join-class.md), 처리 및 동시성::[ 타이머](reference/timer-class.md)를 사용 하는 생성자의 오버 로드 된 버전이 제공는 `ScheduleGroup` 개체입니다. 런타임에서 사용 하는 `Scheduler` 과 관련 된 개체 `ScheduleGroup` 작업을 예약 하는 개체입니다.  
  
 사용할 수도 있습니다는 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask) 간단한 작업을 예약 하는 메서드. 간단한 작업에 대 한 자세한 내용은 참조 [간단한 작업](../../parallel/concrt/lightweight-tasks.md)합니다.  

  
## <a name="example"></a>예제  
 일정 작업 실행 순서를 제어 하는 그룹을 사용 하는 예제를 보려면 [하는 방법: 실행의 영향 범위 순서를 사용 하 여 일정 그룹](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)   
 [방법: 실행 순서에 영향을 주는 일정 그룹 사용](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

