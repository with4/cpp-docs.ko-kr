---
title: "cache_suballoc 클래스 | Microsoft Docs"
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
  - "stdext.cache_suballoc"
  - "allocators/stdext::cache_suballoc"
  - "stdext::cache_suballoc"
  - "cache_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_suballoc 클래스"
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cache_suballoc 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정의 [할당자 차단](../standard-library/allocators-header.md) 할당 하 고 단일 크기의 메모리 블록의 할당을 취소 합니다.  
  
## 구문  
  
```  
template <std::size_t Sz, size_t Nelts = 20> class cache_suballoc  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Sz`|에 할당할 배열의 요소 수입니다.|  
  
## 설명  
 바인딩되지 않은 길이와 사용 가능한 목록에 할당 취소 된 메모리 블록을 저장 하는 cache\_suballoc 템플릿 클래스를 사용 하 여 `freelist<sizeof(Type), max_unbounded>`, 메모리 블록을 사용 하 여 할당 보다 큰 청크에서 suballocates 및 `operator new` 가능한 목록이 비어 있을 때.  
  
 각 청크를 보유 `Sz * Nelts` 사용 가능한 메모리와 데이터의 바이트를 `operator new` 및 `operator delete` 필요 합니다. 할당 된 청크 해제 되지 않습니다.  
  
### 생성자  
  
|||  
|-|-|  
|[cache\_suballoc](../Topic/cache_suballoc::cache_suballoc.md)|`cache_suballoc` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[할당](../Topic/cache_suballoc::allocate.md)|메모리 블록을 할당합니다.|  
|[deallocate](../Topic/cache_suballoc::deallocate.md)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)