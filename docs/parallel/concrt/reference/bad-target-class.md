---
title: "bad_target 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::bad_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_target 클래스"
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bad_target 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 메시징 블록이 수행 중인 작업에 유효하지 않은 대상에 대한 포인터를 제공할 때마다 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class bad_target : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[bad\_target::bad\_target 생성자](../Topic/bad_target::bad_target%20Constructor.md)|오버로드됨.  `bad_target` 개체를 생성합니다.|  
  
## 설명  
 이 예외는 일반적으로 다른 대상에 예약된 메시지를 사용하려고 시도하거나 보유하고 있지 않은 예약을 해제하는 대상 같은 이유로 throw된다.  
  
## 상속 계층  
 `exception`  
  
 `bad_target`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)