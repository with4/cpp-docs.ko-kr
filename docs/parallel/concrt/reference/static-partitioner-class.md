---
title: "static_partitioner 클래스 | Microsoft Docs"
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
  - "ppl/concurrency::static_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "static_partitioner 클래스"
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 8
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# static_partitioner 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`static_partitioner` 클래스는 `parallel_for` 의 반복으로 인한 범위의 정적 분할을 나타냅니다.  분할자는 최대한 많은 근로자가 근본적인 스케줄러에 사용할 수 있도록 범위를 부분으로 나눕니다.  
  
## 구문  
  
```  
class static_partitioner;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[static\_partitioner::static\_partitioner 생성자](../Topic/static_partitioner::static_partitioner%20Constructor.md)|`static_partitioner` 개체를 생성합니다.|  
|[static\_partitioner::~static\_partitioner 소멸자](../Topic/static_partitioner::~static_partitioner%20Destructor.md)|`static_partitioner` 개체를 소멸시킵니다.|  
  
## 상속 계층  
 `static_partitioner`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)