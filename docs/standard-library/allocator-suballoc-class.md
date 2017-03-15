---
title: "allocator_suballoc 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators::allocator_suballoc"
  - "allocator_suballoc"
  - "stdext.allocators.allocator_suballoc"
  - "allocators/stdext::allocators::allocator_suballoc"
  - "stdext::allocators::allocator_suballoc"
  - "allocators/stdext::allocator_suballoc"
  - "allocators.allocator_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_suballoc 클래스"
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# allocator_suballoc 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

저장소 할당 및 형식의 개체에 대 한 해제를 관리 하는 개체에 설명 `Type` 형식의 캐시를 사용 하 여 [cache\_suballoc](../standard-library/cache-suballoc-class.md)합니다.  
  
## 구문  
  
```  
template <class Type>  
    class allocator_suballoc;  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Type`|할당자에 의해 할당된 요소 형식입니다.|  
  
## 설명  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) 매크로 전달 것 처럼이 클래스는 `name` 다음 문에서 매개 변수: `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)