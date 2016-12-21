---
title: "task_canceled 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::task_canceled"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_canceled 클래스"
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_canceled 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 현재 작업을 강제 취소하도록 PPL 작업 레이어에서 throw된 예외를 설명합니다.  또한 취소된 작업의 경우 [작업](../Topic/Task%20Class%20-%20Internal%20Members.md)에서 `get()` 메서드에 의해 throw됩니다.  
  
## 구문  
  
```  
class task_canceled : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[task\_canceled::task\_canceled 생성자](../Topic/task_canceled::task_canceled%20Constructor.md)|오버로드됨.  `task_canceled` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `task_canceled`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task::get 메서드](../Topic/task::get%20Method.md)   
 [cancel\_current\_task 함수](../Topic/cancel_current_task%20Function.md)