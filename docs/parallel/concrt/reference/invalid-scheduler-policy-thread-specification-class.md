---
title: "invalid_scheduler_policy_thread_specification 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::invalid_scheduler_policy_thread_specification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_thread_specification 클래스"
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_scheduler_policy_thread_specification 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 `MinConcurrency` 키의 값이 `MaxConcurrency` 키의 값보다 작은 `SchedulerPolicy` 개체의 동시성 제한을 설정하려는 시도를 할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class invalid_scheduler_policy_thread_specification : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_scheduler\_policy\_thread\_specification::invalid\_scheduler\_policy\_thread\_specification 생성자](../Topic/invalid_scheduler_policy_thread_specification::invalid_scheduler_policy_thread_specification%20Constructor.md)|오버로드됨.  `invalid_scheduler_policy_value` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy 클래스](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetConcurrencyLimits 메서드](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)