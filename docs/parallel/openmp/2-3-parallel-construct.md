---
title: 2.3 parallel 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 121454f6a98901a6c1b695a80c6ec774737b95e0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="23-parallel-construct"></a>2.3 parallel 구문
다음 지시문을 동시에 여러 개의 스레드에서 실행할 프로그램의 영역인 병렬 영역을 정의 합니다. 이 병렬 실행을 시작 하는 기본 구문입니다.  
  
```  
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block  
```  
  
 *절* 다음 중 하나입니다.  
  
 **if(** *scalar-expression* **)**  
  
 **private(** *variable-list* **)**  
  
 **firstprivate(** *variable-list* **)**  
  
 **기본 (공유 &#124; 없음)**  
  
 **shared(** *variable-list* **)**  
  
 **copyin(** *variable-list* **)**  
  
 **reduction(** *operator* **:**  *variable-list* **)**  
  
 **num_threads(** *integer-expression* **)**  
  
 다음 경우 중 하나에 있는 스레드는 병렬 구문을 발견 하면 스레드 팀이 만들어집니다.  
  
-   더 **경우** 절이 있습니다.  
  
-   **경우** 식이 0이 아닌 값으로 계산 합니다.  
  
 이 스레드가 스레드 수가 0, 팀의 마스터 스레드에 되며 모든 스레드가 마스터 스레드에 포함 하 여 팀의 영역을 병렬로 실행 합니다. 경우의 값은 **경우** 식이 0 이면 지역 serialize 됩니다.  
  
 요청 된 스레드의 수를 확인 하려면 다음 규칙 순서로 간주 됩니다. 첫 번째 규칙 인 조건에 적용 됩니다.  
  
1.  경우는 **num_threads** 절을 사용할 수 있으면 다음 정수 식의 값은 요청 된 스레드의 수입니다.  
  
2.  경우는 **omp_set_num_threads** 라이브러리 함수를 호출한 다음 가장 최근에 실행된 한 호출의 인수 값은 요청 된 스레드의 수입니다.  
  
3.  경우 환경 변수 **OMP_NUM_THREADS** 이 환경 변수의 값은 요청 된 스레드 수가 정의 됩니다.  
  
4.  위에서 설명한 방법 중 사용 되는 경우 요청 된 스레드의 수 구현에서 정의 된은 다음 합니다.  
  
 경우는 **num_threads** 절이 있는 다음에서 요청 하는 스레드 수가 교체 되는 **omp_set_num_threads** 라이브러리 함수 또는 **OMP_NUM_THREADS** 병렬 영역에 대 한 환경 변수에 적용 됩니다. 후속 병렬 영역에 영향을 받지 않습니다.  
  
 또한 병렬 영역을 실행 하는 스레드 수가 스레드 수의 동적 조정을 사용 하도록 설정 여부에 따라 달라 집니다. 동적 조정 하지 않으면 스레드 수가 요청 된 병렬 영역을 실행 됩니다. 이상을 사용 하는 경우 요청 된 수의 스레드는 병렬 영역 실행 되는 스레드의 최대 수입니다.  
  
 병렬 영역 스레드 수의 동적 조정을 사용 하지 않으면 병렬 영역에 대해 요청 된 스레드 수는 런타임 시스템에서 제공할 수 있는 수를 초과 하는 동안 발생 하는 경우 프로그램의 동작은 구현 시 정의 합니다. 구현 될 수 있습니다 프로그램의 실행을 중단 예를 들어 또는 병렬 영역을 serialize 할 수 있습니다.  
  
 **omp_set_dynamic** 라이브러리 함수 및 **OMP_DYNAMIC** 활성화 및 스레드 수의 동적인 조절을 비활성화 하는 환경 변수를 사용할 수 있습니다.  
  
 스레드가 지정된 된 시간에 실제로 호스팅하는 실제 프로세서 수가 구현 시 정의 됩니다. 를 만든 후 팀의 스레드 수가 일정 하 게 유지 되는 병렬 영역의 기간에 대 한 합니다. 다른 하나의 병렬 영역에서 런타임 시스템에서 사용자가 명시적으로 또는 자동으로 변경할 수 있습니다.  
  
 병렬 영역의 동적 범위 내에 포함 된 문이 각 스레드에 의해 실행 되도록 하 고 각 스레드가 다른 스레드에서 다른 문의 경로 실행할 수 있습니다. 병렬 영역의 어휘 범위 외부에서 발생 하는 지시문 고아 지시문으로 참조 됩니다.  
  
 병렬 영역의 끝에는 암시적된 장벽이 있습니다. 팀의 마스터 스레드만 병렬 영역 끝날 때 실행을 계속 합니다.  
  
 병렬 영역을 실행 하는 팀에 스레드가 다른 병렬 구문을 발견 하는 경우 새 팀을 만듭니다 및 해당 새 팀의 마스터 됩니다. 중첩 된 병렬 영역은 기본적으로 serialize 됩니다. 결과적으로, 기본적으로 중첩 된 병렬 영역 중 하나의 구성 된 팀에서 실행 됩니다. 런타임 라이브러리 함수를 사용 하 여 기본 동작을 변경할 수 있습니다 **omp_set_nested** 또는 환경 변수가 **OMP_NESTED**합니다. 그러나 중첩 된 병렬 영역을 실행 하는 팀의 스레드 수는 구현 정의 합니다.  
  
 에 대 한 제한 된 **병렬** 지시문은 다음과 같습니다.  
  
-   최대 하나의 **경우** 지시문에 절에 나타날 수 있습니다.  
  
-   If 내 효과 측면 모두 연결 여부 지정 되지 않습니다 식 또는 **num_threads** 식 발생 합니다.  
  
-   A **throw** 실행 병렬 영역 내부 같은 구조화 된 블록의 동적 범위 내에서 다시 시작 하려면 실행을 수행 해야 하 고 예외를 발생 시킨 동일한 스레드에서 찾아내야 합니다.  
  
-   단일 **num_threads** 지시문에 절에 나타날 수 있습니다. **num_threads** 식은 병렬 영역의 컨텍스트 외부에서 평가 되 고 양의 정수 값으로 계산 되어야 합니다.  
  
-   평가 순서는 **경우** 및 **num_threads** 절이 지정 되지 않습니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **개인**, **firstprivate**, **기본**, **공유**, **copyin**, 및 **감소**절 참조 [섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 페이지 25입니다.  
  
-   **OMP_NUM_THREADS** 환경 변수 [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 코어 48 개 페이지에 있습니다.  
  
-   **omp_set_dynamic** 라이브러리 함수 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.  
  
-   **OMP_DYNAMIC** 환경 변수를 참조 [섹션 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 페이지 49에 있습니다.  
  
-   **omp_set_nested** 함수, 참조 [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지.  
  
-   **OMP_NESTED** 환경 변수를 참조 [섹션 4.4](../../parallel/openmp/4-4-omp-nested.md) 페이지 49에 있습니다.  
  
-   **omp_set_num_threads** 라이브러리 함수 참조 [섹션 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지.