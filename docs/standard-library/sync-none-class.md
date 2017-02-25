---
title: "sync_none 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.sync_none"
  - "sync_none"
  - "allocators/stdext::sync_none"
  - "stdext::sync_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_none 클래스"
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# sync_none 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes a [synchronization filter](../standard-library/allocators-header.md) that provides no synchronization.  
  
## 구문  
  
```  
template <class Cache> class sync_none  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Cache`|The type of cache associated with the synchronization filter.  This can be [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md), or [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[allocate](../Topic/sync_none::allocate.md)|Allocates a block of memory.|  
|[deallocate](../Topic/sync_none::deallocate.md)|Frees a specified number of objects from storage beginning at a specified position.|  
|[equals](../Topic/sync_none::equals.md)|Compares two caches for equality.|  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)