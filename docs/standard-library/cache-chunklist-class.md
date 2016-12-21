---
title: "cache_chunklist 클래스 | Microsoft Docs"
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
  - "allocators/stdext::cache_chunklist"
  - "stdext.cache_chunklist"
  - "stdext::cache_chunklist"
  - "cache_chunklist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_chunklist 클래스"
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cache_chunklist 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Defines a [block allocator](../standard-library/allocators-header.md) that allocates and deallocates memory blocks of a single size.  
  
## 구문  
  
```  
template <std::size_t Sz, std::size_t Nelts = 20> class cache_chunklist  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Sz`|The number of elements in the array to be allocated.|  
  
## 설명  
 This template class uses `operator new` to allocate chunks of raw memory, suballocating blocks to allocate storage for a memory block when needed; it stores deallocated memory blocks in a separate free list for each chunk, and uses `operator delete` to deallocate a chunk when none of its memory blocks is in use.  
  
 Each memory block holds `Sz` bytes of usable memory and a pointer to the chunk that it belongs to.  Each chunk holds `Nelts` memory blocks, three pointers, an int and the data that `operator new` and `operator delete` require.  
  
### 생성자  
  
|||  
|-|-|  
|[cache\_chunklist](../Topic/cache_chunklist::cache_chunklist.md)|'`cache_chunklist`' 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[allocate](../Topic/cache_chunklist::allocate.md)|Allocates a block of memory.|  
|[deallocate](../Topic/cache_chunklist::deallocate.md)|Frees a specified number of objects from storage beginning at a specified position.|  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)