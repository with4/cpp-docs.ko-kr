---
title: "방법: 실행 순서에 영향을 주는 일정 그룹 사용 | Microsoft Docs"
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
  - "일정 그룹, 사용[동시성 런타임]"
  - "일정 그룹 사용[동시성 런타임]"
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 실행 순서에 영향을 주는 일정 그룹 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임에서 작업의 예약 순서는 명확하지 않습니다.  그러나 일정 정책을 사용하면 작업이 실행되는 순서에 영향을 줄 수 있습니다.  이 항목에서는 일정 그룹을 [concurrency::SchedulingProtocol](../Topic/PolicyElementKey%20Enumeration.md) 스케줄러 정책과 함께 사용하여 작업의 실행 순서에 영향을 주는 방법을 보여 줍니다.  
  
 이 예제에서는 각각 다른 일정 정책을 사용하여 작업 집합을 두 번 실행합니다.  이때 두 정책 모두 최대 처리 리소스의 수를 2개로 제한합니다.  첫 번째 실행에서는 `EnhanceScheduleGroupLocality` 정책\(기본값\)을 사용하고 두 번째 실행에서는 `EnhanceForwardProgress` 정책을 사용합니다.  `EnhanceScheduleGroupLocality` 정책을 사용하는 경우 스케줄러는 각 작업이 끝나거나 양보할 때까지 한 일정 그룹의 모든 작업을 실행합니다.  반면에 `EnhanceForwardProgress` 정책을 사용하는 경우 스케줄러는 한 작업이 끝나거나 양보하는 즉시 라운드 로빈 방식에 따라 다음 일정 그룹으로 이동합니다.  
  
 각 일정 그룹에 관련 작업이 포함된 경우에는 작업 간에 캐시 집약성이 유지되므로 일반적으로 `EnhanceScheduleGroupLocality` 정책을 사용하면 성능이 향상됩니다.  `EnhanceForwardProgress` 정책을 사용하면 작업을 순서에 따라 앞으로 진행할 수 있으므로 일정 그룹 간 예약이 공평해야 할 경우에 유용합니다.  
  
## 예제  
 이 예제에서는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)에서 파생되는 `work_yield_agent` 클래스를 정의합니다.  `work_yield_agent` 클래스는 한 작업 단위를 수행하고 현재 컨텍스트를 양보한 다음, 다른 작업 단위를 수행합니다.  에이전트는 [concurrency::wait](../Topic/wait%20Function.md) 함수를 사용하여 다른 컨텍스트를 실행할 수 있도록 현재 컨텍스트를 협조적으로 양보합니다.  
  
 이 예제에서는 네 개의 `work_yield_agent` 개체를 만듭니다.  스케줄러 정책을 설정하여 에이전트 실행 순서에 영향을 주는 방법을 나타내기 위해 이 예제에서는 먼저 두 에이전트를 한 일정 그룹과 연결하고 다른 두 에이전트를 다른 일정 그룹과 연결합니다.  예제에서는 [concurrency::CurrentScheduler::CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) 메서드를 사용하여 [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체를 만듭니다.  또한 매번 다른 일정 정책을 사용하여 네 개의 에이전트 모두 두 번 실행합니다.  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/CPP/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **EnhanceScheduleGroupLocality를 사용하여...**  
**그룹 0, 0 작업: 먼저 반복...**  
**그룹 0, 1 작업: 먼저 반복...**  
**그룹 0, 0 작업: 대기 중...**  
**그룹 1, 0 작업: 먼저 반복...**  
**그룹 0, 1 작업: 대기 중...**  
**1 그룹, 작업 1: 먼저 반복...**  
**작업 0, 1 그룹: 대기 중...**  
**그룹 0, 0 작업: 두 번째 루프...**  
**작업 1, 1 그룹: 대기 중...**  
**그룹 0, 1 작업: 두 번째 루프...**  
**그룹 0, 0 작업: 완료...**  
**그룹 1, 0 작업: 두 번째 루프...**  
**그룹 0, 1 작업: 완료...**  
**그룹 1, 1 작업: 두 번째 루프...**  
**작업 0, 1 그룹: 완료...**  
**작업 1, 1 그룹: 완료...**  
**EnhanceForwardProgress를 사용하여...**  
**그룹 0, 0 작업: 먼저 반복...**  
**그룹 1, 0 작업: 먼저 반복...**  
**그룹 0, 0 작업: 대기 중...**  
**그룹 0, 1 작업: 먼저 반복...**  
**작업 0, 1 그룹: 대기 중...**  
**1 그룹, 작업 1: 먼저 반복...**  
**그룹 0, 1 작업: 대기 중...**  
**그룹 0, 0 작업: 두 번째 루프...**  
**작업 1, 1 그룹: 대기 중...**  
**그룹 1, 0 작업: 두 번째 루프...**  
**그룹 0, 0 작업: 완료...**  
**그룹 0, 1 작업: 두 번째 루프...**  
**작업 0, 1 그룹: 완료...**  
**그룹 1, 1 작업: 두 번째 루프...**  
**그룹 0, 1 작업: 완료...**  
**작업 1, 1 그룹: 완료...** 두 정책 모두 결과 이벤트 시퀀스가 같습니다.  그러나 `EnhanceScheduleGroupLocality`를 사용하는 정책은 두 번째 그룹에 포함된 에이전트를 시작하기 전에 첫 번째 일정 그룹에 포함된 두 에이전트를 모두 시작합니다.  반면에 `EnhanceForwardProgress`를 사용하는 정책은 첫 번째 그룹의 한 에이전트를 시작한 다음, 두 번째 그룹의 첫 번째 에이전트를 시작합니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `scheduling-protocol.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc scheduling\-protocol.cpp**  
  
## 참고 항목  
 [일정 그룹](../../parallel/concrt/schedule-groups.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)