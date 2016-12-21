---
title: "allocator_unbounded 클래스 | Microsoft Docs"
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
  - "stdext::allocators::allocator_unbounded"
  - "allocator_unbounded"
  - "allocators/stdext::allocator_unbounded"
  - "allocators::allocator_unbounded"
  - "allocators/stdext::allocators::allocator_unbounded"
  - "allocators.allocator_unbounded"
  - "stdext.allocators.allocator_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_unbounded 클래스"
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_unbounded 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an object that manages storage allocation and freeing for objects of type `Type` using a cache of type [cache\_freelist](../standard-library/cache-freelist-class.md) with a length managed by [max\_unbounded](../standard-library/max-unbounded-class.md).  
  
## 구문  
  
```  
template <class Type>  
    class allocator_unbounded;  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Type`|The type of elements allocated by the allocator.|  
  
## 설명  
 The [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) macro passes this class as the `name` parameter in the following statement: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)