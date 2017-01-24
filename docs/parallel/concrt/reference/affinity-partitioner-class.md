---
title: "affinity_partitioner 클래스 | Microsoft Docs"
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
  - "ppl/concurrency::affinity_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "affinity_partitioner 클래스"
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# affinity_partitioner 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`affinity_partitioner` 클래스는 `static_partitioner` 클래스와 비슷하지만, 이 클래스는 작업자 스레드로의 매핑 서브레인지의 선택에 의한 캐시 선호도를 향상시킵니다.  이것은 동일한 데이터 집합에 대해 루프를 다시 실행하고 캐시가 데이터 맞을 때 성능을 크게 향상시킬 수 있습니다.  동일한 `affinity_partitioner` 개체는 데이터 집약성을 활용하기 위해 특정 데이터 집합에 대해 실행되는 병렬 루프의 후속 반복과 함께 사용되어야 합니다.  
  
## 구문  
  
```  
class affinity_partitioner;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[affinity\_partitioner::affinity\_partitioner 생성자](../Topic/affinity_partitioner::affinity_partitioner%20Constructor.md)|`affinity_partitioner` 개체를 생성합니다.|  
|[affinity\_partitioner::~affinity\_partitioner 소멸자](../Topic/affinity_partitioner::~affinity_partitioner%20Destructor.md)|`affinity_partitioner` 개체를 소멸시킵니다.|  
  
## 상속 계층  
 `affinity_partitioner`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)