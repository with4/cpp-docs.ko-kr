---
title: "allocator_newdel 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators::allocator_newdel"
  - "allocators/stdext::allocators::allocator_newdel"
  - "stdext.allocators.allocator_newdel"
  - "allocators/stdext::allocator_newdel"
  - "allocator_newdel"
  - "stdext::allocators::allocator_newdel"
  - "allocators.allocator_newdel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_newdel 클래스"
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# allocator_newdel 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implements an allocator that uses `operator delete` to deallocate a memory block and `operator new` to allocate a memory block.  
  
## 구문  
  
```  
template <class Type>  
    class allocator_newdel;  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Type`|The type of elements allocated by the allocator.|  
  
## 설명  
 The [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) macro passes this class as the `name` parameter in the following statement: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)