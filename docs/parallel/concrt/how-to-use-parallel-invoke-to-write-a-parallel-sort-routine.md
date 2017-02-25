---
title: "방법: parallel_invoke를 사용하여 병렬 정렬 루틴 작성 | Microsoft Docs"
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
  - "task_handle 클래스, 예제"
  - "task_group 클래스, 예제"
  - "make_task 함수, 예제"
  - "structured_task_group 클래스, 예제"
  - "작업 그룹으로 병렬 성능 향상[동시성 런타임]"
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# 방법: parallel_invoke를 사용하여 병렬 정렬 루틴 작성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 [parallel\_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘을 사용하여 바이토닉 정렬 알고리즘의 성능을 향상시키는 방법에 대해 설명합니다.  바이토닉 정렬 알고리즘은 입력 시퀀스를 더 작은 정렬된 파티션으로 재귀적으로 나눕니다.  각 파티션 작업은 다른 모든 작업과 별개로 실행되므로 바이토닉 정렬 알고리즘을 병렬로 실행할 수 있습니다.  
  
 바이토닉 정렬은 입력 시퀀스의 모든 조합을 정렬하는 *정렬 네트워크*의 한 예라고 할 수 있지만 이 방법은 길이가 2의 거듭제곱인 시퀀스를 정렬합니다.  
  
> [!NOTE]
>  이 예제에서는 그림에 대한 병렬 정렬 루틴을 사용합니다.  PPL에서 제공 하는 기본 제공 정렬 알고리즘을 사용할 수도 있습니다:  [concurrency::parallel\_sort](../Topic/parallel_sort%20Function.md),  [concurrency::parallel\_buffered\_sort](../Topic/parallel_buffered_sort%20Function.md), 및  [concurrency::parallel\_radixsort](../Topic/parallel_radixsort%20Function.md).  자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
##  <a name="top"></a> 단원  
 이 문서에서는 다음 작업에 대해 설명합니다.  
  
-   [직렬 바이토닉 정렬 수행](#serial)  
  
-   [parallel\_invoke를 사용하여 바이토닉 정렬을 병렬로 수행](#parallel)  
  
##  <a name="serial"></a> 직렬 바이토닉 정렬 수행  
 다음 예제에서는 직렬 버전의 바이토닉 정렬 알고리즘을 보여 줍니다.  `bitonic_sort` 함수는 시퀀스를 두 개의 파티션으로 나누고, 이러한 파티션을 반대 방향으로 정렬한 후 결과를 병합합니다.  이 함수는 자신을 재귀적으로 두 번 호출하여 각 파티션을 정렬합니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 \[[맨 위](#top)\]  
  
##  <a name="parallel"></a> parallel\_invoke를 사용하여 바이토닉 정렬을 병렬로 수행  
 이 단원에서는 `parallel_invoke` 알고리즘을 사용하여 바이토닉 정렬 알고리즘을 병렬로 수행하는 방법에 대해 설명합니다.  
  
### 절차  
  
##### 바이토닉 정렬 알고리즘을 병렬로 수행하려면  
  
1.  헤더 파일 ppl.h에 대한 `#include` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  `concurrency` 네임스페이스에 대한 `using` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  `parallel_bitonic_mege`라는 새 함수를 만듭니다. 이 함수는 작업량이 충분할 경우 `parallel_invoke` 알고리즘을 사용하여 시퀀스를 병렬로 병합합니다.  그렇지 않으면 `bitonic_merge`를 호출하여 시퀀스를 연속으로 병합합니다.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  `bitonic_sort` 함수에 대해 이전 단계와 유사한 프로세스를 수행합니다.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  배열을 오름차순으로 정렬하는 `parallel_bitonic_sort` 함수의 오버로드된 버전을 만듭니다.  
  
     [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 `parallel_invoke` 알고리즘은 일련의 작업 중 마지막 작업을 호출 컨텍스트에서 수행하여 오버헤드를 줄입니다.  예를 들어 `parallel_bitonic_sort` 함수에서 첫 번째 작업은 별도의 컨텍스트에서 실행되고 두 번째 작업은 호출 컨텍스트에서 실행됩니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 다음 전체 예제에서는 바이토닉 정렬 알고리즘의 직렬 버전과 병렬 버전을 둘 다 수행합니다.  또한 각 계산을 수행하는 데 필요한 시간을 콘솔에 출력합니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.  
  
  **직렬 시간: 4353**  
**병렬 시간: 1248** \[[맨 위](#top)\]  
  
## 코드 컴파일  
 코드를 컴파일하려면 코드를 복사한 다음, Visual Studio 프로젝트 또는 `parallel-bitonic-sort.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-bitonic\-sort.cpp**  
  
## 강력한 프로그래밍  
 이 예제에서는 각 작업 그룹의 수명이 함수보다 짧기 때문에 [concurrency::task\_group](../Topic/task_group%20Class.md) 클래스 대신 `parallel_invoke` 알고리즘을 사용합니다.  가능하면, `task group` 개체보다 실행 오버헤드가 적어서 성능이 높은 코드를 작성할 수 있는 `parallel_invoke`를 사용하는 것이 좋습니다.  
  
 일부 알고리즘의 병렬 버전은 수행할 작업의 양이 충분한 경우에만 효과적으로 수행됩니다.  예를 들어 `parallel_bitonic_merge` 함수는 시퀀스의 요소가 500개 이하인 경우 직렬 버전 `bitonic_merge`를 호출합니다.  작업량을 기반으로 전체 정렬 방법을 계획할 수도 있습니다.  예를 들어 배열에 포함되어 있는 항목이 500개 미만인 경우 다음 예제에서와 같이 직렬 버전의 빠른 정렬 알고리즘을 사용하는 것이 더 효율적일 수 있습니다.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 병렬 알고리즘과 마찬가지로 필요에 따라 코드를 프로파일링하고 조정하는 것이 좋습니다.  
  
## 참고 항목  
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel\_invoke 함수](../Topic/parallel_invoke%20Function.md)