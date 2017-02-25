---
title: "max_fixed_size 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators/stdext::max_fixed_size"
  - "max_fixed_size"
  - "stdext::max_fixed_size"
  - "stdext.max_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_fixed_size 클래스"
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# max_fixed_size 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Describes a [max class](../standard-library/allocators-header.md) object that limits a [freelist](../standard-library/freelist-class.md) object to a fixed maximum length.  
  
## 구문  
  
```  
template <std::size_t Max> class max_fixed_size  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Max`|The max class that determines the maximum number of elements to store in the `freelist`.|  
  
### 생성자  
  
|||  
|-|-|  
|[max\_fixed\_size](../Topic/max_fixed_size::max_fixed_size.md)|'`max_fixed_size`' 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[allocated](../Topic/max_fixed_size::allocated.md)|Increments the count of allocated memory blocks.|  
|[deallocated](../Topic/max_fixed_size::deallocated.md)|Decrements the count of allocated memory blocks.|  
|[전체](../Topic/max_fixed_size::full.md)|Returns a value that specifies whether more memory blocks should be added to the free list.|  
|[released](../Topic/max_fixed_size::released.md)|Decrements the count of memory blocks on the free list.|  
|[saved](../Topic/max_fixed_size::saved.md)|Increments the count of memory blocks on the free list.|  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)