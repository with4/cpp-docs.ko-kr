---
title: "방법: 동시성 런타임을 사용하기 위해 OpenMP parallel for 루프 변환 | Microsoft Docs"
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
  - "OpenMP에서 동시성 런타임으로 변환, parallel for 루프"
  - "OpenMP에서 동시성 런타임으로 변환, 병렬 루프"
  - "parallel for 루프, OpenMP에서 동시성 런타임으로 변환"
  - "병렬 루프, OpenMP에서 동시성 런타임으로 변환"
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: 동시성 런타임을 사용하기 위해 OpenMP parallel for 루프 변환
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) 및 [for](../../parallel/openmp/reference/for-openmp.md) 지시문을 사용하는 기본 루프를 동시성 런타임 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘을 사용하도록 변환하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 OpenMP 및 동시성 런타임을 사용하여 임의의 값 배열에 있는 소수 계수를 계산합니다.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **OpenMP를 사용하여...**  
**107254 소수를 찾을 수 있습니다.**  
**\[동시성 런타임\] 사용**  
**107254 소수를 찾을 수 있습니다.** `parallel_for` 알고리즘 및 OpenMP 3.0에서는 부호 있는 정수 형식 또는 부호 없는 정수 형식을 인덱스 형식으로 사용할 수 있습니다.  `parallel_for` 알고리즘에서도 지정된 범위가 부호 있는 형식을 오버플로하지 않는지 확인합니다.  OpenMP 버전 2.0 및 2.5에서는 부호 있는 정수 인덱스 형식만 사용할 수 있습니다.  또한 OpenMP에서는 인덱스 범위의 유효성을 검사하지 않습니다.  
  
 동시성 런타임을 사용하는 이 예제 버전에서는 [atomic](../../parallel/openmp/reference/atomic.md) 지시문 대신 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 개체를 사용하여, 동기화할 필요 없이 카운터 값을 증가시킵니다.  
  
 `parallel_for` 및 기타 병렬 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  `combinable` 클래스에 대한 자세한 내용은 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)를 참조하십시오.  
  
## 예제  
 이 예제에서는 네이티브 배열 대신 [std::array](../../standard-library/array-class-stl.md) 개체에서 동작하도록 이전 예제를 수정합니다.  OpenMP 버전 2.0 및 2.5에서는 `parallel` `for` 구문에 부호 있는 정수 인덱스 형식만 사용할 수 있으므로 반복기를 사용하여 STL\(표준 템플릿 라이브러리\) 컨테이너 요소에 병렬로 액세스할 수 없습니다.  PPL\(병렬 패턴 라이브러리\)은 [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘을 제공하므로 STL에서 제공하는 것과 같은 작업을 반복적 컨테이너에서 병렬로 수행할 수 있습니다.  이 알고리즘은 `parallel_for` 알고리즘에서 사용하는 것과 같은 분할 논리를 사용합니다.  `parallel_for_each` 알고리즘은 `parallel_for_each` 알고리즘이 동시에 작업을 실행한다는 점을 제외하고는 STL [std::for\_each](../Topic/for_each.md) 알고리즘과 비슷합니다.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-count-primes.cpp` 파일에 붙여 넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-count\-primes.cpp**  
  
## 참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)