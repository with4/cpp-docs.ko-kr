---
title: "CurrentScheduler 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::CurrentScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CurrentScheduler 클래스"
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CurrentScheduler 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

호출 컨텍스트와 연결된 현재 스케줄러에 대한 추상화를 나타냅니다.  
  
## 구문  
  
```  
class CurrentScheduler;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CurrentScheduler::Create 메서드](../Topic/CurrentScheduler::Create%20Method.md)|`_Policy` 매개 변수로 동작이 설명하는 새 스케줄러를 만들고 호출 컨텍스트에 추가합니다.  새로 만든 스케줄러는 호출 컨텍스트에 대한 현재 스케줄러가 됩니다.|  
|[CurrentScheduler::CreateScheduleGroup 메서드](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|오버로드됨.  호출 컨텍스트와 관련된 스케줄러 내에 새 일정 그룹을 만듭니다.   `_Placement`  매개 변수를 사용하는 버전은 매개 변수에 의해 지정 된 위치에서 실행하는 새 일정 그룹 내에서 작업이 발생 하게 합니다.|  
|[CurrentScheduler::Detach 메서드](../Topic/CurrentScheduler::Detach%20Method.md)|호출 컨텍스트에서 현재 스케줄러를 분리하고 존재하는 경우 이전에 연결된 스케줄러를 현재 스케줄러로 복원합니다.  이 메서드가 반환한 후 호출 컨텍스트는 `CurrentScheduler::Create` 또는 `Scheduler::Attach` 메서드를 사용해 컨텍스트에 이전에 연결된 스케줄러가 관리합니다.|  
|[CurrentScheduler::Get 메서드](../Topic/CurrentScheduler::Get%20Method.md)|호출 컨텍스트와 관련된 스케즐러에 대한 포인터를 반환하며, 현재 스케줄러로 참조됩니다.|  
|[CurrentScheduler::GetNumberOfVirtualProcessors 메서드](../Topic/CurrentScheduler::GetNumberOfVirtualProcessors%20Method.md)|호출 컨텍스트와 연결된 스케줄러에 대한 가상 프로세서의 현재 수를 반환합니다.|  
|[CurrentScheduler::GetPolicy 메서드](../Topic/CurrentScheduler::GetPolicy%20Method.md)|현재 스케줄러에서 만든 정책의 복사본을 반환합니다.|  
|[CurrentScheduler::Id 메서드](../Topic/CurrentScheduler::Id%20Method.md)|현재 스케줄러에 대한 고유 식별자를 반환합니다.|  
|[CurrentScheduler::IsAvailableLocation 메서드](../Topic/CurrentScheduler::IsAvailableLocation%20Method.md)|현재 스케줄러에서 지정된 위치 인지 확인합니다.|  
|[CurrentScheduler::RegisterShutdownEvent 메서드](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|현재 컨텍스트와 관련된 스케줄러가 종료되고 스스로 소멸될 때 신호를 보낼 `_ShutdownEvent` 매개 변수에 Windows 이벤트 핸들이 전달되도록 합니다.  이벤트 신호가 있을 때 스케줄러에 예약된 모든 작업이 완료됩니다.  여러 종료 이벤트는 이 메서드를 통해 등록할 수 있습니다.|  
|[CurrentScheduler::ScheduleTask 메서드](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|오버로드됨.  호출 컨텍스트와 관련된 스케줄러 내에 간단한 작업을 예약합니다.  간단한 작업은 런타임에 결정되는 일정 그룹에 배치됩니다.   `_Placement`  매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행 되도록 합니다.|  
  
## 설명  
 호출 컨텍스트와 연결된 스케줄러가 없는 경우\([스케줄러](../../../parallel/concrt/reference/scheduler-class.md) 참조\) `CurrentScheduler` 클래스 내의 많은 메서드는 프로세스의 기본 스케줄러에 연결됩니다.  또한 프로세스의 기본 스케줄러가 이런 호출 동안 만들어진다는 것을 의미할 수도 있습니다.  
  
## 상속 계층  
 `CurrentScheduler`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)