---
title: "SchedulerPolicy 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::SchedulerPolicy"
  - "concrtrm/concurrency::SchedulerPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SchedulerPolicy 클래스"
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# SchedulerPolicy 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`SchedulerPolicy` 클래스에는 스케줄러 인스턴스의 동작을 제어하는 각 정책 요소에 대해 하나씩 키\/값 쌍이 포함되어 있습니다.  
  
## 구문  
  
```  
class SchedulerPolicy;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[SchedulerPolicy::SchedulerPolicy 생성자](../Topic/SchedulerPolicy::SchedulerPolicy%20Constructor.md)|오버로드됨.  새 스케줄러 정책을 생성하고 동시성 런타임 및 리소스 관리자가 지원하는 [정책 키](../Topic/PolicyElementKey%20Enumeration.md)의 값으로 채웁니다.|  
|[SchedulerPolicy:: ~ SchedulerPolicy 소멸자](../Topic/SchedulerPolicy::~SchedulerPolicy%20Destructor.md)|스케줄러 정책을 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SchedulerPolicy::GetPolicyValue 메서드](../Topic/SchedulerPolicy::GetPolicyValue%20Method.md)|`_Key` 매개 변수로 제공된 정책 키 값을 검색합니다.|  
|[SchedulerPolicy::SetConcurrencyLimits 메서드](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)|`SchedulerPolicy` 개체에서 `MinConcurrency` 및 `MaxConcurrency` 정책을 동시에 설정합니다.|  
|[SchedulerPolicy::SetPolicyValue 메서드](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)|`_Key` 매개 변수로 제공된 정책 키 값을 검색하고 오래된 값을 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[SchedulerPolicy::operator \= 연산자](../Topic/SchedulerPolicy::operator=%20Operator.md)|다른 스케줄러를 정책의 스케줄러 정책을 할당합니다.|  
  
## 설명  
 `SchedulerPolicy` 클래스를 통해 제어할 수 있는 정책에 대한 자세한 내용은 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)를 참조하세요.  
  
## 상속 계층  
 `SchedulerPolicy`  
  
## 요구 사항  
 **헤더:**  concrt.h, concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey 열거형](../Topic/PolicyElementKey%20Enumeration.md)   
 [CurrentScheduler 클래스](../../../parallel/concrt/reference/currentscheduler-class.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)