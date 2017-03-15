---
title: "allocator_variable_size 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators.allocator_variable_size"
  - "allocators::allocator_variable_size"
  - "allocators/stdext::allocator_variable_size"
  - "stdext.allocators.allocator_variable_size"
  - "allocator_variable_size"
  - "allocators/stdext::allocators::allocator_variable_size"
  - "stdext::allocators::allocator_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_variable_size 클래스"
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# allocator_variable_size 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes an object that manages storage allocation and freeing for objects of type `Type` using a cache of type [cache\_freelist](../standard-library/cache-freelist-class.md) with a length managed by [max\_variable\_size](../standard-library/max-variable-size-class.md).  
  
## 구문  
  
```  
template <class Type>  
    class allocator_variable_size;  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Type`|The type of elements allocated by the allocator.|  
  
## 설명  
 The [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) macro passes this class as the `name` parameter in the following statement: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)