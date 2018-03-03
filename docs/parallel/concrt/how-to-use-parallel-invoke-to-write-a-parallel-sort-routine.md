---
title: "방법: parallel_invoke를 사용 하 여 병렬 정렬 루틴 작성 | Microsoft Docs"
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
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff14294236efc26b83d31ad185dc1cfd6329dbe9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>방법: parallel_invoke를 사용하여 병렬 정렬 루틴 작성
이 문서에 사용 하는 방법에 설명 된 [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) 바 이토 닉 정렬 알고리즘의 성능을 향상 시키기 위해 알고리즘입니다. 바 이토 닉 정렬 알고리즘 재귀적으로 입력된 시퀀스를 정렬 된 파티션을 더 작은 나눕니다. 바 이토 닉 정렬 알고리즘은 각 파티션 작업은 다른 모든 작업과 독립적 이므로 병렬로 실행할 수 있습니다.  
  
 바 이토 닉 정렬의 예는 한 *정렬 네트워크* 입력된 시퀀스의 모든 조합을 정렬 하는,이 예에서는 길이가 2의 거듭제곱 시퀀스를 정렬 합니다.  
  
> [!NOTE]
>  이 예제에서는 이해를 돕기 위해 병렬 정렬 루틴을 사용합니다. PPL에서 제공 하는 기본 제공 정렬 알고리즘을 사용할 수 있습니다: [concurrency:: parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency:: parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), 및 [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort)합니다. 자세한 내용은 참조 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
##  <a name="top"></a> 섹션  
 이 문서에서는 다음 작업을 설명합니다.  
  
- [직렬로 바 이토 닉 정렬 수행](#serial)  
  
- [병렬로 수행 바 이토 닉 정렬 parallel_invoke를 사용 하 여](#parallel)  
  
##  <a name="serial"></a>직렬로 바 이토 닉 정렬 수행  
 다음 예제에서는 바 이토 닉 정렬 알고리즘의 직렬 버전을 나타냅니다. `bitonic_sort` 함수는 시퀀스를 두 개의 파티션으로 나누고 이러한 파티션을 서로 반대 방향으로 정렬 한 후 결과 병합 합니다. 각 파티션을 정렬에 두 번 재귀적으로이 함수가 자신을 호출 합니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="parallel"></a>병렬로 수행 바 이토 닉 정렬 parallel_invoke를 사용 하 여  
 이 섹션에서는 사용 하는 방법을 설명는 `parallel_invoke` 병렬로 바 이토 닉 정렬 알고리즘을 수행 하는 알고리즘입니다.  
  
### <a name="procedures"></a>절차  
  
##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>병렬로 바 이토 닉 정렬 알고리즘을 수행 하려면  
  
1.  추가 `#include` 헤더 파일 ppl.h에 대 한 지시문입니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  추가 `using` 에 대 한 지시문은 `concurrency` 네임 스페이스입니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  호출 하는 새 함수를 만들 `parallel_bitonic_mege`, 사용 하는 `parallel_invoke` 알고리즘을 충분 한 양의 작업을 수행 해야 하는 경우 시퀀스를 병렬로 병합 합니다. 그렇지 않으면 호출 `bitonic_merge` 시퀀스를 직렬로 병합 합니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  이전 단계에서 하지만 대 한 예제와 유사 하는 프로세스를 수행 하는 `bitonic_sort` 함수입니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  오버 로드 된 버전을 만듭니다는 `parallel_bitonic_sort` 배열을 오름차순으로 정렬 하는 함수입니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 `parallel_invoke` 알고리즘은 호출 컨텍스트에서 일련의 작업 중 마지막 작업을 수행 하 여 오버 헤드를 줄입니다. 예를 들어는 `parallel_bitonic_sort` 함수를 첫 번째 태스크는 별도 컨텍스트에서 실행 되 고 두 번째 작업은 호출 컨텍스트에서 실행 됩니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 다음 전체 예제에서는 직렬 버전과 병렬 버전을 바 이토 닉 정렬 알고리즘의 모두 수행합니다. 이 예제에서는 또한 출력을 콘솔 각 계산을 수행 하는 데 필요한 시간 합니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 프로세서가 4개인 컴퓨터의 샘플 출력은 다음과 같습니다.  
  
```Output  
serial time: 4353  
parallel time: 1248  
```  
  
 [[맨 위로 이동](#top)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `parallel-bitonic-sort.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 병렬-바 이토 닉-sort.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 사용 하 여이 예제는 `parallel_invoke` 대신 알고리즘에서 [concurrency:: task_group](reference/task-group-class.md) 클래스 하므로 각 작업 그룹의 수명이 함수 보다는 확장 되지 않습니다. 사용 하는 것이 좋습니다 `parallel_invoke` 덜 보다 실행 오버 헤드가 있기 때문에 가능한 경우 `task group` 을 더 잘 수행 되는 코드를 작성할 수 있습니다.  
  
 일부 알고리즘의 병렬 버전 충분 한 작업을 수행 해야 경우에 성능이 향상 됩니다. 예를 들어는 `parallel_bitonic_merge` 함수 호출은 직렬 버전과 `bitonic_merge`시퀀스에서 500 개 이하의 요소가 없는 경우. 또한 작업 시간에 따라 전체 정렬 전략을 계획할 수 있습니다. 예를 들어 보다 효율적으로 다음 예제와 같이 배열 500 개 미만의 항목이 포함 된 경우 빠른 정렬 알고리즘의 직렬 버전을 사용할 수 있습니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 모든 병렬 알고리즘에서와 마찬가지로 프로 파일링 코드를 적절 하 게 조정 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel_invoke 함수](reference/concurrency-namespace-functions.md#parallel_invoke)

