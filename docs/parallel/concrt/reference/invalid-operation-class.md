---
title: "invalid_operation 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_operation 클래스"
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_operation 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 잘못된 작업이 수행될 때 throw되는 예외로, 동시성 런타임에서 throw된 다른 예외 형식으로 보다 정확하게 설명되지 않은 예외를 설명합니다.  
  
## 구문  
  
```  
class invalid_operation : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_operation::invalid\_operation 생성자](../Topic/invalid_operation::invalid_operation%20Constructor.md)|오버로드됨.  `invalid_operation` 개체를 생성합니다.|  
  
## 설명  
 이 예외를 throw하는 다양한 메서드는 일반적으로 어떤 상황에서 이를 throw할지 문서화합니다.  
  
## 상속 계층  
 `exception`  
  
 `invalid_operation`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)