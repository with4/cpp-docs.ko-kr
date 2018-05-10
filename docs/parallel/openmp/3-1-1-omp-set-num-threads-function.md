---
title: 3.1.1 omp_set_num_threads 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99c82ff324cbf21612d2459511877d152e2757f5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads 함수
`omp_set_num_threads` 기본 개수를 지정 하지 않는 후속 병렬 영역에 사용할 스레드를 설정 하는 함수는 `num_threads` 절. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 매개 변수 값 *num_threads* 양의 정수 여야 합니다. 스레드 수의 동적 조정을 활성화 되어 있는지 여부에 미치는 영향에 따라 다릅니다. 다양 한 간의 상호 작용 하는 방법에 대 한 규칙에 대 한는 `omp_set_num_threads` 함수 및 스레드, 동적 조정 8 페이지 섹션 2.3을 참조 하세요.  
  
 이 함수는 프로그램의 부분에서 호출 될 때 위에서 설명한 효과가 있는 `omp_in_parallel` 함수는 0을 반환 합니다. 프로그램의 일부에서 호출 되는 경우 여기서는 `omp_in_parallel` 0이 아닌 값을 반환 하는 함수,이 함수의 동작이 정의 되지 않습니다.  
  
 이 호출 하는 보다 우선은 `OMP_NUM_THREADS` 환경 변수입니다. 호출 하 여 설정할 수 있는 스레드 수에 대 한 기본값 `omp_set_num_threads` 하거나 설정 하는 `OMP_NUM_THREADS` 단일 환경 변수를 명시적으로 재정의 될 수 있습니다 **병렬** 지정 하 여 지시문의 `num_threads` 절.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   `omp_set_dynamic` 함수, 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.  
  
-   `omp_get_dynamic` 함수, 참조 [섹션 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) 40 페이지.  
  
-   `OMP_NUM_THREADS` 환경 변수 참조 [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48, 페이지 및 섹션 2.3 8 페이지에 있습니다.  
  
-   `num_threads` 절 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 페이지 8에서