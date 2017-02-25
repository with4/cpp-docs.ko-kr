---
title: "unique_lock 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::unique_lock"
dev_langs: 
  - "C++"
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# unique_lock 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a template that can be instantiated to create objects that manage the locking and unlocking of a `mutex`.  
  
## 구문  
  
```  
template<class Mutex>  
class unique_lock;  
```  
  
## 설명  
 The template argument `Mutex` must name a *mutex type*.  
  
 Internally, a `unique_lock` stores a pointer to an associated `mutex` object and a `bool` that indicates whether the current thread owns the `mutex`.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`unique_lock::mutex_type`|Synonym for the template argument `Mutex`.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[unique\_lock::unique\_lock 생성자](../Topic/unique_lock::unique_lock%20Constructor.md)|`unique_lock` 개체를 생성합니다.|  
|[unique\_lock::~unique\_lock 소멸자](../Topic/unique_lock::~unique_lock%20Destructor.md)|Releases any resources that are associated with the `unique_lock` object.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[unique\_lock::lock 메서드](../Topic/unique_lock::lock%20Method.md)|Blocks the calling thread until the thread obtains ownership of the associated `mutex`.|  
|[unique\_lock::mutex 메서드](../Topic/unique_lock::mutex%20Method.md)|Retrieves the stored pointer to the associated `mutex`.|  
|[unique\_lock::owns\_lock 메서드](../Topic/unique_lock::owns_lock%20Method.md)|Specifies whether the calling thread owns the associated `mutex`.|  
|[unique\_lock::release 메서드](../Topic/unique_lock::release%20Method.md)|Disassociates the `unique_lock` object from the associated `mutex` object.|  
|[unique\_lock::swap 메서드](../Topic/unique_lock::swap%20Method.md)|Swaps the associated `mutex` and ownership status with that of a specified object.|  
|[unique\_lock::try\_lock 메서드](../Topic/unique_lock::try_lock%20Method.md)|차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[unique\_lock::try\_lock\_for 메서드](../Topic/unique_lock::try_lock_for%20Method.md)|차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[unique\_lock::try\_lock\_until 메서드](../Topic/unique_lock::try_lock_until%20Method.md)|차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[unique\_lock::unlock 메서드](../Topic/unique_lock::unlock%20Method.md)|Releases ownership of the associated `mutex`.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[unique\_lock::operator bool 연산자](../Topic/unique_lock::operator%20bool%20Operator.md)|Specifies whether the calling thread has ownership of the associated `mutex`.|  
|[unique\_lock::operator\= 연산자](../Topic/unique_lock::operator=%20Operator.md)|Copies the stored `mutex` pointer and associated ownership status from a specified object.|  
  
## 상속 계층  
 `unique_lock`  
  
## 요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)