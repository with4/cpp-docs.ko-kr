---
title: "sync_per_thread 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::sync_per_thread"
  - "sync_per_thread"
  - "allocators/stdext::sync_per_thread"
  - "stdext.sync_per_thread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_thread 클래스"
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sync_per_thread 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes a [synchronization filter](../standard-library/allocators-header.md) that provides a separate cache object for each thread.  
  
## 구문  
  
```  
template <class Cache> class sync_per_thread  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Cache`|The type of cache associated with the synchronization filter.  This can be [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md), or [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## 설명  
 Allocators that use `sync_per_thread` can compare equal even though blocks allocated in one thread cannot be deallocated from another thread.  When using one of these allocators memory blocks allocated in one thread should not be made visible to other threads.  In practice this means that a container that uses one of these allocators should only be accessed by a single thread.  
  
### 멤버 함수  
  
|||  
|-|-|  
|[allocate](../Topic/sync_per_thread::allocate.md)|Allocates a block of memory.|  
|[deallocate](../Topic/sync_per_thread::deallocate.md)|Frees a specified number of objects from storage beginning at a specified position.|  
|[equals](../Topic/sync_per_thread::equals.md)|Compares two caches for equality.|  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)