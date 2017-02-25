---
title: "missing_wait 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::missing_wait"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "missing_wait 클래스"
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# missing_wait 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 개체의 소멸자를 실행할 때 `task_group` 또는 `structured_task_group` 개체에 작업이 예약되어 있을 때 throw되는 예외를 설명합니다.  예외의 결과로 스택 해제로 소멸자가 도달할 경우 이 예외는 throw되지 않습니다.  
  
## 구문  
  
```  
class missing_wait : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[missing\_wait::missing\_wait 생성자](../Topic/missing_wait::missing_wait%20Constructor.md)|오버로드됨.  `missing_wait` 개체를 생성합니다.|  
  
## 설명  
 예외 흐름이 없으면 해당 개체가 소멸되기 전에 `task_group` 또는 `structured_task_group` 개체의 `wait` 또는 `run_and_wait` 메서드를 호출해야 합니다.  런타임은 `wait` 또는 `run_and_wait` 메서드를 호출하지 않았음을 알리기 위해 이 예외를 throw합니다.  
  
## 상속 계층  
 `exception`  
  
 `missing_wait`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group 클래스](../Topic/task_group%20Class.md)   
 [task\_group::wait 메서드](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait 메서드](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group 클래스](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::wait 메서드](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait 메서드](../Topic/structured_task_group::run_and_wait%20Method.md)