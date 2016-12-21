---
title: "improper_scheduler_detach 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::improper_scheduler_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_detach 클래스"
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# improper_scheduler_detach 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 `Scheduler` 개체의 `Attach` 메서드를 사용해서 스케줄러에 연결되지 않은 컨텍스트에서 `CurrentScheduler::Detach` 메서드가 호출될 때마다 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class improper_scheduler_detach : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[improper\_scheduler\_detach::improper\_scheduler\_detach 생성자](../Topic/improper_scheduler_detach::improper_scheduler_detach%20Constructor.md)|오버로드됨.  `improper_scheduler_detach` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `improper_scheduler_detach`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach 메서드](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach 메서드](../Topic/Scheduler::Attach%20Method.md)