---
title: "default_scheduler_exists 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::default_scheduler_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default_scheduler_exists 클래스"
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default_scheduler_exists 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 기본 스케줄러가 프로세스 내에서 이미 있는 경우 `Scheduler::SetDefaultSchedulerPolicy` 메서드를 호출할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class default_scheduler_exists : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[default\_scheduler\_exists::default\_scheduler\_exists 생성자](../Topic/default_scheduler_exists::default_scheduler_exists%20Constructor.md)|오버로드됨.  `default_scheduler_exists` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `default_scheduler_exists`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler::SetDefaultSchedulerPolicy 메서드](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)