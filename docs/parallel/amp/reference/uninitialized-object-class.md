---
title: "uninitialized_object 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::uninitialized_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uninitialized_object 클래스"
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# uninitialized_object 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

초기화된 개체가 사용될 때 throw되는 예외입니다.  
  
## 구문  
  
```  
class uninitialized_object : public runtime_exception;  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[uninitialized\_object::uninitialized\_object 생성자](../Topic/uninitialized_object::uninitialized_object%20Constructor.md)|`uninitialized_object` 클래스의 새 인스턴스를 초기화합니다.|  
  
## 상속 계층  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)