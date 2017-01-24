---
title: "방법: parallel_for_each 루프 작성 | Microsoft Docs"
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
  - "parallel_for_each 루프 작성[동시성 런타임]"
  - "parallel_for_each 함수, 예제"
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: parallel_for_each 루프 작성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘을 사용하여 [std::array](../../standard-library/array-class-stl.md) 개체에서 소수 개수를 병렬로 계산하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 배열에서 소수의 수를 두 번 계산합니다.  이 예제에서는 먼저 [std::for\_each](../Topic/for_each.md) 알고리즘을 사용하여 소수 개수를 연속으로 계산합니다.  그런 다음 `parallel_for_each` 알고리즘을 사용하여 같은 작업을 병렬로 수행합니다.  또한 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.  
  
  **직렬 버전:**  
**17984 소수를 찾을 수 있습니다.**  
**6115 ms 걸렸습니다.**  
**병렬 버전**  
**17984 소수를 찾을 수 있습니다.**  
**1653 ms 걸렸습니다.**   
## 코드 컴파일  
 코드를 컴파일하려면 코드를 복사한 다음, Visual Studio 프로젝트 또는 `parallel-count-primes.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-count\-primes.cpp**  
  
## 강력한 프로그래밍  
 이 예제에서 `parallel_for_each` 알고리즘에 전달하는 람다 식은 `InterlockedIncrement` 함수를 사용하여 병렬 루프 반복에서 카운터를 동시에 증가시킬 수 있도록 합니다.  `InterlockedIncrement`와 같은 함수를 사용하여 공유 리소스에 대한 액세스를 동기화하는 경우 코드에 성능 병목 현상을 나타낼 수 있습니다.  [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 클래스와 같이 잠금이 필요 없는 동기화 메커니즘을 사용하면 공유 리소스에 대한 동시 액세스를 제거할 수 있습니다.  이 방법으로 `combinable` 클래스를 사용하는 예제를 보려면 [방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)을 참조하십시오.  
  
## 참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for\_each 함수](../Topic/parallel_for_each%20Function.md)