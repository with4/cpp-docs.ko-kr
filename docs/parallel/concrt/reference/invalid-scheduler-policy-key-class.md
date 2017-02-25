---
title: "invalid_scheduler_policy_key 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_scheduler_policy_key"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_key 클래스"
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_scheduler_policy_key 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 잘못되었거나 알 수 없는 키가 `SchedulerPolicy` 개체 생성자로 전달되거나 `SchedulerPolicy` 개체의 `SetPolicyValue` 메서드가 `SetConcurrencyLimits` 메서드 같은 다른 수단을 사용해 변경해야 하는 키를 전달할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class invalid_scheduler_policy_key : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_scheduler\_policy\_key::invalid\_scheduler\_policy\_key 생성자](../Topic/invalid_scheduler_policy_key::invalid_scheduler_policy_key%20Constructor.md)|오버로드됨.  `invalid_scheduler_policy_key` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy 클래스](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue 메서드](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits 메서드](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)