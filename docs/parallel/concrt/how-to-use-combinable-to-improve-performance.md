---
title: '방법: combinable 성능 향상을 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3185ee9f7546e6927197d2e3452ea4cf86f9ab5c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-combinable-to-improve-performance"></a>방법: combinable을 사용하여 성능 개선
사용 하는 방법을 보여 주는이 예제는 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스에 있는 숫자의 합계를 계산 하는 [std:: array](../../standard-library/array-class-stl.md) 개체 소수입니다. `combinable` 클래스 공유 상태를 제거 하 여 성능이 향상 됩니다.  
  
> [!TIP]
>  경우에 따라 병렬 매핑 ([concurrency:: parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) 줄이고 ([동시성:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce))를 통해 성능 향상을 제공할 수 `combinable`합니다. 사용 하 여 매핑 및 줄이기 작업이이 예제와 동일한 결과를 생성 하는 예제를 보려면 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 [std:: accumulate](../../standard-library/numeric-functions.md#accumulate) 소수를 배열에 있는 요소의 합계를 계산 하는 함수입니다. 이 예제에서는 `a` 는 `array` 개체 및 `is_prime` 함수는 입력된 값은 소수 있는지 여부를 결정 합니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## <a name="example"></a>예제  

 다음 예제에서는 이전 예제를 병렬화 하는 간단한 방법을 보여 줍니다. 사용 하 여이 예제는 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 배열을 병렬로 처리 하는 알고리즘 및 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 개체에 대 한 액세스를 동기화 하는 `prime_sum` 변수 . 각 스레드가 공유 리소스를 사용할 수 있을 때까지 대기 해야 하기 때문에이 예제를 확장 하지 않습니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `combinable` 이전 예의 성능을 향상 시키기 위해 개체입니다. 이 예제에서는 동기화 개체; 필요를 하지 않습니다. 때문에 확장성이 `combinable` 개체는 작업을 독립적으로 수행 하는 각 스레드를 사용 하면 됩니다.  
  
 A `combinable` 개체는 두 단계에서 주로 사용 됩니다. 먼저 병렬로 작업을 수행 하 여 일련의 세분화 된 계산을 생성 합니다. 다음으로 결합 하거나 줄일는 계산을 최종 결과에. 사용 하 여이 예제는 [concurrency::combinable::local](reference/combinable-class.md#local) 로컬 합계에 대 한 참조를 얻는 메서드를 합니다. 다음 사용 하 여는 [concurrency::combinable::combine](reference/combinable-class.md#combine) 메서드 및 [std:: plus](../../standard-library/plus-struct.md) 로컬 계산 결과 최종 결과로 결합 하는 개체입니다.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## <a name="example"></a>예제  
 다음 전체 예제에서는 직렬 및 병렬로 주요 번호의 합을 계산 합니다. 예제에서는 계산을 모두 수행 하는 데 필요한 시간에 콘솔에 출력 합니다.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 프로세서가 4개인 컴퓨터의 샘플 출력은 다음과 같습니다.  
  
```Output  
1709600813  
serial time: 6178 ms  
 
1709600813  
parallel time: 1638 ms  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `parallel-sum-of-primes.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 병렬-합-의-primes.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 사용 하 여 매핑 및 줄이기 작업 동일한 결과를 생성 하는 예제를 보려면 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)   
 [critical_section 클래스](../../parallel/concrt/reference/critical-section-class.md)
