---
title: "ISchedulerProxy 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ISchedulerProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISchedulerProxy 구조체"
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# ISchedulerProxy 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

스케줄러가 동시성 런타임 리소스 관리자와 통신하여 리소스 할당을 협상하는 인터페이스입니다.  
  
## 구문  
  
```  
struct ISchedulerProxy;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ISchedulerProxy::BindContext 메서드](../Topic/ISchedulerProxy::BindContext%20Method.md)|아직 연결되어 있지 않으면 실행 컨텍스트를 스레드 프록시에 연결합니다.|  
|[ISchedulerProxy::CreateOversubscriber 메서드](../Topic/ISchedulerProxy::CreateOversubscriber%20Method.md)|기존 실행 리소스에 연결된 하드웨어 스레드에 새 가상 프로세서 루트를 만듭니다.|  
|[ISchedulerProxy::RequestInitialVirtualProcessors 메서드](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)|가상 프로세서 루트의 초기 할당을 요청합니다.  모든 가상 프로세서 루트는 스케줄러에 대해 수행할 수 있는 한 스레드만 실행할 수 있는 기능을 나타냅니다.|  
|[ISchedulerProxy::Shutdown 메서드](../Topic/ISchedulerProxy::Shutdown%20Method.md)|스케줄러가 종료되고 있음을 리소스 관리자에 알립니다.  이로 인해 리소스 관리자는 스케줄러에 부여된 모든 리소스를 즉시 회수하게 됩니다.|  
|[ISchedulerProxy::SubscribeCurrentThread 메서드](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)|현재 스레드를 리소스 관리자를 사용하여 등록하고 이 스케줄러에 연결합니다.|  
|[ISchedulerProxy::UnbindContext 메서드](../Topic/ISchedulerProxy::UnbindContext%20Method.md)|`pContext` 매개 변수에서 지정한 실행 컨텍스트에서 스레드 프록시 연결을 해제하고 스레드 프록시 팩터리의 사용 가능한 풀로 반환합니다.  이 메서드는 [ISchedulerProxy::BindContext](../Topic/ISchedulerProxy::BindContext%20Method.md) 메서드를 통해 바인딩된 실행 컨텍스트에서만 호출할 수 있으며 [IThreadProxy::SwitchTo](../Topic/IThreadProxy::SwitchTo%20Method.md) 메서드 호출의 `pContext` 매개 변수를 통해 아직 시작되지 않았습니다.|  
  
## 설명  
 리소스 관리자는 [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md) 메서드를 사용하여 등록하는 모든 스케줄러에 `ISchedulerProxy` 인터페이스를 전달합니다.  
  
## 상속 계층  
 `ISchedulerProxy`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler 구조체](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy 구조체](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 구조체](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager 구조체](../../../parallel/concrt/reference/iresourcemanager-structure.md)