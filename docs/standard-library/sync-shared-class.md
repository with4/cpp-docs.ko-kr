---
title: "sync_shared 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sync_shared"
  - "allocators/stdext::sync_shared"
  - "stdext.sync_shared"
  - "stdext::sync_shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_shared 클래스"
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sync_shared 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

뮤텍스를 사용하여 모든 할당자가 공유하는 캐시 개체에 대한 액세스를 제어하는 [동기화 필터](../standard-library/allocators-header.md)를 설명합니다.  
  
## 구문  
  
```  
template <class Cache> class sync_shared  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Cache`|동기화 필터와 연결된 캐시 형식입니다.[cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) 또는 [cache\_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/sync_shared::allocate.md)|메모리 블록을 할당합니다.|  
|[deallocate](../Topic/sync_shared::deallocate.md)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[다음과 같은 경우](../Topic/sync_shared::equals.md)|두 캐시가 같은지 비교합니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)