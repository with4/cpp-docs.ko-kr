---
title: "sync_per_container 클래스 | Microsoft Docs"
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
  - "stdext.sync_per_container"
  - "sync_per_container"
  - "stdext::sync_per_container"
  - "allocators/stdext::sync_per_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_container 클래스"
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sync_per_container 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes a [synchronization filter](../standard-library/allocators-header.md) that provides a separate cache object for each allocator object.  
  
## 구문  
  
```  
template <class Cache> class sync_per_container  
    : public Cache  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Cache`|The type of cache associated with the synchronization filter.  This can be [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md), or [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[equals](../Topic/sync_per_container::equals.md)|Compares two caches for equality.|  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)