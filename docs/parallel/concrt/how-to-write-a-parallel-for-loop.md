---
title: '방법: parallel_for 루프 작성 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4f3121130cd4b2871e3e3df73dd4117f946caca
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-write-a-parallelfor-loop"></a>방법: parallel_for 루프 작성
사용 하는 방법을 보여 주는이 예제 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 두 행렬의 곱을 계산 합니다.  
  
## <a name="example"></a>예제  
 다음 예제와 `matrix_multiply` 함수는 두 개의 사각형 매트릭스의 곱을 계산 합니다.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]  
  
## <a name="example"></a>예제  
 다음 예제와 `parallel_matrix_multiply` 함수를 사용 하는 `parallel_for` 외부 루프를 병렬로 수행 하는 알고리즘이 있습니다.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]  
  
 이 예제에서는 병렬 처리에 대 한 오버 헤드를 활용할 수 있는 충분 한 작업을 수행 하기 때문에만 외부 루프를 병렬로 실행 합니다. 내부 루프를 평행 화 하면 받지 못합니다 향상 된 성능이 약간 내부 루프를 수행 하는 작업의 병렬 처리에 대 한 오버 헤드 보다 크지 않습니다 때문에 합니다. 따라서 외부 루프만 병렬 처리하는 것이 대부분의 시스템에서 동시성의 이점을 극대화하는 가장 좋은 방법입니다.  
  
## <a name="example"></a>예제  
 다음 자세한 예제의 성능을 비교는 `matrix_multiply` 함수와 `parallel_matrix_multiply` 함수입니다.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]  
  
 프로세서가 4개인 컴퓨터의 샘플 출력은 다음과 같습니다.  
  
```Output  
serial: 3853  
parallel: 1311  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `parallel-matrix-multiply.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 병렬-매트릭스-multiply.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for 함수](reference/concurrency-namespace-functions.md#parallel_for)


