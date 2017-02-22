---
title: "message_not_found 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::message_not_found"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_not_found 클래스"
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# message_not_found 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 메시징 블록이 요청한 메시지를 찾을 수 없을 때 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class message_not_found : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[message\_not\_found::message\_not\_found 생성자](../Topic/message_not_found::message_not_found%20Constructor.md)|오버로드됨.  `message_not_found` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `message_not_found`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)