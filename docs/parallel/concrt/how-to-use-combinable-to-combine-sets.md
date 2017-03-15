---
title: "방법: combinable을 사용하여 집합 결합 | Microsoft Docs"
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
  - "combinable을 사용하여 집합 결합[동시성 런타임]"
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: combinable을 사용하여 집합 결합
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 사용하여 소수 집합을 계산하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 소수 집합을 두 번 계산합니다.  각 계산 결과는 [std::bitset](../../standard-library/bitset-class.md) 개체에 저장됩니다.  이 예제에서는 먼저 직렬로 집합을 계산한 후 병렬로 집합을 계산합니다.  또한 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.  
  
 이 예제에서는 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘과 `combinable` 개체를 사용하여 스레드 로컬 집합을 생성합니다.  그런 다음 [concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md) 메서드를 사용하여 스레드 로컬 집합을 최종 집합으로 결합합니다.  
  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.  
  
  **직렬 시간: 312 ms**  
**병렬 시간: 78 ms**   
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `parallel-combine-primes.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-combine\-primes.cpp**  
  
## 참고 항목  
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)   
 [combinable::combine\_each 메서드](../Topic/combinable::combine_each%20Method.md)