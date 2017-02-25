---
title: "simple_partitioner 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::simple_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "simple_partitioner 클래스"
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# simple_partitioner 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`simple_partitioner` 클래스는 `parallel_for` 의 반복으로 인한 범위의 정적 분할을 나타냅니다.  분할자는 각 부분이 부븐 크기에 의해 지정된 반복의 횟수 이상이 되도록 범위를 나눕니다.  
  
## 구문  
  
```  
class simple_partitioner;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[simple\_partitioner::simple\_partitioner 생성자](../Topic/simple_partitioner::simple_partitioner%20Constructor.md)|`simple_partitioner` 개체를 생성합니다.|  
|[simple\_partitioner::~simple\_partitioner 소멸자](../Topic/simple_partitioner::~simple_partitioner%20Destructor.md)|`simple_partitioner` 개체를 소멸시킵니다.|  
  
## 상속 계층  
 `simple_partitioner`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)