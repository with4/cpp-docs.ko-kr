---
title: "improper_scheduler_attach 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_scheduler_attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_attach 클래스"
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# improper_scheduler_attach 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 이미 현재 컨텍스트에 연결된 `Scheduler` 개체에서 `Attach` 메서드를 호출할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class improper_scheduler_attach : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[improper\_scheduler\_attach::improper\_scheduler\_attach 생성자](../Topic/improper_scheduler_attach::improper_scheduler_attach%20Constructor.md)|오버로드됨.  `improper_scheduler_attach` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `improper_scheduler_attach`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach 메서드](../Topic/Scheduler::Attach%20Method.md)