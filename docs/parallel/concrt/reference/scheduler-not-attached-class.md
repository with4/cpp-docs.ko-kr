---
title: "scheduler_not_attached 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::scheduler_not_attached"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_not_attached 클래스"
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_not_attached 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 현재 컨텍스트에 연결해야 하는 작업을 수행할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class scheduler_not_attached : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_not\_attached::scheduler\_not\_attached 생성자](../Topic/scheduler_not_attached::scheduler_not_attached%20Constructor.md)|오버로드됨.  `scheduler_not_attached` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `scheduler_not_attached`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler 클래스](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach 메서드](../Topic/Scheduler::Attach%20Method.md)