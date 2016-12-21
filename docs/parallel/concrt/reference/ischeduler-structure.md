---
title: "IScheduler 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::IScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IScheduler 구조체"
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IScheduler 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

작업 스케줄러의 추상화에 대한 인터페이스입니다.  동시성 런타임 리소스 관리자는 이 인터페이스를 사용하여 작업 스케줄러와 통신합니다.  
  
## 구문  
  
```  
struct IScheduler;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IScheduler::AddVirtualProcessors 메서드](../Topic/IScheduler::AddVirtualProcessors%20Method.md)|스케줄러에 사용하도록 가상 프로세서 루트의 집합을 제공합니다.  `IVirtualProcessorRoot` 인터페이스는 스케줄러를 대신하여 작업을 수행할 수 있는 단일 스레드를 실행할 권한을 나타냅니다.|  
|[IScheduler::GetId 메서드](../Topic/IScheduler::GetId%20Method.md)|스케줄러에 대한 고유 식별자를 반환합니다.|  
|[IScheduler::GetPolicy 메서드](../Topic/IScheduler::GetPolicy%20Method.md)|스케줄러 정책 복사본을 반환합니다.  스케줄러 정책에 대한 자세한 내용은 [SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)를 참조하십시오.|  
|[IScheduler::NotifyResourcesExternallyBusy 메서드](../Topic/IScheduler::NotifyResourcesExternallyBusy%20Method.md)|배열 `ppVirtualProcessorRoots`에 있는 가상 프로세서 루트의 집합으로 표현되는 하드웨어 스레드가 다른 스케줄러에 의해 현재 사용되고 있음을 이 스케줄러에 알립니다.|  
|[IScheduler::NotifyResourcesExternallyIdle 메서드](../Topic/IScheduler::NotifyResourcesExternallyIdle%20Method.md)|배열 `ppVirtualProcessorRoots`에 있는 가상 프로세서 루트의 집합으로 표현되는 하드웨어 스레드가 다른 스케줄러에 의해 사용되고 있지 않음을 이 스케줄러에 알립니다.|  
|[IScheduler::RemoveVirtualProcessors 메서드](../Topic/IScheduler::RemoveVirtualProcessors%20Method.md)|이전에 이 스케줄러에 할당된 가상 프로세서 루트의 제거를 시작합니다.|  
|[IScheduler::Statistics 메서드](../Topic/IScheduler::Statistics%20Method.md)|작업 도착 및 완료 비율과 관련한 정보를 제공하고 스케줄러에 대한 큐 길이를 변경합니다.|  
  
## 설명  
 리소스 관리자와 통신하는 사용자 지정 스케줄러를 구현하는 경우 `IScheduler` 인터페이스의 구현을 제공해야 합니다.  이 인터페이스는 스케줄러와 리소스 관리자 사이의 양방향 통신 채널 중 한 쪽 끝입니다.  다른 쪽 끝은 리소스 관리자에 의해 구현되는 `IResourceManager` 및 `ISchedulerProxy` 인터페이스로 표현됩니다.  
  
## 상속 계층  
 `IScheduler`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy 클래스](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [IExecutionContext 구조체](../../../parallel/concrt/reference/iexecutioncontext-structure.md)   
 [IThreadProxy 구조체](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 구조체](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager 구조체](../../../parallel/concrt/reference/iresourcemanager-structure.md)