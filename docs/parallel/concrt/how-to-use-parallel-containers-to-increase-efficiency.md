---
title: "방법: 병렬 컨테이너를 사용하여 효율성 향상 | Microsoft Docs"
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
  - "병렬 컨테이너로 효율성 향상[동시성 런타임]"
  - "concurrent_queue 클래스, 예제"
  - "concurrent_vector 클래스, 예제"
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 병렬 컨테이너를 사용하여 효율성 향상
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 병렬 컨테이너를 사용하여 병렬 방식에 따라 효율적으로 데이터를 저장하고 액세스하는 방법을 보여 줍니다.  
  
 예제 코드에서는 소수와 카마이클 수 집합을 병렬로 계산합니다.  그런 다음 각 카마이클 수에 대해 해당 수의 소인수를 계산합니다.  
  
## 예제  
 다음 예제에서는 입력 값이 소수인지 여부를 확인하는 `is_prime` 함수와 입력 값이 카마이클 수인지 여부를 확인하는 `is_carmichael` 함수를 보여 줍니다.  
  
 [!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]  
  
## 예제  
 다음 예제에서는 `is_prime` 및 `is_carmichael` 함수를 사용하여 소수 및 카마이클 수 집합을 계산합니다.  이 예제에서는 [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) 및 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘을 사용하여 각 집합을 병렬로 계산합니다.  병렬 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
 이 예제에서는 나중에 작업 큐로 사용할 수 있도록 [concurrency::concurrent\_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 개체를 사용하여 카마이클 수의 집합을 저장합니다.  또한 나중에 이 집합을 반복하여 소인수를 찾을 수 있도록 [concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 개체를 사용하여 소수의 집합을 저장합니다.  
  
 [!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]  
  
## 예제  
 다음 예제에서는 나누기 시도\(trial division\)라는 알고리즘을 사용하여 지정된 값의 모든 소인수를 찾는 `prime_factors_of` 함수를 보여 줍니다.  
  
 이 함수는 [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘을 사용하여 소수 컬렉션을 반복합니다.  `concurrent_vector` 개체를 사용하면 병렬 루프에서 소인수를 동시에 결과에 추가할 수 있습니다.  
  
 [!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]  
  
## 예제  
 이 예제에서는 `prime_factors_of` 함수를 호출한 후 소인수를 계산하여 카마이클 수의 큐에서 각 요소를 처리합니다.  여기에서는 작업 그룹을 사용하여 이 작업을 병렬로 수행합니다.  작업 그룹에 대한 자세한 내용은 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)를 참조하십시오.  
  
 이 예제에서는 각 카마이클 수에 소인수가 5개 이상 있는 경우 해당 카마이클 수의 소인수를 출력합니다.  
  
 [!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]  
  
## 예제  
 다음 코드에서는 병렬 컨테이너를 사용하여 카마이클 수의 소인수를 계산하는 전체 예제를 보여 줍니다.  
  
 [!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **9890881의 주요 요인은: 7 11 13 41 241.**  
**825265의 주요 요인은: 5 7 17 19 73.**  
**1050985의 주요 요인은: 5 13 19 23 37.**   
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는`carmichael-primes.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc carmichael\-primes.cpp**  
  
## 참고 항목  
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [concurrent\_vector 클래스](../../parallel/concrt/reference/concurrent-vector-class.md)   
 [concurrent\_queue 클래스](../../parallel/concrt/reference/concurrent-queue-class.md)   
 [parallel\_invoke 함수](../Topic/parallel_invoke%20Function.md)   
 [parallel\_for 함수](../Topic/parallel_for%20Function.md)   
 [task\_group 클래스](../Topic/task_group%20Class.md)