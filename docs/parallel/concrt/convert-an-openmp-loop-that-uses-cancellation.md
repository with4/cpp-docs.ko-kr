---
title: '방법: 동시성 런타임을 사용 하기 위해 취소를 사용 하는 OpenMP 루프 변환 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dae22a46d6570d7ef7abbdfc08cb2c6d76d0c08
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환
병렬 루프 모든 반복 실행 될 필요가 없습니다. 예를 들어 값을 검색 하는 알고리즘은 값을 찾은 후 종료 될 수 있습니다. OpenMP 병렬 루프를 중단 하는 메커니즘을 제공 하지 않습니다. 그러나 솔루션을 찾았습니다 나타내려면 루프의 반복을 사용 하도록 설정 하는 부울 값입니다. 또는 플래그를 사용할 수 있습니다. 동시성 런타임에서 아직 시작 되지 않은 다른 작업을 취소 한 작업을 수 있는 기능을 제공 합니다.  
  
 OpenMP 변환 하는 방법을 보여 주는이 예제 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 동시성 런타임에서 취소 메커니즘을 사용 하도록 모든 반복을 실행에 대 한 필요 하지 않은 루프입니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 OpenMP와 동시성 런타임을 사용 하 여의 병렬 버전을 구현 하는 [std::any_of](../../standard-library/algorithm-functions.md#any_of) 알고리즘입니다. 이 예제의 OpenMP 버전 플래그를 사용 하 여 조건이 충족 하는 모든 병렬 루프 반복 간에 조정. 동시성 런타임을 사용 하는 버전 사용 하 여 [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) 메서드는 조건이 충족 되 면 전체 작업을 중지 하려면.  

  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Using OpenMP...  
9114046 is in the array.  
Using the Concurrency Runtime...  
9114046 is in the array.  
```  
  
 루프의 모든 반복 실행을 사용 하 여 OpenMP 버전에서는 플래그 설정 된 경우에 합니다. 또한 자식 작업이 포함 하는 작업 인 경우 플래그도 것 취소를 전달 하는 자식 작업에 사용할 수입니다. 동시성 런타임에서 작업 그룹이 취소 되 면 런타임에 자식 작업을 포함 하 여 작업의 전체 트리를 취소 합니다. [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 알고리즘 작업을 사용 하 여 작업을 수행 합니다. 따라서 루프의 반복 하나가 루트 작업을 취소 하는 경우 계산의 전체 트리 취소 됩니다. 작업 트리에서 취소 되 면 런타임에 새 작업을 시작 하지 않습니다. 그러나 런타임에 끝나기를 이미 시작 된 태스크 수 있습니다. 따라서의 경우에 `parallel_for_each` 알고리즘, 활성 루프 반복 해당 리소스를 정리할 수 있습니다.  
  
 이 예의 두 버전을 배열에는 검색할 값의 복사본을 여러 개 포함 하는 경우 여러 루프 반복 각 결과 동시에 설정 수 및 전체 작업을 취소 합니다. 문제 한 태스크만 조건이 충족 되는 경우 작업을 수행 해야 하는 경우 임계 영역 같은 동기화 기본 형식을 사용할 수 있습니다.  
  
 또한 PPL을 사용 하는 작업을 취소 하는 예외 처리를 사용할 수 있습니다. 취소에 대 한 자세한 내용은 참조 [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.  
  
 에 대 한 자세한 내용은 `parallel_for_each` 오류 코드 및 기타 병렬 알고리즘을 참조 하십시오. [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `concrt-omp-parallel-any-of.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc /openmp concrt-omp-병렬-any-of.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [PPL에서의 취소](cancellation-in-the-ppl.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)

