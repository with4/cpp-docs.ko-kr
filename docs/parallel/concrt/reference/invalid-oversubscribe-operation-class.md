---
title: "invalid_oversubscribe_operation 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::invalid_oversubscribe_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_oversubscribe_operation 클래스"
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
caps.latest.revision: 19
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_oversubscribe_operation 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 먼저 `_BeginOversubscription` 매개 변수를 `true`로 설정한 상태에서 `Context::Oversubscribe` 메서드를 호출하지 않고 `_BeginOversubscription` 매개 변수를 `false`로 설정한 상태에서 `Context::Oversubscribe` 메서드를 호출할 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_oversubscribe\_operation::invalid\_oversubscribe\_operation 생성자](../Topic/invalid_oversubscribe_operation::invalid_oversubscribe_operation%20Constructor.md)|오버로드됨.  `invalid_oversubscribe_operation` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Context::Oversubscribe 메서드](../Topic/Context::Oversubscribe%20Method.md)