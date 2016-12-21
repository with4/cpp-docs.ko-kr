---
title: "비동기 에이전트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "에이전트[동시성 런타임]"
  - "asynchronous 에이전트"
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
caps.latest.revision: 15
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 비동기 에이전트
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*비동기 에이전트* 또는 *에이전트*는 규모가 큰 컴퓨팅 작업을 해결하기 위해 다른 에이전트와 함께 비동기적으로 동작하는 응용 프로그램 구성 요소입니다.  에이전트를 수명 주기가 설정된 작업으로 간주할 수 있습니다.  예를 들어 한 에이전트는 키보드, 디스크의 파일 또는 네트워크 연결과 같은 입\/출력 장치에서 데이터를 읽고 다른 에이전트는 해당 데이터를 사용할 수 있게 되면 데이터로 작업을 수행합니다.  첫 번째 에이전트는 메시지 전달을 사용하여 두 번째 에이전트에 추가 데이터를 사용할 수 있음을 알립니다.  동시성 런타임 작업 스케줄러는 효율성이 낮은 선점이 없어도 에이전트가 협조적으로 차단 및 양보할 수 있도록 하는 효율적인 메커니즘을 제공합니다.  
  
 에이전트 라이브러리는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md) 클래스를 정의하여 비동기 에이전트를 나타냅니다.  `agent`는 가상 메서드 [concurrency::agent::run](../Topic/agent::run%20Method.md)을 선언하는 추상 클래스입니다.  `run` 메서드는 에이전트에서 수행하는 작업을 실행합니다.  `run`은 추상 메서드이므로 `agent`에서 파생되는 모든 클래스에 이 메서드를 구현해야 합니다.  
  
## 에이전트 수명 주기  
 에이전트에는 수명 주기가 설정되어 있습니다.  [concurrency::agent\_status](../Topic/agent_status%20Enumeration.md) 열거형은 에이전트의 다양한 상태를 정의합니다.  다음 그림은 에이전트가 상태별로 진행되는 방식을 보여 주는 상태 다이어그램입니다.  이 그림에서 실선은 응용 프로그램에서 호출하는 메서드를 나타내고 점선은 런타임에서 호출되는 메서드를 나타냅니다.  
  
 ![에이전트 상태 다이어그램](../../parallel/concrt/media/agentstate.png "AgentState")  
  
 다음 표에서는 `agent_status` 열거형의 각 상태에 대해 설명합니다.  
  
|에이전트 상태|설명|  
|-------------|--------|  
|`agent_created`|에이전트가 실행되도록 예약되지 않았습니다.|  
|`agent_runnable`|런타임에서 에이전트를 실행하도록 예약하고 있습니다.|  
|`agent_started`|에이전트가 시작되어 실행되고 있습니다.|  
|`agent_done`|에이전트가 끝났습니다.|  
|`agent_canceled`|에이전트가 `started` 상태를 시작하기 전에 취소되었습니다.|  
  
 `agent_created`는 에이전트의 초기 상태이고, `agent_runnable` 및 `agent_started`는 활성 상태이며, `agent_done` 및 `agent_canceled`는 종료 상태입니다.  
  
 `agent` 개체의 현재 상태를 검색하려면 [concurrency::agent::status](../Topic/agent::status%20Method.md) 메서드를 사용합니다.  `status` 메서드는 동시성이 보장되지만 `status` 메서드가 반환될 때 에이전트의 상태를 변경할 수 있습니다.  예를 들어 `status` 메서드를 호출할 때는 에이전트가 `agent_started` 상태일 수 있지만 `status` 메서드가 반환된 직후에는 `agent_done` 상태로 이동했습니다.  
  
## 메서드 및 기능  
 다음 표에서는 `agent` 클래스에 속하는 중요한 메서드 중 일부를 보여 줍니다.  모든 `agent` 클래스 메서드에 대한 자세한 내용은 [에이전트 클래스](../../parallel/concrt/reference/agent-class.md)를 참조하십시오.  
  
|메서드|설명|  
|---------|--------|  
|[start](../Topic/agent::start%20Method.md)|`agent` 개체의 실행을 예약하고 `agent_runnable` 상태로 설정합니다.|  
|[run](../Topic/agent::run%20Method.md)|`agent` 개체에서 수행할 작업을 실행합니다.|  
|[done](../Topic/agent::done%20Method.md)|에이전트를 `agent_done` 상태로 이동합니다.|  
|[cancel](../Topic/agent::cancel%20Method.md)|에이전트가 시작되지 않은 경우 이 메서드는 에이전트의 실행을 취소하고 `agent_canceled` 상태로 설정합니다.|  
|[status](../Topic/agent::status%20Method.md)|`agent` 개체의 현재 상태를 검색합니다.|  
|[wait](../Topic/agent::wait%20Method.md)|`agent` 개체가 `agent_done` 또는 `agent_canceled` 상태가 될 때까지 기다립니다.|  
|[wait\_for\_all](../Topic/agent::wait_for_all%20Method.md)|제공된 모든 `agent` 개체가 `agent_done` 또는 `agent_canceled` 상태가 될 때까지 기다립니다.|  
|[wait\_for\_one](../Topic/agent::wait_for_one%20Method.md)|제공된 모든 `agent` 개체 중 적어도 하나가 `agent_done` 또는 `agent_canceled` 상태가 될 때까지 기다립니다.|  
  
 에이전트 개체를 만든 후에는 [concurrency::agent::start](../Topic/agent::start%20Method.md) 메서드를 호출하여 해당 에이전트 개체의 실행을 예약합니다.  런타임에서는 에이전트가 예약된 후 `run` 메서드를 호출하고 `agent_runnable` 상태로 설정합니다.  
  
 런타임에서는 비동기 에이전트에서 throw되는 예외를 관리하지 않습니다.  예외 처리 및 에이전트에 대한 자세한 내용은 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)를 참조하십시오.  
  
## 예제  
 에이전트를 기반으로 한 기본 응용 프로그램을 만드는 방법을 보여 주는 예제를 보려면 [연습: 에이전트 기반 응용 프로그램 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)를 참조하십시오.  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)