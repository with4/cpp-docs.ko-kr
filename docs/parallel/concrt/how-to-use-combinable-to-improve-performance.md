---
title: "방법: combinable을 사용하여 성능 개선 | Microsoft Docs"
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
  - "combinable 클래스, 예제"
  - "combinable로 병렬 성능 향상[동시성 런타임]"
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: combinable을 사용하여 성능 개선
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 사용하여 [std::array](../../standard-library/array-class-stl.md) 개체에서 소수의 합계를 계산하는 방법을 보여 줍니다.  `combinable` 클래스는 공유 상태를 제거하여 성능을 향상시킵니다.  
  
> [!TIP]
>  경우에 따라서는 병렬 맵 \([concurrency::parallel\_transform](../Topic/parallel_transform%20Function.md)\)과 감소 \([동시성:: parallel\_reduce](../Topic/parallel_reduce%20Function.md)\)를 통해  `combinable` 를 넘는 성능 향상을 제공할 수 있습니다.  매핑 과 작업을 줄여 같은 결과를 생성하는 예제를 보려면, [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 [std::accumulate](../Topic/accumulate.md) 함수를 사용하여 배열에서 소수 요소의 합계를 계산합니다.  이 예제에서 `a`는 `array` 개체이고 `is_prime` 함수는 입력 값이 소수인지 여부를 확인합니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## 예제  
 다음 예제에서는 이전 예제를 병렬화하는 간단한 방법을 보여 줍니다.  이 예제에서는 [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘을 사용하여 배열을 병렬로 처리하고 [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) 개체를 사용하여 `prime_sum` 변수에 대한 액세스를 동기화합니다.  공유 리소스를 사용할 수 있을 때까지 각 스레드가 기다려야 하므로 이 예제를 확장하지 않습니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## 예제  
 다음 예제에서는 `combinable` 개체를 사용하여 이전 예제의 성능을 향상시킵니다.  이 예제에서는 동기화 개체를 사용할 필요가 없으며 `combinable` 개체를 사용하여 각 스레드에서 개별적으로 작업을 수행할 수 있으므로 확장됩니다.  
  
 일반적으로 `combinable` 개체는 두 단계로 사용됩니다.  먼저 작업을 병렬로 수행하여 세분화된 일련의 계산을 만듭니다.  그런 다음 계산을 최종 결과로 결합하거나 줄입니다.  이 예제에서는 [concurrency::combinable::local](../Topic/combinable::local%20Method.md) 메서드를 사용하여 로컬 합계에 대한 참조를 가져옵니다.  그런 다음 [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) 메서드 및 [std::plus](../../standard-library/plus-struct.md) 개체를 사용하여 로컬 계산을 최종 결과로 결합합니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## 예제  
 다음 전체 예제에서는 소수의 합계를 연속 및 병렬 방식으로 모두 계산합니다.  또한 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.  
  
  **1709600813**  
**직렬 시간: 6178 ms**  
**1709600813**  
**병렬 시간: 1638 ms**   
## 코드 컴파일  
 코드를 컴파일하려면 코드를 복사한 다음, Visual Studio 프로젝트 또는 `parallel-sum-of-primes.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-sum\-of\-primes.cpp**  
  
## 강력한 프로그래밍  
 매핑과 작업을 줄여 동일한 결과 생성하는 예제를 보려면  [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 확인하십시오.  
  
## 참고 항목  
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)   
 [critical\_section 클래스](../../parallel/concrt/reference/critical-section-class.md)