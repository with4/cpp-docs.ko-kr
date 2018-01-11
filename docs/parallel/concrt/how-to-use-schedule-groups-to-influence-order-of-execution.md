---
title: "방법: 실행 순서를 영향을 주는 일정 그룹 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcb37c1c14a9d09230bfa5d4fdce1da5eddfb4f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>방법: 실행 순서에 영향을 주는 일정 그룹 사용
동시성 런타임에서 작업 예약 된 순서는 결정적이 지 합니다. 그러나 작업이 실행 되는 순서 영향을 주는 일정 예약 정책을 사용할 수 있습니다. 이 항목에서는 일정 그룹와 함께 사용 하는 [concurrency::SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) 스케줄러 정책 작업이 실행 되는 순서에 영향을 줍니다.  

  
 이 예제에서는 각각 서로 다른 일정 예약 정책을 사용 하 여 일련의 작업을 두 번 실행합니다. 이 두 정책은 2 개로 처리 리소스의 최대 수를 제한 합니다. 첫 번째 실행의 `EnhanceScheduleGroupLocality` 정책, 기본값 및 사용 하 여를 실행 하는 두 번째는 `EnhanceForwardProgress` 정책입니다. 아래는 `EnhanceScheduleGroupLocality` 정책을 스케줄러 모든 작업 그룹의 실행 일정을 두 개 각 태스크를 완료 하거나 생성 될 때까지 합니다. 아래는 `EnhanceForwardProgress` 정책을 스케줄러 그룹으로 이동 다음 일정에 라운드 로빈 방식으로 한 작업이 완료 되거나 생성 후 합니다.  
  
 각 일정 그룹 관련된 작업을 포함 하는 경우는 `EnhanceScheduleGroupLocality` 정책 성능이 향상 작업 간에 캐시 집약성이 유지 때문에 일반적으로 발생 합니다. `EnhanceForwardProgress` 정책 작업이 앞으로 진행할 수 있도록 하 고는 일정 그룹에 걸쳐 공정성을 예약 해야 하는 경우에 유용 합니다.  
  
## <a name="example"></a>예  
 이 예에서는 정의 `work_yield_agent` 클래스에서 파생 된 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md)합니다. `work_yield_agent` 클래스 수행 된 작업 단위의 현재 컨텍스트를 생성 하 고, 다른 작업 단위를 수행 합니다. 에이전트가 사용 하 여 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 함수를 다른 컨텍스트에서 실행 될 수 있도록 현재 컨텍스트를 협조적으로 양보 합니다.  
  
 이 예제에서는 네 개를 만듭니다 `work_yield_agent` 개체입니다. 을 에이전트가 실행 되는 순서에 영향을 스케줄러 정책을 설정 하는 방법을 설명 하기는 예는 일정을 두 개 그룹 및 다른 일정 그룹에 다른 두 명의 에이전트 처음 두 명의 에이전트를 연결 합니다. 이 예제에서는 사용는 [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) 방법을 만들 수는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체입니다. 예제에서는 두 번 매번 다른 일정 정책 사용 하 여 모든 4 명의 에이전트를 실행합니다.  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Using EnhanceScheduleGroupLocality...  
group 0,
    task 0: first loop...  
group 0,
    task 1: first loop...  
group 0,
    task 0: waiting...  
group 1,
    task 0: first loop...  
group 0,
    task 1: waiting...  
group 1,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 0,
    task 1: second loop...  
group 0,
    task 0: finished...  
group 1,
    task 0: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: finished...  
 
Using EnhanceForwardProgress...  
group 0,
    task 0: first loop...  
group 1,
    task 0: first loop...  
group 0,
    task 0: waiting...  
group 0,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 1,
    task 1: first loop...  
group 0,
    task 1: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 1,
    task 0: second loop...  
group 0,
    task 0: finished...  
group 0,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: finished...  
```  
  
 두 정책을 모두 동일한 시퀀스 이벤트를 생성합니다. 그러나 사용 하는 정책은 `EnhanceScheduleGroupLocality` 에이전트를 두 번째 그룹의 일부인 에이전트를 시작 하기 전에 첫 번째 일정 그룹의 일부인 모두 시작 합니다. 사용 하는 정책 `EnhanceForwardProgress` 첫 번째 그룹에서 한 에이전트를 시작 하 고 다음 두 번째 그룹의 첫 번째 에이전트를 시작 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `scheduling-protocol.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 예약 protocol.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [일정 그룹](../../parallel/concrt/schedule-groups.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

