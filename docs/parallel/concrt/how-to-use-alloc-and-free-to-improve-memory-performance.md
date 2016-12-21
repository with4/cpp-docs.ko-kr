---
title: "방법: Alloc 및 Free를 사용하여 메모리 성능 개선 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Alloc 및 Free 사용[동시성 런타임]"
  - "Alloc 및 Free 사용[동시성 런타임]"
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Alloc 및 Free를 사용하여 메모리 성능 개선
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 [concurrency::Alloc](../Topic/Alloc%20Function.md) 및 [concurrency::Free](../Topic/Free%20Function.md) 함수를 사용하여 메모리 성능을 향상시키는 방법을 보여 줍니다.  여기에서는 각각 `new` 및 `delete` 연산자를 지정하는 세 가지 다른 형식에 대해 병렬로 배열 요소의 순서를 바꾸는 데 필요한 시간을 비교합니다.  
  
 `Alloc` 및 `Free` 함수는 여러 스레드에서 `Alloc`과 `Free`를 둘 다 자주 호출할 때 가장 유용합니다.  런타임은 각 스레드를 위해 별도의 메모리 캐시를 보유하므로 런타임에서는 잠금 또는 메모리 차단을 사용하지 않아도 메모리를 관리할 수 있습니다.  
  
## 예제  
 다음 예제에서는 각각 `new` 및 `delete` 연산자를 지정하는 세 가지 형식을 보여 줍니다.  `new_delete` 클래스는 전역 `new` 및 `delete` 연산자를 사용하고, `malloc_free` 클래스는 C 런타임의 [malloc](../../c-runtime-library/reference/malloc.md) 및 [free](../../c-runtime-library/reference/free.md) 함수를 사용하고, `Alloc_Free` 클래스는 동시성 런타임의 `Alloc` 및 `Free` 함수를 사용합니다.  
  
 [!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]  
  
## 예제  
 다음 예제에서는 `swap` 및 `reverse_array` 함수를 보여 줍니다.  `swap` 함수는 배열에서 지정된 인덱스에 있는 콘텐츠를 교환합니다.  이 함수는 임시 변수를 위해 힙에서 메모리를 할당합니다.  `reverse_array` 함수는 큰 배열을 만들고, 이 배열의 순서를 병렬로 여러 번 바꾸는 데 필요한 시간을 계산합니다.  
  
 [!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]  
  
## 예제  
 다음 예제에서는 `wmain` 함수를 보여 줍니다. 이 함수는 각각 서로 다른 메모리 할당 체계를 사용하는 `new_delete`, `malloc_free` 및 `Alloc_Free` 형식에서 `reverse_array` 함수를 사용하는 데 필요한 시간을 계산합니다.  
  
 [!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]  
  
## 예제  
 다음은 완성된 예제입니다.  
  
 [!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/CPP/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]  
  
 프로세서가 4개인 컴퓨터에 대해 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **2031 ms 사용하여 생성\/삭제 했습니다.**  
**1672 ms malloc\/해제 했습니다.**  
**656 ms Alloc\/해제 했습니다.** `Alloc` 및 `Free` 함수는 여러 스레드에서 메모리 블록을 자주 할당하고 해제하기 위해 최적화되어 있으므로 이 예제에서는 `Alloc` 및 `Free` 함수를 사용하는 형식의 메모리 성능이 가장 좋습니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `allocators.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc allocators.cpp**  
  
## 참고 항목  
 [메모리 관리 함수](../../parallel/concrt/memory-management-functions.md)   
 [Alloc 함수](../Topic/Alloc%20Function.md)   
 [Free 함수](../Topic/Free%20Function.md)