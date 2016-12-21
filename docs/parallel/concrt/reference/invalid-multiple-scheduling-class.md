---
title: "invalid_multiple_scheduling 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::invalid_multiple_scheduling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_multiple_scheduling 클래스"
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_multiple_scheduling 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 `task_handle` 개체가 `wait` 또는 `run_and_wait` 메서드 호출에 지장을 주지 않고 `task_group` 또는 `structured_task_group` 개체의 `run` 메서드를 사용하여 예약될 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class invalid_multiple_scheduling : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_multiple\_scheduling::invalid\_multiple\_scheduling 생성자](../Topic/invalid_multiple_scheduling::invalid_multiple_scheduling%20Constructor.md)|오버로드됨.  `invalid_multiple_scheduling` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_handle 클래스](../../../parallel/concrt/reference/task-handle-class.md)   
 [task\_group 클래스](../Topic/task_group%20Class.md)   
 [task\_group::run 메서드](../Topic/task_group::run%20Method.md)   
 [task\_group::wait 메서드](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait 메서드](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group 클래스](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::run 메서드](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait 메서드](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait 메서드](../Topic/structured_task_group::run_and_wait%20Method.md)