---
title: "reader_writer_lock 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::reader_writer_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reader_writer_lock 클래스"
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 21
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# reader_writer_lock 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

작성기 우선 큐 기반 판독기\-작성기는 로컬 회전으로만 잠급니다.  잠금은 FIFO\(선입선출\) 액세스 권한을 작성기에 부여하며 작성기가 연속적으로 로드되면 판독기를 사용할 수 없습니다.  
  
## 구문  
  
```  
class reader_writer_lock;  
```  
  
## 멤버  
  
### 공용 클래스  
  
|Name|설명|  
|----------|--------|  
|[reader\_writer\_lock::scoped\_lock 클래스](../Topic/reader_writer_lock::scoped_lock%20Class.md)|작성기로 `reader_writer_lock` 잠금 개체를 얻는 데 사용할 수 있는 예외 안전 RAII 래퍼입니다.|  
|[reader\_writer\_lock::scoped\_lock\_read 클래스](../Topic/reader_writer_lock::scoped_lock_read%20Class.md)|판독기로 `reader_writer_lock` 잠금 개체를 얻는 데 사용할 수 있는 예외 안전 RAII 래퍼입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[reader\_writer\_lock::reader\_writer\_lock 생성자](../Topic/reader_writer_lock::reader_writer_lock%20Constructor.md)|새 `reader_writer_lock` 개체를 생성합니다.|  
|[reader\_writer\_lock::~reader\_writer\_lock 소멸자](../Topic/reader_writer_lock::~reader_writer_lock%20Destructor.md)|`reader_writer_lock` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[reader\_writer\_lock::lock 메서드](../Topic/reader_writer_lock::lock%20Method.md)|판독기\-작성기 잠금을 작성기로 가져옵니다.|  
|[reader\_writer\_lock::lock\_read 메서드](../Topic/reader_writer_lock::lock_read%20Method.md)|판독기\-작성기 잠금을 판독기로 가져옵니다.  작성기의 경우 활성 판독기는 수행될 때까지 기다려야 합니다.  판독기는 단순히 잠금에서 관심 사항을 등록하고 작성기가 해제되기를 기다립니다.|  
|[reader\_writer\_lock::try\_lock 메서드](../Topic/reader_writer_lock::try_lock%20Method.md)|차단하지 않고 작성기로 판독기\-작성기 잠금을 얻으려고 합니다.|  
|[reader\_writer\_lock::try\_lock\_read 메서드](../Topic/reader_writer_lock::try_lock_read%20Method.md)|차단하지 않고 판독기로 판독기\- 작성기 잠금을 얻으려고 합니다.|  
|[reader\_writer\_lock::unlock 메서드](../Topic/reader_writer_lock::unlock%20Method.md)|판독기 또는 작성기를 잠근 사용자를 기반으로 판독기 및 작성기 잠금을 해제합니다.|  
  
## 설명  
 자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)을 참조하십시오.  
  
## 상속 계층  
 `reader_writer_lock`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section 클래스](../../../parallel/concrt/reference/critical-section-class.md)