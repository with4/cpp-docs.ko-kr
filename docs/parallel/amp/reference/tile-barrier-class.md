---
title: "tile_barrier 클래스 | Microsoft Docs"
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
  - "amp/Concurrency::tile_barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tile_barrier 클래스"
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: 17
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# tile_barrier 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`wait` 메서드를 사용하여 스레드 그룹\(타일\)에서 실행 중인 스레드 실행을 동기화합니다.  런타임만이 이 클래스를 인스턴스화할 수 있습니다.  
  
## 구문  
  
```  
class tile_barrier;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[tile\_barrier::tile\_barrier 생성자](../Topic/tile_barrier::tile_barrier%20Constructor.md)|`tile_barrier` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[tile\_barrier::wait 메서드](../Topic/tile_barrier::wait%20Method.md)|타일에 있는 모든 스레드가 대기를 완료할 때까지 스레드 그룹\(타일\)에 있는 모든 스레드의 실행을 중지하도록 지시합니다.|  
|[tile\_barrier::wait\_with\_all\_memory\_fence 메서드](../Topic/tile_barrier::wait_with_all_memory_fence%20Method.md)|모든 메모리 액세스가 완료되고 타일에 있는 모든 스레드가 이 호출에 도달할 때까지 타일에 있는 모든 스레드의 실행을 차단합니다.|  
|[tile\_barrier::wait\_with\_global\_memory\_fence 메서드](../Topic/tile_barrier::wait_with_global_memory_fence%20Method.md)|모든 전역 메모리 액세스가 완료되고 타일에 있는 모든 스레드가 이 호출에 도달할 때까지 타일에 있는 모든 스레드의 실행을 차단합니다.|  
|[tile\_barrier::wait\_with\_tile\_static\_memory\_fence 메서드](../Topic/tile_barrier::wait_with_tile_static_memory_fence%20Method.md)|모든 `tile_static` 메모리 액세스가 완료되고 타일에 있는 모든 스레드가 이 호출에 도달할 때까지 타일에 있는 모든 스레드의 실행을 차단합니다.|  
  
## 상속 계층  
 `tile_barrier`  
  
## 요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)