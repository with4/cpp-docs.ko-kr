---
title: "방법: for 루프 동시성 런타임을 사용 하기 위해 OpenMP parallel 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a27e07884b4ada54f694136ea2fbca474c9d214d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>방법: 동시성 런타임을 사용하기 위해 OpenMP parallel for 루프 변환

OpenMP를 사용 하는 기본 루프를 변환 하는 방법을 보여 주는이 예제 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) 및 [에 대 한](../../parallel/openmp/reference/for-openmp.md) 동시성 런타임을 사용 하는 지시문 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘입니다.  
  
## <a name="example"></a>예  
 이 예제에서는 OpenMP와 동시성 런타임을 모두을 사용 하 여 난수 값의 배열에서 소수의 수를 계산 합니다.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Using OpenMP...  
found 107254 prime numbers.  
Using the Concurrency Runtime...  
found 107254 prime numbers.  
```  
  
 `parallel_for` 알고리즘과 OpenMP 3.0 허용 인덱스 형식이 부호 있는 정수 형식 또는 부호 없는 정수 계열 형식 이어야 합니다. `parallel_for` 알고리즘도 하면 지정된 된 범위 부호 있는 형식이 오버플로 하지 않습니다. OpenMP 2.0 버전을 2.5 부호 있는 정수 인덱스 유형의 경우에 허용합니다. 또한 OpenMP 인덱스 범위를 확인 하지 않습니다.  
  
 동시성 런타임을 사용 하는이 예제의 버전 또한 사용 하 여 한 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 대신 개체는 [원자성](../../parallel/openmp/reference/atomic.md) 필요 없이 카운터 값이 증가 하는 지시문 동기화 합니다.  
  
 에 대 한 자세한 내용은 `parallel_for` 오류 코드 및 기타 병렬 알고리즘을 참조 하십시오. [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다. 에 대 한 자세한 내용은 `combinable` 클래스를 참조 하십시오. [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다.  
  
## <a name="example"></a>예  

 이 예에서는 예제를 수정 이전에 [std:: array](../../standard-library/array-class-stl.md) 개체 대신 네이티브 배열입니다. OpenMP 2.0 버전을 2.5 가능 하 게 정수 인덱스 형식에만 서명 때문에 `parallel_for` 구문에 동시에 c + + 표준 라이브러리 컨테이너의 요소에 액세스 하려면 반복기를 사용할 수 없습니다. 병렬 패턴 라이브러리 (PPL)은 제공는 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 에서 c + + 표준 라이브러리에서 제공 하는 것과 같은 반복 컨테이너는으로 병렬 작업을 수행 하는 알고리즘입니다. 동일한 분할 논리를 사용 하는 `parallel_for` 알고리즘에서 사용 합니다. `parallel_for_each` 알고리즘에는 c + + 표준 라이브러리와 유사 [for_each](../../standard-library/algorithm-functions.md#for_each) 점을 제외 하 고 알고리즘에서 `parallel_for_each` 알고리즘의 작업을 동시에 실행 합니다.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `concrt-omp-count-primes.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc /openmp concrt-omp-개수-primes.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)

