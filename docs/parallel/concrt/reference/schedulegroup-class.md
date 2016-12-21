---
title: "ScheduleGroup 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::ScheduleGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ScheduleGroup 클래스"
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ScheduleGroup 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

일정 그룹에 대한 추상화를 나타냅니다.  일정 그룹은 다른 그룹으로 이동하기 전에 같은 그룹에서 다른 작업을 실행하거나 공간적으로 같은 NUMA 노드 또는 물리적 소켓의 같은 그룹 내에서 여러 항목을 실행하여 일시적으로 함께 예약하는 이점을 갖는 관련 작업을 구성합니다.  
  
## 구문  
  
```  
class ScheduleGroup;  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[ScheduleGroup::~ScheduleGroup 소멸자](../Topic/ScheduleGroup::~ScheduleGroup%20Destructor.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ScheduleGroup::Id 메서드](../Topic/ScheduleGroup::Id%20Method.md)|그룹이 속해 있는 스케줄러 내에서 고유한 스케줄러 그룹의 식별자를 반환합니다.|  
|[ScheduleGroup::Reference 메서드](../Topic/ScheduleGroup::Reference%20Method.md)|일정 그룹의 참조 횟수를 증가시킵니다.|  
|[ScheduleGroup::Release 메서드](../Topic/ScheduleGroup::Release%20Method.md)|일정 그룹의 참조 횟수를 감소시킵니다.|  
|[ScheduleGroup::ScheduleTask 메서드](../Topic/ScheduleGroup::ScheduleTask%20Method.md)|일정 그룹 내에 간단한 작업을 예약합니다.|  
  
## 상속 계층  
 `ScheduleGroup`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [CurrentScheduler 클래스](../../../parallel/concrt/reference/currentscheduler-class.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)