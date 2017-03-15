---
title: "일정 그룹 | Microsoft Docs"
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
  - "일정 그룹"
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 일정 그룹
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 동시성 런타임에서 일정 그룹의 역할을 설명 합니다. A *일정 그룹* 선호도 설정 하거나, 관련된 태스크를 함께 그룹화 합니다. 모든 스케줄러에는 하나 이상의 일정 그룹에 있습니다. 작업 간에 높은 수준의 국부성이 필요한 경우, 예를 들어 동일한 프로세서 노드에서 관련 작업 그룹을 실행하면 이점이 있는 경우 일정 그룹을 사용합니다. 반대로, 응용 프로그램에 특정 품질 요구 사항, 예를 들어 일련의 작업에 할당 되는 처리 리소스의 양을 제한 하려면 하는 경우에 스케줄러 인스턴스를 사용 합니다. 스케줄러 인스턴스에 대 한 자세한 내용은 참조 [스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)합니다.  
  
> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다. 작업 스케줄러를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 때문에 시작 하는 것이 좋습니다는 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 동시성 런타임으로 접하는 경우.  
  
 모든 `Scheduler` 개체에 모든 일정 노드에 기본 일정 그룹입니다. A *일정 노드* 내부 시스템 토폴로지에 매핑됩니다. 중 더 큰에 런타임에 모든 프로세서 패키지에 대해 하나의 일정 노드 또는 비균일 메모리 아키텍처 (NUMA) 노드를 만듭니다. 일정 그룹에 작업을 명시적으로 연결 하지 않는 경우 스케줄러 작업을 추가 하는 그룹을 선택 합니다.  
  
  `SchedulingProtocol` 스케줄러 정책을 스케줄러 각 일정 그룹에 작업을 실행 하는 순서에 영향을 줍니다. 때 `SchedulingProtocol` 로 설정 된 `EnhanceScheduleGroupLocality` (기본값) 인 작업 스케줄러에서 작업은 현재 작업이 완료 되거나 협조적으로 양보 하는 일정 그룹에서 다음 작업을 선택 합니다. 작업 스케줄러는 사용 가능한 다음 그룹으로 이동 하기 전에 작업에 대 한 현재 일정 그룹을 검색 합니다. 반대로, `SchedulingProtocol` 로 설정 된 `EnhanceForwardProgress`, 스케줄러는 각 작업을 완료 하거나 생성 한 후 다음 일정 그룹으로 이동 합니다. 이러한 정책을 비교 하는 예제를 보려면 [하는 방법: 실행의 영향 범위 순서를 사용 하 여 일정 그룹](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)합니다.  
  
 런타임에서 사용 하는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 일정 그룹을 나타내는 클래스입니다. 만들려는 `ScheduleGroup` 개체를 호출 하는 [concurrency::CurrentScheduler::CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) 또는 [concurrency::Scheduler::CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md) 메서드. 런타임에서 참조 카운팅 메커니즘의 수명을 제어를 사용 하 여 `ScheduleGroup` 개체와 마찬가지로 `Scheduler` 개체입니다. 만들 때 한 `ScheduleGroup` 개체, 런타임에서 참조 카운터를 1로 설정 합니다.  [concurrency::ScheduleGroup::Reference](../Topic/ScheduleGroup::Reference%20Method.md) 메서드는 참조 카운터를 1 씩입니다.  [concurrency::ScheduleGroup::Release](../Topic/ScheduleGroup::Release%20Method.md) 메서드 감소 하나는 참조 카운터입니다.  
  
 동시성 런타임에서 많은 종류를 사용 하는 일정 그룹 함께 개체를 연결할 수 있습니다. 예를 들어는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 클래스와 메시지 블록 클래스와 같은 [concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md), [concurrency:: join](../../parallel/concrt/reference/join-class.md), 처리 및 동시성::[타이머](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d5d4c847-5ad6-4c7f-b35b-d0b6f446d8b4/locales/en-US), 오버 로드 된 버전의 생성자를 제공는 `ScheduleGroup` 개체입니다. 런타임에서 사용 하는 `Scheduler` 이 연관 된 개체 `ScheduleGroup` 작업을 예약 하는 개체입니다.  
  
 사용할 수도 있습니다는 [concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md) 간단한 작업을 예약 하는 방법입니다. 간단한 작업에 대 한 자세한 내용은 참조 [간단한 작업](../../parallel/concrt/lightweight-tasks.md)합니다.  
  
## <a name="example"></a>예제  
 일정의 작업 실행 순서를 제어 하는 그룹을 사용 하는 예제를 보려면 [하는 방법: 실행의 영향 범위 순서를 사용 하 여 일정 그룹](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)   
 [방법: 실행 순서에 영향을 주는 일정 그룹 사용](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

