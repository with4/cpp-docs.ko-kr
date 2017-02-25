---
title: "freelist 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::freelist"
  - "freelist"
  - "stdext.freelist"
  - "allocators/stdext::freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "freelist 클래스"
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# freelist 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Manages a list of memory blocks.  
  
## 구문  
  
```  
template <std::size_t Sz, class Max> class freelist  
    : public Max  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`Sz`|The number of elements in the array to be allocated.|  
|`Max`|The max class representing the maximum number of elements to be stored in the free list.  The max class can be [max\_none](../standard-library/max-none-class.md), [max\_unbounded](../standard-library/max-unbounded-class.md), [max\_fixed\_size](../standard-library/max-fixed-size-class.md), or [max\_variable\_size](../standard-library/max-variable-size-class.md).|  
  
## 설명  
 This template class manages a list of memory blocks of size `Sz` with the maximum length of the list determined by the max class passed in `Max`.  
  
### 생성자  
  
|||  
|-|-|  
|[freelist](../Topic/freelist::freelist.md)|'`freelist`' 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[pop](../Topic/freelist::pop.md)|Removes the first memory block from the free list.|  
|[push](../Topic/freelist::push.md)|Adds a memory block to the list.|  
  
## 요구 사항  
 **Header:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)