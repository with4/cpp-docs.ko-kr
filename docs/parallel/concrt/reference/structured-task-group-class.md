---
title: "structured_task_group 클래스 | Microsoft Docs"
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
  - "ppl/concurrency::structured_task_group"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "structured_task_group 클래스"
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# structured_task_group 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`structured_task_group` 클래스는 매우 구조적인 병렬 작업 컬렉션을 나타냅니다.  실행을 시작하지 않은 작업을 중단하는 실행이 완료되기 전에 `task_handle` 개체를 사용하여 `structured_task_group`에 개별 병렬 작업을 큐에 추가하고 완료되기를 기다리거나 작업 그룹을 취소할 수 있습니다.  
  
## 구문  
  
```  
class structured_task_group;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[structured\_task\_group::structured\_task\_group 생성자](../Topic/structured_task_group::structured_task_group%20Constructor.md)|오버로드됨.  새 `structured_task_group` 개체를 생성합니다.|  
|[structured\_task\_group::~structured\_task\_group 소멸자](../Topic/structured_task_group::~structured_task_group%20Destructor.md)|`structured_task_group` 개체를 소멸시킵니다.  예외로 인한 스택 해제의 결과로 소멸자가 실행되지 않는 경우 소멸자 실행 전에 개체에서 `wait` 또는 `run_and_wait` 메서드를 호출해야 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[structured\_task\_group::cancel 메서드](../Topic/structured_task_group::cancel%20Method.md)|이 작업 그룹에서 시작한 작업의 하위 트리를 취소하려는 시도를 하십시오.  작업 그룹에 예약된 모든 작업은 가능한 경우 전이적으로 취소됩니다.|  
|[structured\_task\_group::is\_canceling 메서드](../Topic/structured_task_group::is_canceling%20Method.md)|작업 그룹이 현재 취소 중에 있는지 여부를 호출자에게 알립니다.  이는 `cancel` 메서드가 `structured_task_group` 개체에서 호출된 것을 반드시 나타낼 필요는 없습니다\(이 메서드가 `true`를 반드시 반환한다는 보장은 없음\).  `structured_task_group` 개체가 인라인으로 실행되고 있고 작업 트리에 있는 작업 그룹이 취소된 경우일 수 있습니다.  이 경우 취소가 이 `structured_task_group` 개체를 통해 진행되는 사전 시간을 런타임이 확인할 수 있는 경우 `true`도 반환됩니다.|  
|[structured\_task\_group::run 메서드](../Topic/structured_task_group::run%20Method.md)|오버로드됨.  `structured_task_group` 개체에서 작업을 예약합니다.  호출자가 `_Task_handle` 매개 변수에 전달된 `task_handle` 개체의 수명을 관리합니다.   `_Placement`  매개 변수를 사용하는 버전은 작업이 해당 매개 변수에 의해 지정된 위치에서 실행하도록 합니다.|  
|[structured\_task\_group::run\_and\_wait 메서드](../Topic/structured_task_group::run_and_wait%20Method.md)|오버로드됨.  전체 취소 지원을 받으려면 `structured_task_group` 개체의 지원을 받아 호출 컨텍스트에 대해 인라인 실행하는 작업을 예약합니다.  `task_handle` 개체가 매개 변수로 `run_and_wait`에 전달되는 경우 호출자는 `task_handle` 개체의 수명을 관리하는 일을 담당합니다.  그런 다음 함수는 `structured_task_group` 개체에 대한 모든 작업이 완료되거나 취소될 때까지 대기합니다.|  
|[structured\_task\_group::wait 메서드](../Topic/structured_task_group::wait%20Method.md)|`structured_task_group`의 모든 작업이 완료되거나 취소될 때까지 기다립니다.|  
  
## 설명  
 성능 개선을 위해 `structured_task_group` 개체의 사용에 여러 가지 심각한 제한이 부과되었습니다.  
  
-   `structured_task_group` 단일 개체는 여러 스레드에서 사용할 수 없습니다.  `structured_task_group` 개체에 대한 모든 작업은 개체를 만든 스레드에서 수행되어야 합니다.  이 규칙의 두 가지 예외는 멤버 함수 `cancel` 및 `is_canceling`입니다.  개체는 lambda 식의 목록에 없을 수 있으며 작업이 취소 작업 중 하나를 사용하는 경우가 아니면 작업 내에서 사용될 수 있습니다.  
  
-   `structured_task_group` 개체에 예약된 모든 작업은 수명을 명시적으로 관리해야 하는 `task_handle` 개체를 사용하여 예약됩니다.  
  
-   여러 그룹은 반드시 중첩된 순서로만 사용할 수 있습니다.  두 `structured_task_group` 개체가 선언된 경우 선언할 두 번째 개체\(내부 개체\)는 `cancel` 또는 `is_canceling`이 첫 번째 개체\(외부 개체\)에서 호출되는 것을 제외하고 메서드 전에 소멸되어야 합니다.  이 조건은 동일하거나 기능적으로 중첩된 범위 내에서 여러 `structured_task_group` 개체를 선언하는 경우 및 `run` 또는 `run_and_wait`를 통해 `structured_task_group`에 큐에 추가된 작업의 경우 모두에 적용됩니다.  
  
-   일반 `task_group` 클래스와 달리 `structured_task_group` 클래스의 모든 상태는 최종 상태입니다.  그룹에 큐 추가 작업을 수행하고 완료되기를 기다린 후에 다시 같은 그룹을 사용할 수 없습니다.  
  
 자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)을 참조하십시오.  
  
## 상속 계층  
 `structured_task_group`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group 클래스](../Topic/task_group%20Class.md)   
 [task\_handle 클래스](../../../parallel/concrt/reference/task-handle-class.md)