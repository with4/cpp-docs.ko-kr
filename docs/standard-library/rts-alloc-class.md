---
title: "rts_alloc 클래스 | Microsoft Docs"
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
  - "stdext::rts_alloc"
  - "allocators/stdext::rts_alloc"
  - "rts_alloc"
  - "stdext.rts_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rts_alloc 클래스"
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rts_alloc 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

rts\_alloc 템플릿 클래스는 캐시 인스턴스의 배열을 보유하고 컴파일 시간 대신 런타임에 할당 및 할당 취소에 사용할 인스턴스를 결정하는 [필터](../standard-library/allocators-header.md)에 대해 설명합니다.  
  
## 구문  
  
```  
template <class Cache> class rts_alloc  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Cache`|배열에 포함된 캐시 인스턴스의 형식입니다.  [cache\_chunklist 클래스](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) 또는 [cache\_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|  
  
## 설명  
 이 템플릿 클래스는 여러 개의 블록 할당자 인스턴스를 보유하고 컴파일 시간 대신 런타임에 할당 또는 할당 취소에 사용할 인스턴스를 결정합니다.  rebind를 컴파일할 수 없는 컴파일러에서 사용됩니다.  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/rts_alloc::allocate.md)|메모리 블록을 할당합니다.|  
|[deallocate](../Topic/rts_alloc::deallocate.md)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[다음과 같은 경우](../Topic/rts_alloc::equals.md)|두 캐시가 같은지 비교합니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)   
 [\<allocators\>](../standard-library/allocators-header.md)