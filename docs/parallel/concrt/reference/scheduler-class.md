---
title: "Scheduler 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::Scheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Scheduler 클래스"
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Scheduler 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임 스케줄러에 대한 추상화를 나타냅니다.  
  
## 구문  
  
```  
class Scheduler;  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[Scheduler::Scheduler 생성자](../Topic/Scheduler::Scheduler%20Constructor.md)|`Scheduler` 클래스의 개체는 팩터리 메서드를 사용하거나 암시적으로만 만들 수 있습니다.|  
|[Scheduler::~Scheduler 소멸자](../Topic/Scheduler::~Scheduler%20Destructor.md)|`Scheduler` 클래스의 개체는 모든 외부 참조가 더 이상 존재하지 않을 때 명시적으로 소멸됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[Scheduler::Attach 메서드](../Topic/Scheduler::Attach%20Method.md)|스케줄러를 호출 컨텍스트에 첨부합니다.  이 메서드가 반환된 후 호출 컨텍스트는 스케줄러에 의해 관리되며 스케줄러는 현재 스케줄러가 됩니다.|  
|[Scheduler::Create 메서드](../Topic/Scheduler::Create%20Method.md)|`_Policy` 매개 변수에서 동작을 설명하는 새 스케줄러를 만들고 스케줄러에 초기 참조를 배치하고 해당 포인터를 반환합니다.|  
|[Scheduler::CreateScheduleGroup 메서드](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|오버로드됨.  스케줄러 내에 새 일정 그룹을 만듭니다.   `_Placement`  매개 변수를 사용하는 버전은 매개 변수에 의해 지정 된 위치에서 실행하는 새 일정 그룹 내에서 작업이 발생 하게 합니다.|  
|[Scheduler::GetNumberOfVirtualProcessors 메서드](../Topic/Scheduler::GetNumberOfVirtualProcessors%20Method.md)|스케줄러에 대한 가상 프로세서의 현재 수를 반환합니다.|  
|[Scheduler::GetPolicy 메서드](../Topic/Scheduler::GetPolicy%20Method.md)|스케줄러에서 만든 정책의 복사본을 반환합니다.|  
|[Scheduler::Id 메서드](../Topic/Scheduler::Id%20Method.md)|스케줄러에 대한 고유 식별자를 반환합니다.|  
|[Scheduler::IsAvailableLocation 메서드](../Topic/Scheduler::IsAvailableLocation%20Method.md)|스케줄러에서 지정된 위치 인지 확인합니다.|  
|[Scheduler::Reference 메서드](../Topic/Scheduler::Reference%20Method.md)|스케줄러 참조 횟수를 증가시킵니다.|  
|[Scheduler::RegisterShutdownEvent 메서드](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|스케줄러가 종료되고 스스로 소멸될 때 Windows 이벤트 핸들이 `_Event` 매개 변수에 전달됩니다.  이벤트 신호가 있을 때 스케줄러에 예약된 모든 작업이 완료됩니다.  여러 종료 이벤트는 이 메서드를 통해 등록할 수 있습니다.|  
|[Scheduler::Release 메서드](../Topic/Scheduler::Release%20Method.md)|스케줄러 참조 횟수를 감소시킵니다.|  
|[Scheduler::ResetDefaultSchedulerPolicy 메서드](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|기본 스케줄러 정책을 런타임의 기본값으로 다시 설정합니다.  다음에 기본 스케줄러를 만들면 런타임 기본 정책 설정을 사용합니다.|  
|[Scheduler::ScheduleTask 메서드](../Topic/Scheduler::ScheduleTask%20Method.md)|오버로드됨.  스케줄러 내에 간단한 작업을 예약합니다.  간단한 작업은 런타임에 결정되는 일정 그룹에 배치됩니다.   `_Placement`  매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행 되도록 합니다.|  
|[Scheduler::SetDefaultSchedulerPolicy 메서드](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|사용자 정의 정책을 사용하여 기본 스케줄러를 만들 수 있습니다.  이 메서드는 기본 스케줄러가 프로세스 내에 없을 때만 호출할 수 있습니다.  기본 정책이 설정된 후에는 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md) 메서드에 대한 다음 유효한 호출이 있을 때까지 효력을 유지합니다.|  
  
## 설명  
 동시성 런타임 스케줄러는 스레드 같은 운영 체제의 실행 컨텍스트에 매핑하는 실행 컨텍스트를 사용하여 응용 프로그램이 큐에 추가한 작업을 실행합니다.  언제든지 스케줄러의 동시성 수준은 리소스 관리자가 자신에게 부여한 가상 프로세서 수와 같습니다.  가상 프로세서는 리소스 처리를 위한 추상화이며 내부 시스템에서 하드웨어 스레드에 매핑됩니다.  단일 스케줄러 컨텍스트만 주어진 시간에 가상 프로세서에서 실행할 수 있습니다.  
  
 동시성 런타임은 병렬 작업을 실행하기 위해 프로세스당 기본 스케줄러를 만듭니다.  또한 자체 스케줄러가 인스턴스를 만들고 이 클래스를 사용하여 조작할 수 있습니다.  
  
## 상속 계층  
 `Scheduler`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler Class](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)