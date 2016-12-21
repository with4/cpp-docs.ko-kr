---
title: "Context 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::Context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Context 클래스"
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
caps.latest.revision: 20
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Context 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

실행 컨텍스트에 대한 추상화를 나타냅니다.  
  
## 구문  
  
```  
class Context;  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[Context::~Context 소멸자](../Topic/Context::~Context%20Destructor.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[Context::Block 메서드](../Topic/Context::Block%20Method.md)|현재 컨텍스트를 차단합니다.|  
|[Context::CurrentContext 메서드](../Topic/Context::CurrentContext%20Method.md)|현재 컨텍스트에 대한 포인터를 반환합니다.|  
|[Context::GetId 메서드](../Topic/Context::GetId%20Method.md)|컨텍스트가 속해 있는 스케줄러 내에서 고유한 컨텍스트의 식별자를 반환합니다.|  
|[Context::GetScheduleGroupId 메서드](../Topic/Context::GetScheduleGroupId%20Method.md)|컨텍스트가 현재 작동 중인 일정 그룹에 대한 식별자를 반환합니다.|  
|[Context::GetVirtualProcessorId 메서드](../Topic/Context::GetVirtualProcessorId%20Method.md)|컨텍스트가 현재 실행 중인 가상 프로세서에 대한 식별자를 반환합니다.|  
|[Context::Id 메서드](../Topic/Context::Id%20Method.md)|현재 컨텍스트가 속해 있는 스케줄러 내에서 고유한 현재 컨텍스트의 식별자를 반환합니다.|  
|[Context::IsCurrentTaskCollectionCanceling 메서드](../Topic/Context::IsCurrentTaskCollectionCanceling%20Method.md)|현재 컨텍스트에서 인라인 실행 중인 작업 컬렉션이 현재 취소 중인지\(또는 곧 취소\) 여부를 반환합니다.|  
|[Context::IsSynchronouslyBlocked 메서드](../Topic/Context::IsSynchronouslyBlocked%20Method.md)|컨텍스트가 동기적으로 차단되는지 여부를 결정합니다.  컨텍스트는 차단을 일으키는 작업을 명시적으로 수행한 경우 동기적으로 차단된 것으로 간주됩니다.|  
|[Context::Oversubscribe 메서드](../Topic/Context::Oversubscribe%20Method.md)|추가 가상 프로세서가 해당 스케줄러에서 가상 프로세서 중 하나에서 실행되는 컨텍스트에서 실행될 때 코드 블록의 기간 동안 스케줄러에 삽입합니다.|  
|[Context::ScheduleGroupId 메서드](../Topic/Context::ScheduleGroupId%20Method.md)|현재 컨텍스트가 작동 중인 일정 그룹에 대한 식별자를 반환합니다.|  
|[Context::Unblock 메서드](../Topic/Context::Unblock%20Method.md)|컨텍스트를 차단 해제하고 실행할 수 없게 만듭니다.|  
|[Context::VirtualProcessorId 메서드](../Topic/Context::VirtualProcessorId%20Method.md)|현재 컨텍스트가 실행 중인 가상 프로세서에 대한 식별자를 반환합니다.|  
|[Context::Yield 메서드](../Topic/Context::Yield%20Method.md)|다른 컨텍스트가 실행할 수 있도록 실행을 양보합니다.  양도할 수 있는 다른 컨텍스트가 없는 경우 스케줄러는 다른 운영 체제 스레드를 양도할 수 있습니다.|  
  
## 설명  
 동시성 런타임 스케줄러\([스케줄러](../../../parallel/concrt/reference/scheduler-class.md) 참조\)는 실행 컨텍스트를 사용하여 응용 프로그램이 큐에 추가한 작업을 실행합니다.  Win32 스레드는 Windows 운영체제에서의 실행 컨텍스트의 예입니다.  
  
 언제든지 스케줄러의 동시성 수준은 리소스 관리자가 자신에게 부여한 가상 프로세서 수와 같습니다.  가상 프로세서는 리소스 처리를 위한 추상화이며 내부 시스템에서 하드웨어 스레드에 매핑됩니다.  단일 스케줄러 컨텍스트만 주어진 시간에 가상 프로세서에서 실행할 수 있습니다.  
  
 스케줄러는 본질적으로 공동 작업이며 실행 컨텍스트는 대기 상태에 들어가기를 원할 경우 언제든지 가상 프로세서를 다른 컨텍스트에 양도할 수 있습니다.  대기가 충족될 때 스케줄러에서 사용 가능한 가상 프로세서가 실행을 시작할 때까지 다시 시작할 수 없습니다.  
  
## 상속 계층  
 `Context`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)