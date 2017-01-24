---
title: "out_of_memory 클래스 | Microsoft Docs"
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
  - "amprt/Concurrency::out_of_memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out_of_memory 클래스"
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# out_of_memory 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

장치 또는 시스템 메모리 부족으로 인해 메서드가 실패할 때 발생되는 예외입니다.  
  
## 구문  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[out\_of\_memory::out\_of\_memory 생성자](../Topic/out_of_memory::out_of_memory%20Constructor.md)|`out_of_memory` 클래스의 새 인스턴스를 초기화합니다.|  
  
## 상속 계층  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)