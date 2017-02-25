---
title: "메모리 관리 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 관리 함수[동시성 런타임]"
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 메모리 관리 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 동시성 런타임에서 메모리를 동시에 할당하고 해제할 수 있도록 제공하는 메모리 관리 함수에 대해 설명합니다.  
  
> [!TIP]
>  동시성 런타임에서 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다.  작업 스케줄러를 사용하면 응용 프로그램의 성능을 세부적으로 조정할 수 있으므로 동시성 런타임을 처음 사용하는 경우 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)에서 시작하는 것이 좋습니다.  
  
 동시성 런타임에서는 메모리 블록을 동시에 할당하고 해제하기 위해 최적화된 두 개의 메모리 관리 함수를 제공합니다.  [concurrency::Alloc](../Topic/Alloc%20Function.md) 함수는 지정된 크기를 사용하여 메모리 블록을 할당합니다.  [concurrency::Free](../Topic/Free%20Function.md) 함수는 `Alloc`로 할당된 메모리를 해제합니다.  
  
> [!NOTE]
>  `Alloc` 및 `Free` 함수는 서로 의존합니다.  `Free` 함수는 `Alloc` 함수를 사용하여 할당하는 메모리를 해제하는 경우에만 사용합니다.  또한 `Alloc` 함수를 사용하여 메모리를 할당하는 경우 해당 메모리를 해제하려면 `Free` 함수만 사용해야 합니다.  
  
 다양한 스레드 또는 작업에서 고정된 할당 크기 집합을 할당하거나 해제하는 경우 `Alloc` 및 `Free` 함수를 사용해야 합니다.  동시성 런타임은 C 런타임 힙에서 할당 메모리를 캐시합니다.  동시성 런타임은 각 실행 스레드를 위해 별도의 메모리 캐시를 보유하므로 런타임에서 잠금 또는 메모리 차단을 사용하지 않아도 메모리를 관리할 수 있습니다.  메모리 캐시에 자주 액세스하면 `Alloc` 및 `Free` 함수를 사용할 때 응용 프로그램에서 이점을 더 많이 얻을 수 있습니다.  예를 들어 `Alloc` 함수와 `Free` 함수를 둘 다 자주 호출하는 스레드는 주로 `Alloc` 또는 `Free` 함수를 호출하는 스레드보다 더 많은 이점을 얻습니다.  
  
> [!NOTE]
>  이러한 메모리 관리 함수를 사용하고 응용 프로그램에서 많은 양의 메모리를 사용하는 경우에는 응용 프로그램의 메모리 부족 상태가 예상보다 빨리 올 수도 있습니다.  한 스레드에서 캐시되는 메모리 블록은 다른 스레드에서 사용할 수 없으므로 한 스레드에 많은 양의 메모리가 포함되어 있으면 해당 메모리를 사용할 수 없습니다.  
  
## 예제  
 `Alloc` 및 `Free` 함수를 사용하여 메모리 성능을 향상시키는 예제를 보려면 [방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)을 참조하십시오.  
  
## 참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)