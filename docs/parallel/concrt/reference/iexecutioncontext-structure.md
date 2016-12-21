---
title: "IExecutionContext 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::IExecutionContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionContext 구조체"
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IExecutionContext 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

주어진 가상 프로세서에서 실행할 수 있는 실행 컨텍스트와 공동으로 컨텍스트를 전환할 인터페이스입니다.  
  
## 구문  
  
```  
struct IExecutionContext;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IExecutionContext::Dispatch 메서드](../Topic/IExecutionContext::Dispatch%20Method.md)|스레드 프록시가 특정 실행 컨텍스트 실행을 시작할 때 호출되는 메서드입니다.  이는 스케줄러에 대한 주 작업자 루틴이 되어야 합니다.|  
|[IExecutionContext::GetId 메서드](../Topic/IExecutionContext::GetId%20Method.md)|실행 컨텍스트의 고유 식별자를 반환합니다.|  
|[IExecutionContext::GetProxy 메서드](../Topic/IExecutionContext::GetProxy%20Method.md)|이 컨텍스트를 실행 중인 스레드가 프록시에 대한 인터페이스를 반환합니다.|  
|[IExecutionContext::GetScheduler 메서드](../Topic/IExecutionContext::GetScheduler%20Method.md)|이 실행 컨텍스트가 속해 있는 스케줄러에 대한 인터페이스를 반환합니다.|  
|[IExecutionContext::SetProxy 메서드](../Topic/IExecutionContext::SetProxy%20Method.md)|스레드 프록시를 이 실행 컨텍스트에 연결합니다.  관련된 스레드 프록시가 컨텍스트의 `Dispatch` 메서드를 실행하기 전에 이 메서드를 오른쪽으로 호출합니다.|  
  
## 설명  
 동시성 런타임의 리소스 관리자와 인터페이스하는 사용자 지정 스케줄러를 구현하는 경우 `IExecutionContext` 인터페이스를 구현해야 합니다.  리소스 관리자가 만든 스레드는 `IExecutionContext::Dispatch` 메서드를 실행하여 스케줄러 대신 작업을 수행합니다.  
  
## 상속 계층  
 `IExecutionContext`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler 구조체](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy 구조체](../../../parallel/concrt/reference/ithreadproxy-structure.md)