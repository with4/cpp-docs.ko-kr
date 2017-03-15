---
title: "작업 스케줄러(동시성 런타임) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "간단한 작업[동시성 런타임]"
  - "초과 구독[동시성 런타임]"
  - "일정 그룹[동시성 런타임]"
  - "스케줄러 인스턴스[동시성 런타임]"
  - "스케줄러 정책[동시성 런타임]"
  - "작업 스케줄러[동시성 런타임]"
  - "작업 스케줄러[동시성 런타임], 간단한 작업"
  - "작업 스케줄러[동시성 런타임], 초과 구독"
  - "작업 스케줄러[동시성 런타임], 일정 그룹"
  - "작업 스케줄러[동시성 런타임], 스케줄러 인스턴스"
  - "작업 스케줄러[동시성 런타임], 스케줄러 정책"
  - "작업 스케줄러[동시성 런타임], wait 함수"
  - "wait 함수[동시성 런타임]"
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
caps.latest.revision: 42
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 41
---
# 작업 스케줄러(동시성 런타임)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

설명서의 이 부분의 항목에서는 동시성 런타임 작업 스케줄러의 중요한 기능에 대해 설명합니다.  작업 스케줄러는 동시성 런타임을 사용하는 기존 코드의 성능을 미세 조정하려는 경우에 유용합니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서는 작업 스케줄러를 사용할 수 없습니다.  자세한 내용은 [C\+\+로 Windows 스토어 앱용 비동기 작업 만들기](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)를 참조하세요.  
>   
>  Visual Studio 2015 이상 버전에서 ppltasks.h의 [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) 클래스 및 관련 형식은 Windows ThreadPool을 해당 스케줄러로 사용합니다.  이 항목은 ppltasks.h에서 정의된 형식에 더 이상 적용되지 않습니다.  Parallel\_for와 같은 병렬 알고리즘은 동시성 런타임을 기본 스케줄러로 계속 사용합니다.  
  
> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다.  작업 스케줄러는 응용 프로그램의 성능을 미세 조정하는 데 도움이 되기 때문에 동시성 런타임을 처음 사용하는 경우 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)에서 시작하는 것이 좋습니다.  
  
 작업 스케줄러는 런타임에 작업을 예약하고 조정합니다.  *작업*은 특정 작업을 수행하는 작업 단위입니다.  작업은 일반적으로 다른 작업과 병렬로 실행될 수 있습니다.  작업 그룹 항목, 병렬 알고리즘 및 비동기 에이전트에서 수행하는 작업이 모두 작업의 예입니다.  
  
 작업 스케줄러는 여러 컴퓨팅 리소스가 있는 컴퓨터에서 효율적인 작업 예약과 관련된 세부 정보를 관리합니다.  또한 작업 스케줄러는 기본 운영 체제의 최신 기능을 사용합니다.  따라서 동시성 런타임을 사용하는 응용 프로그램은 확장된 기능이 있는 하드웨어에서 자동으로 크기가 조정되고 향상됩니다.  
  
 [기타 동시성 모델과 비교](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)에서는 우선 및 협조적 일정 예약 메커니즘 간의 차이점을 설명합니다.  작업 스케줄러는 협조적 일정 및 작업 가로채기 알고리즘을 운영 체제의 우선 스케줄러와 함께 사용하여 처리 리소스의 사용량을 최대화합니다.  
  
 동시성 런타임은 기본 스케줄러를 제공하므로 인프라 세부 정보를 관리할 필요가 없습니다.  따라서 일반적으로 작업 스케줄러를 직접 사용하지는 않습니다.  그러나 응용 프로그램의 품질 요구 사항을 충족하기 위해 작업 스케줄러를 사용하여 고유한 일정 예약 정책을 제공하거나 스케줄러를 특정 작업에 연결할 수 있습니다.  예를 들어 최대 4개 프로세서까지만 크기가 조정되는 병렬 정렬 루틴이 있다고 가정합니다.  *스케줄러 정책*을 사용하여 최대 4개의 동시 작업을 생성하는 스케줄러를 만들 수 있습니다.  이 스케줄러에서 정렬 루틴을 실행하면 다른 활성 스케줄러가 나머지 처리 리소스를 모두 사용할 수 있습니다.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)|스케줄러 인스턴스와 `concurrency::Scheduler` 및 `concurrency::CurrentScheduler` 클래스를 사용하여 스케줄러 인스턴스를 관리하는 방법을 설명합니다.  특정 형식의 작업에 명시적 일정 예약 정책을 연결하려는 경우 스케줄러 인스턴스를 사용합니다.|  
|[스케줄러 정책](../../parallel/concrt/scheduler-policies.md)|스케줄러 정책의 역할을 설명합니다.  스케줄러가 작업을 관리할 때 사용하는 전략을 제어하려는 경우 스케줄러 정책을 사용합니다.|  
|[일정 그룹](../../parallel/concrt/schedule-groups.md)|일정 그룹의 역할을 설명합니다.  작업 간에 높은 수준의 국부성이 필요한 경우, 예를 들어 동일한 프로세서 노드에서 관련 작업 그룹을 실행하면 이점이 있는 경우 일정 그룹을 사용합니다.|  
|[간단한 작업](../../parallel/concrt/lightweight-tasks.md)|간단한 작업의 역할을 설명합니다.  간단한 작업은 동시성 런타임의 일정 예약 기능을 사용하도록 기존 코드를 조정하는 경우에 유용합니다.|  
|[컨텍스트](../../parallel/concrt/contexts.md)|컨텍스트, `concurrency::wait` 함수 및 `concurrency::Context` 클래스의 역할을 설명합니다.  컨텍스트가 차단, 차단 해제 및 양보하는 시기를 제어해야 하는 경우 또는 응용 프로그램에서 초과 구독을 사용할 수 있게 하려는 경우에 이 기능을 사용합니다.|  
|[메모리 관리 함수](../../parallel/concrt/memory-management-functions.md)|`concurrency::Alloc` 및 `concurrency::Free` 함수를 설명합니다.  이러한 함수는 동시에 메모리를 할당 및 해제하여 메모리 성능을 향상시킬 수 있습니다.|  
|[기타 동시성 모델과 비교](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|우선 및 협조적 일정 예약 메커니즘 간의 차이점을 설명합니다.|  
|[PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md)|응용 프로그램에서 병렬 알고리즘과 같은 다양한 병렬 패턴을 사용하는 방법을 설명합니다.|  
|[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)|응용 프로그램에서 비동기 에이전트를 사용하는 방법을 설명합니다.|  
|[동시성 런타임](../../parallel/concrt/concurrency-runtime.md)|병렬 프로그래밍을 간소화하는 동시성 런타임에 대해 설명하고 관련 항목의 링크를 제공합니다.|