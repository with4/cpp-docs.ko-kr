---
title: "메모리 관리 기능 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 309080a807a1325bbf921657a152cff60e87cb95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-functions"></a>메모리 관리 함수
이 문서에서는 동시성 런타임에서 메모리 할당과 해제를 동시에 수 있도록 제공 하는 메모리 관리 함수를 설명 합니다.  
  
> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다. 작업 스케줄러를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 때문에로 시작 하는 것이 좋습니다는 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 하려는 경우 동시성 런타임으로 새입니다.  
  
 동시성 런타임은 할당 하 고 메모리 블록을 동시에 해제에 대 한 최적화 된 두 메모리 관리 함수를 제공 합니다. [concurrency:: alloc](reference/concurrency-namespace-functions.md#alloc) 함수는 지정된 된 크기를 사용 하 여 메모리 블록을 할당 합니다. [concurrency:: free](reference/concurrency-namespace-functions.md#free) 함수에 의해 할당 된 메모리를 해제 `Alloc`합니다.  
  
> [!NOTE]
>  `Alloc` 및 `Free` 함수 서로에 의존 합니다. 사용 하 여는 `Free` 만 사용 하 여 할당 하는 메모리를 해제 하는 함수는 `Alloc` 함수입니다. 또한 사용 하는 경우는 `Alloc` 메모리를 할당만 사용 하는 함수는 `Free` 함수를 해당 메모리를 해제 합니다.  
  
 사용 하 여는 `Alloc` 및 `Free` 할당 하 고 서로 다른 스레드 또는 작업에서 할당 크기의 고정된 된 집합을 해제 하는 경우의 작동 합니다. 동시성 런타임은 C 런타임 힙에서 할당 하는 메모리를 캐시 합니다. 각 실행 스레드;에 대 한 별도 메모리 캐시를 보유 하는 동시성 런타임 따라서 런타임에 잠금 또는 메모리 장벽을 사용 하지 않고 메모리를 관리합니다. 응용 프로그램에서 이점을 `Alloc` 및 `Free` 메모리 내 캐시에 더 자주 액세스할 때 작동 합니다. 자주 둘 다를 호출 하는 스레드는 예를 들어 `Alloc` 및 `Free` 주로 호출 하는 스레드 보다 더 많은 이점을 얻습니다 `Alloc` 또는 `Free`합니다.  
  
> [!NOTE]
>  이러한 메모리 관리 함수를 사용 하 고 프로그램 응용 프로그램 사용 하 여 많은 응용 프로그램 메모리를 입력할 수 있습니다 때 메모리 부족 상태 예상 보다 빨리 합니다. 한 스레드에서 캐시 되는 메모리 블록의 한 스레드가 많은 메모리를 보유 하는 경우 다른 스레드를 사용할 수 없기 때문 해당 메모리를 사용할 수 없습니다.  
  
## <a name="example"></a>예  
 사용 하는 예제에 대 한는 `Alloc` 및 `Free` 메모리 성능을 향상 시키는 함수 참조 [하는 방법: 사용 Alloc 및 Free 메모리 성능 개선에](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)

