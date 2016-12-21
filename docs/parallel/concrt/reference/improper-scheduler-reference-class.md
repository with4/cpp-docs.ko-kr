---
title: "improper_scheduler_reference 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::improper_scheduler_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_reference 클래스"
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# improper_scheduler_reference 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 해당 스케줄러의 일부가 아닌 컨텍스트에서 종료 중인 `Scheduler` 개체에서 `Reference` 메서드가 호출될 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class improper_scheduler_reference : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[improper\_scheduler\_reference::improper\_scheduler\_reference 생성자](../Topic/improper_scheduler_reference::improper_scheduler_reference%20Constructor.md)|오버로드됨.  `improper_scheduler_reference` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `improper_scheduler_reference`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Reference 메서드](../Topic/Scheduler::Reference%20Method.md)