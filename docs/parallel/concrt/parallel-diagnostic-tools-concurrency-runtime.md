---
title: "병렬 진단 도구(동시성 런타임) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "병렬 진단 도구[동시성 런타임]"
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: 15
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 병렬 진단 도구(동시성 런타임)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]에서는 다중 스레드 응용 프로그램의 디버깅 및 프로파일링을 광범위하게 지원합니다.  
  
## 디버깅  
 Visual Studio 디버거는  **병렬 스택** 창  **병렬 작업** 창 및  **병렬 감시** 창을 포함합니다.  자세한 내용은 [연습: 병렬 응용 프로그램 디버깅](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md) 및 [방법: 병렬 조사식 창 사용](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md)를 참조하십시오.  
  
## 프로파일링  
 프로파일링 도구에서는 다중 스레드 응용 프로그램이 해당 응용 프로그램 자체 또는 다른 프로그램과 상호 작용하는 방식에 대한 그래픽, 표 형식 및 숫자 정보를 표시하는 세 가지 데이터 뷰를 제공합니다.  이러한 뷰를 사용하면 관심 있는 영역을 빠르게 식별하고 표시된 그래픽의 위치에서 호출 스택, 호출 사이트 및 소스 코드로 이동할 수 있습니다.  자세한 내용은 [동시성 시각화 도우미](../Topic/Concurrency%20Visualizer.md)을 참조하십시오.  
  
## 이벤트 추적  
 동시성 런타임에서는 다양한 이벤트가 발생할 경우 ETW\([Windows용 이벤트 추적](http://msdn.microsoft.com/library/windows/desktop/bb968803)\)를 사용하여 프로파일러와 같은 계측 도구에 알립니다.  이러한 이벤트에는 스케줄러가 활성화되거나 비활성화되는 경우, 컨텍스트가 시작되거나 끝나거나 차단되거나 차단 해제되거나 양보되거나, 병렬 알고리즘이 시작되거나 끝나는 경우가 포함됩니다.  
  
 [동시성 시각화 도우미](../Topic/Concurrency%20Visualizer.md)와 같은 도구는 이러한 기능을 사용하므로 일반적으로 사용자가 이러한 이벤트를 직접 사용할 필요가 없습니다.  그러나 사용자 지정 프로파일러를 개발할 때나 [Xperf](http://go.microsoft.com/fwlink/?LinkID=160628)와 같은 이벤트 추적 도구를 사용할 때는 이러한 이벤트가 유용합니다.  
  
 추적을 사용하도록 설정되어 있는 경우에만 동시성 런타임에서 이러한 이벤트를 발생시킵니다.  이벤트 추적을 사용하도록 설정하려면 [concurrency::EnableTracing](../Topic/EnableTracing%20Function.md) 함수를 호출하고 이벤트 추적을 사용하지 않도록 설정하려면 [concurrency::DisableTracing](../Topic/DisableTracing%20Function.md) 함수를 호출합니다.  
  
 다음 표에서는 이벤트 추적을 사용하도록 설정되어 있을 때 런타임에서 발생시키는 이벤트에 대해 설명합니다.  
  
|Event|설명|값|  
|-----------|--------|-------|  
|[concurrency::ConcRT\_ProviderGuid](../Topic/ConcRT_ProviderGuid%20Constant.md)|동시성 런타임에 대한 ETW 공급자 식별자입니다.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](../Topic/ContextEventGuid%20Constant.md)|컨텍스트와 관련된 이벤트를 표시합니다.|`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](../Topic/PPLParallelForEventGuid%20Constant.md)|[concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘에 대한 호출의 진입 및 종료를 표시합니다.|`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](../Topic/PPLParallelForeachEventGuid%20Constant.md)|[concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘에 대한 호출의 진입 및 종료를 표시합니다.|`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|[concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘에 대한 호출의 진입 및 종료를 표시합니다.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](../Topic/SchedulerEventGuid%20Constant.md)|[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)와 관련된 이벤트를 표시합니다.|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](../Topic/VirtualProcessorEventGuid%20Constant.md)|가상 프로세서와 관련된 이벤트를 표시합니다.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 동시성 런타임에서 다음 이벤트를 정의하지만 현재 발생시키지는 않습니다.  런타임에서 이러한 이벤트를 나중에 사용하도록 예약합니다.  
  
-   [concurrency::ConcRTEventGuid](../Topic/ConcRTEventGuid%20Constant.md)  
  
-   [concurrency::ScheduleGroupEventGuid](../Topic/SchedulerEventGuid%20Constant.md)  
  
-   [concurrency::ChoreEventGuid](../Topic/ChoreEventGuid%20Constant.md)  
  
-   [concurrency::LockEventGuid](../Topic/LockEventGuid%20Constant.md)  
  
-   [concurrency::ResourceManagerEventGuid](../Topic/ResourceManagerEventGuid%20Constant.md)  
  
 [concurrency::ConcRT\_EventType](../Topic/ConcRT_EventType%20Enumeration.md) 열거형은 이벤트가 추적하는 사용 가능한 작업을 지정합니다.  예를 들어 `parallel_for` 알고리즘의 진입 시 런타임에서 `PPLParallelForEventGuid` 이벤트를 발생시키고 `CONCRT_EVENT_START`를 작업으로 제공합니다.  `parallel_for` 알고리즘에서 반환하기 전에 런타임에서 다시 `PPLParallelForEventGuid` 이벤트를 발생시키고 `CONCRT_EVENT_END`를 작업으로 제공합니다.  
  
 다음 예제에서는 `parallel_for`에 대한 호출 추적을 사용하도록 설정하는 방법을 보여 줍니다.  `parallel_for`에 대한 첫 번째 호출을 추적하도록 설정되어 있지 않으므로 런타임에서 이 호출을 추적하지 않습니다.  `EnableTracing`을 호출하면 런타임에서 `parallel_for`에 대한 두 번째 호출을 추적하도록 설정됩니다.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/CPP/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 런타임에서 `EnableTracing` 및 `DisableTracing`을 호출하는 횟수를 추적합니다.  따라서 `EnableTracing`을 여러 번 호출하는 경우 추적을 사용하지 않도록 설정하기 위해 같은 횟수만큼 `DisableTracing`을 호출해야 합니다.  
  
## 참고 항목  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)