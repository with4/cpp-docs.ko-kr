---
title: "cache_freelist 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.cache_freelist"
  - "allocators/stdext::cache_freelist"
  - "stdext::cache_freelist"
  - "cache_freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_freelist 클래스"
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# cache_freelist 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정의 [할당자 차단](../standard-library/allocators-header.md) 할당 하 고 단일 크기의 메모리 블록의 할당을 취소 합니다.  
  
## 구문  
  
```  
template <std::size_t Sz, class Max> class cache_freelist  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Sz`|에 할당할 배열의 요소 수입니다.|  
|`Max`|사용 가능한 목록의 최대 크기를 나타내는 최대 클래스입니다. 이 수 [max\_fixed\_size](../standard-library/max-fixed-size-class.md), [max\_none](../standard-library/max-none-class.md), [max\_unbounded](../standard-library/max-unbounded-class.md), 또는 [max\_variable\_size](../standard-library/max-variable-size-class.md)합니다.|  
  
## 설명  
 Cache\_freelist 템플릿 클래스에는 무료 메모리 블록 크기의 목록을 유지 관리 `Sz`합니다. 사용 가능한 목록 가득 찼을 때 `operator delete` 메모리 할당 해제를 차단 합니다. 사용 가능한 목록 비어 있을 때 `operator new` 새로운 메모리 블록을 할당할 수 있습니다. 가능한 목록의 최대 크기는 최대 클래스에 전달 된 클래스에 의해 결정 된 `Max` 매개 변수입니다.  
  
 각 메모리 블록 보유 `Sz` 사용 가능한 메모리와 데이터의 바이트를 `operator new` 및 `operator delete` 필요 합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[cache\_freelist](../Topic/cache_freelist::cache_freelist.md)|`cache_freelist` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/cache_freelist::allocate.md)|메모리 블록을 할당합니다.|  
|[deallocate](../Topic/cache_freelist::deallocate.md)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)