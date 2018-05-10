---
title: E. 구현 정의 동작 OpenMP C/c + +에서 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 598964ec6a12ac4c357efc04df78bfbe3af798a5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. 구현 정의 동작 OpenMP C/c + +에서
이 부록 "구현에서 정의 된"이 api에서로 설명 하는 동작을 요약 합니다.  각 동작은 다시 상호 참조 하도록 주 사양에서 설명 합니다.  
  
## <a name="remarks"></a>설명  
 구현을 정의 하 고 이러한 경우의 동작을 문서화 필요 하지만이 목록이 불완전할 수 있습니다.  
  
-   **스레드 수가:** 병렬 영역 스레드 수의 동적 조정을 사용 하지 않으면 및 병렬 영역에 대해 요청 된 스레드의 수 런타임 시스템을 제공할 수 있도록 동작의 수를 초과 하는 동안 발생 하는 경우 프로그램은 구현 시 정의 (9 페이지 참조).  
  
     Visual c + +에서는 중첩 되지 않은 병렬 영역에 대 한 64 개 스레드 (최대)이 제공 됩니다.  
  
-   **프로세서의 수:** 스레드가 지정된 된 시간에 실제로 호스팅하는 실제 프로세서 수가 구현에서 정의 된 (10 페이지 참조).  
  
     Visual c + +에서는이 숫자 상수가 아닙니다. 및 운영 체제에 의해 제어 됩니다.  
  
-   **스레드 팀을 만들고:** 중첩 된 병렬 영역을 실행 하는 팀의 스레드 수는 구현 정의 합니다. ( 10 페이지 참조).  
  
     Visual c + +에서는이 운영 체제에 의해 결정 됩니다.  
  
-   **schedule (runtime):** 런타임이 될 때까지 지연 됩니다에 대 한 일정에 대 한 결정 합니다. 일정 유형 및 청크 크기를 설정 하 여 런타임 시 선택할 수는 `OMP_SCHEDULE` 환경 변수입니다. 이 환경 변수를 설정 하지 않으면 결과 일정은 구현 시 정의 (13 페이지 참조).  
  
     일정 유형은 Visual c + +에서 `static` 청크 크기가 없습니다.  
  
-   **기본 일정:** schedule 절의 없는 경우, 기본 일정은 구현 시 정의 (13 페이지 참조).  
  
     Visual c + +에서는 기본 일정 유형이 `static` 청크 크기가 없습니다.  
  
-   **ATOMIC:** 는 구현에서 정의 된 여부 구현에서는 모든 대체 `atomic` 지시문으로 **중요** 지시문 동일한 고유 이름 (20 페이지 참조).  
  
     Visual c + +에서는 데이터 수정 된 [원자성](../../parallel/openmp/reference/atomic.md) 자연 맞춤 켜져 있지 않으면 해당 속성을 만족 하는 긴 모든 원자 단위 연산을 하나의 임계 영역을 사용할 경우 1 개 또는 2 바이트입니다. 그렇지 않으면 임계 영역 사용 되지 않습니다.  
  
-   **omp_get_num_threads:** 스레드 수는 사용자가 명시적으로 설정 되지 않았습니다, 구현에서 정의 된 기본값은 (9, 페이지를 참조 하 고 [단원 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지).  
  
     Visual c + +에서는 기본 스레드 수의 프로세서 수와 같습니다.  
  
-   **omp_set_dynamic:** 동적 스레드 조정에 대 한 기본값은 구현 시 정의 (참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 페이지 39).  
  
     기본값은 Visual c + +에서 `FALSE`합니다.  
  
-   **omp_set_nested:** 중첩 된 병렬 처리를 사용 하는 중첩 된 병렬 영역은 실행 하는 데 사용 되는 스레드 수는 구현 시 정의 (참조 [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지).  
  
     Visual c + +에서 스레드 수는 운영 체제에 의해 결정 됩니다.  
  
-   `OMP_SCHEDULE` 환경 변수:이 환경 변수에 대 한 기본값은 구현 시 정의 (참조 [섹션 4.1](../../parallel/openmp/4-1-omp-schedule.md) 페이지 코어 48 개).  
  
     일정 유형은 Visual c + +에서 `static` 청크 크기가 없습니다.  
  
-   `OMP_NUM_THREADS` 환경 변수: 없는 값을 지정 하는 경우는 `OMP_NUM_THREADS` 환경 변수를 지정한 값이 양의 정수 또는 사용할 스레드 수는 값은 시스템에서 지원할 수 스레드의 최대 개수 보다 큰 경우 구현 시 정의 (참조 [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 페이지 코어 48 개).  
  
     Visual c + +에서 값을 지정 하는 경우가 0 또는 이하인 스레드 수는 프로세서 수와 같습니다.  값은 64 보다 큰 경우 스레드 수가 64입니다.  
  
-   `OMP_DYNAMIC` 환경 변수: 기본값은 구현 시 정의 (참조 [섹션 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 페이지).  
  
     기본값은 Visual c + +에서 `FALSE`합니다.