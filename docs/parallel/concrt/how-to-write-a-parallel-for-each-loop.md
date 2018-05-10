---
title: '방법: parallel_for_each 루프 작성 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68ba40b7d9ea93e73d9d18d3548b0c0f34c6411f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-write-a-parallelforeach-loop"></a>방법: parallel_for_each 루프 작성
사용 하는 방법을 보여 주는이 예제는 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 알고리즘에서 소수의 수를 계산 하는 [std:: array](../../standard-library/array-class-stl.md) 병렬로 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 번 배열에서 소수의 수를 계산 합니다. 이 예제에서는 먼저 사용 하 여는 [for_each](../../standard-library/algorithm-functions.md#for_each) 알고리즘의 수를 연속으로 계산을 합니다. 이 예제에서는 다음 사용 하 여는 `parallel_for_each` 알고리즘을 동시에 동일한 작업을 수행 합니다. 또한 이 예제에서는 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 프로세서가 4개인 컴퓨터의 샘플 출력은 다음과 같습니다.  
  
```Output  
serial version:  
found 17984 prime numbers  
took 6115 ms  
 
parallel version:  
found 17984 prime numbers  
took 1653 ms  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `parallel-count-primes.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 병렬-개수-primes.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 에 전달 하는 람다 식을 `parallel_for_each` 알고리즘에서 사용 하는 `InterlockedIncrement` 함수 카운터를 동시에 증가 하는 루프의 병렬 반복 사용할 수 있도록 합니다. 와 같은 함수를 사용 하는 경우 `InterlockedIncrement` 공유 리소스에 대 한 액세스를 동기화 하려면 코드에서 성능 병목 상태를 제공할 수 있습니다. 예를 들어 잠금 없는 동기화 메커니즘을 사용할 수 있습니다, [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 공유 리소스에 대 한 동시 액세스를 제거 하기 위해 클래스입니다. 사용 하는 예제에 대 한는 `combinable` 이런이 방식으로 클래스를 참조 하십시오. [하는 방법: combinable 성능 향상을 사용 하 여](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for_each 함수](reference/concurrency-namespace-functions.md#parallel_for_each)


