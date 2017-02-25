---
title: "auto_partitioner 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::auto_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_partitioner 클래스"
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_partitioner 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`auto_partitioner` 클래스는 기본 메서드를 나타내고 `parallel_for`, `parallel_for_each` 및 `parallel_transform` 은 그들이 반복하는 반복은 범위 분할을 사용합니다.  직원 분할 방법은 로드 균형 조정에 대한 가로채기, 심지어 반복 당 취소도 포함합니다.  
  
## 구문  
  
```  
class auto_partitioner;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[auto\_partitioner::auto\_partitioner 생성자](../Topic/auto_partitioner::auto_partitioner%20Constructor.md)|`auto_partitioner` 개체를 생성합니다.|  
|[auto\_partitioner::~auto\_partitioner 소멸자](../Topic/auto_partitioner::~auto_partitioner%20Destructor.md)|`auto_partitioner` 개체를 소멸시킵니다.|  
  
## 상속 계층  
 `auto_partitioner`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)