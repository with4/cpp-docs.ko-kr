---
title: "allocator_fixed_size 클래스 | Microsoft Docs"
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
  - "allocators/stdext::allocators::allocator_fixed_size"
  - "allocators::allocator_fixed_size"
  - "allocators/stdext::allocator_fixed_size"
  - "allocator_fixed_size"
  - "stdext::allocators::allocator_fixed_size"
  - "allocators.allocator_fixed_size"
  - "stdext.allocators.allocator_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_fixed_size 클래스"
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_fixed_size 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an object that manages storage allocation and freeing for objects of type `Type` using a cache of type [cache\_freelist](../standard-library/cache-freelist-class.md) with a length managed by [max\_fixed\_size](../standard-library/max-fixed-size-class.md).  
  
## 구문  
  
```  
template <class Type>  
    class allocator_fixed_size;  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Type`|The type of elements allocated by the allocator.|  
  
## 설명  
 The [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) macro passes this class as the `name` parameter in the following statement: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)