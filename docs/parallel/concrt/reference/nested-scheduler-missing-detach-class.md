---
title: "nested_scheduler_missing_detach 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::nested_scheduler_missing_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nested_scheduler_missing_detach 클래스"
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# nested_scheduler_missing_detach 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 `Scheduler` 개체의 `Attach` 메서드를 사용해 두 번째 스케줄러에 연결된 컨텍스트에서 `CurrentScheduler::Detach` 메서드를 호출하지 않은 것을 동시성 런타임이 발견할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class nested_scheduler_missing_detach : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[nested\_scheduler\_missing\_detach::nested\_scheduler\_missing\_detach 생성자](../Topic/nested_scheduler_missing_detach::nested_scheduler_missing_detach%20Constructor.md)|오버로드됨.  `nested_scheduler_missing_detach` 개체를 생성합니다.|  
  
## 설명  
 이 예외는 이미 소유하고 있거나 다른 스케줄러에 추가된 컨텍스트에서 `Scheduler` 개체의 `Attach` 메서드를 호출하여 다른 컨텍스트 내에 한 스케줄러를 중첩할 때만 throw됩니다.  동시성 런타임은 문제 해결을 위한 도움을 제공하는 시나리오를 발견하면 잘못하여 예외를 throw합니다.  `CurrentScheduler::Detach` 메서드 호출을 무시하는 모든 인스턴스가 이 예외를 throw한다는 보장은 없습니다.  
  
## 상속 계층  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach 메서드](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach 메서드](../Topic/Scheduler::Attach%20Method.md)