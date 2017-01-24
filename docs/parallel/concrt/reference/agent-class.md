---
title: "에이전트 클래스 | Microsoft Docs"
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
  - "agents/concurrency::agent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "에이전트 클래스"
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 에이전트 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

모든 독립 에이전트에 대한 기본 클래스로 사용할 클래스입니다.  이것은 다른 에이전트의 상태를 숨기고 메시지 전달을 통해 상호 작용하는데 사용됩니다.  
  
## 구문  
  
```  
class agent;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[agent::agent 생성자](../Topic/agent::agent%20Constructor.md)|오버로드됨.  에이전트를 생성합니다.|  
|[agent::~agent 소멸자](../Topic/agent::~agent%20Destructor.md)|에이전트가 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[agent::cancel 메서드](../Topic/agent::cancel%20Method.md)|에이전트가 `agent_created` 또는 `agent_runnable` 상태에서 `agent_canceled` 상태로 이동합니다.|  
|[agent::start 메서드](../Topic/agent::start%20Method.md)|에이전트가 `agent_created` 상태에서 `agent_runnable` 상태로 이동하고 실행을 예약합니다.|  
|[agent::status 메서드](../Topic/agent::status%20Method.md)|에이전트에서 상태 정보의 동기 소스.|  
|[agent::status\_port 메서드](../Topic/agent::status_port%20Method.md)|에이전트의 상태 정보에 대한 비동기 소스입니다.|  
|[agent::wait 메서드](../Topic/agent::wait%20Method.md)|에이전트가 해당 작업을 완료하기를 기다립니다.|  
|[agent::wait\_for\_all 메서드](../Topic/agent::wait_for_all%20Method.md)|지정한 모든 에이전트 해당 작업을 완료하기를 기다립니다.|  
|[agent::wait\_for\_one 메서드](../Topic/agent::wait_for_one%20Method.md)|지정한 에이전트 중 하나가 해당 작업을 완료하기를 기다립니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[agent::done 메서드](../Topic/agent::done%20Method.md)|에이전트가 `agent_done` 상태로 이동하여 에이전트가 완료되었음을 나타냅니다.|  
|[agent::run 메서드](../Topic/agent::run%20Method.md)|에이전트의 주 작업을 나타냅니다.  `run`는 파생된 클래스에서 재정의하고 시작된 후에 에이전트가 무엇을 수행해야 하는지 지정해야 합니다.|  
  
## 설명  
 자세한 내용은 [비동기 에이전트](../../../parallel/concrt/asynchronous-agents.md)을 참조하십시오.  
  
## 상속 계층  
 `agent`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)