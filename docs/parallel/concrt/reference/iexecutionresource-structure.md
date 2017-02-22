---
title: "IExecutionResource 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionResource 구조체"
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# IExecutionResource 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

하드웨어 스레드에 대한 추상화입니다.  
  
## 구문  
  
```  
struct IExecutionResource;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IExecutionResource::CurrentSubscriptionLevel 메서드](../Topic/IExecutionResource::CurrentSubscriptionLevel%20Method.md)|활성화된 가상 프로세서 루트 및 이 실행 리소스가 나타내는 기본 하드웨어 스레드와 현재 관련된 구독한 외부 스레드를 반환합니다.|  
|[IExecutionResource::GetExecutionResourceId 메서드](../Topic/IExecutionResource::GetExecutionResourceId%20Method.md)|이 실행 리소스가 나타내는 하드웨어 스레드에 대한 고유 식별자를 반환합니다.|  
|[IExecutionResource::GetNodeId 메서드](../Topic/IExecutionResource::GetNodeId%20Method.md)|이 실행 리소스가 속해 있는 프로세서 노드에 대한 고유 식별자를 반환합니다.|  
|[IExecutionResource::Remove 메서드](../Topic/IExecutionResource::Remove%20Method.md)|이 실행 리소스를 리소스 관리자에 반환합니다.|  
  
## 설명  
 실행 리소스는 독립 실행형이거나 가상 프로세서 루트에 연결될 수 있습니다.  응용 프로그램의 스레드가 스레드 구독을 만들면 독립 실행형 실행 리소스가 만들어집니다.  메서드 [ISchedulerProxy::SubscribeThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md) 및 [ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)는 스레드 구독을 만들고 구독을 나타내는 `IExecutionResource` 인터페이스를 반환합니다.  스레드 구독을 만드는 것은 스케줄러에 할당하는 가상 프로세서 루트 리소스 관리자와 함께 해당 스레드가 큐에서 제거한 작업을 스케줄러에 참가한다는 것을 리소스 관리자에게 알리는 방법입니다.  리소스 관리자는 가능하면 하드웨어 스레드가 초과 구독되는 것을 방지하기 위해 정보를 사용합니다.  
  
## 상속 계층  
 `IExecutionResource`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IVirtualProcessorRoot 구조체](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [ISchedulerProxy::SubscribeCurrentThread 메서드](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)   
 [ISchedulerProxy::RequestInitialVirtualProcessors 메서드](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)