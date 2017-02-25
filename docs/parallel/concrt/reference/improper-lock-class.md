---
title: "improper_lock 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_lock 클래스"
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# improper_lock 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 잠금을 잘못 얻을 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class improper_lock : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[improper\_lock::improper\_lock 생성자](../Topic/improper_lock::improper_lock%20Constructor.md)|오버로드됨.  `improper_lock exception`을 생성합니다.|  
  
## 설명  
 일반적으로 이 예외는 같은 컨텍스트에서 재진입 잠금을 회귀적으로 얻으려고 시도할 때 throw됩니다.  
  
## 상속 계층  
 `exception`  
  
 `improper_lock`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section 클래스](../../../parallel/concrt/reference/critical-section-class.md)   
 [reader\_writer\_lock 클래스](../../../parallel/concrt/reference/reader-writer-lock-class.md)