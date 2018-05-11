---
title: F. 새로운 기능 및 버전 2.0에서에서 구현 하는 설명 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e48f299e66ed1b4c075757a9cd143d0afe897db
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. 새로운 기능 및 버전 2.0에에서 대 한 설명
이 부록 키 변경 버전 2.0 버전 1.0의에서 이동에 OpenMP C/c + + 사양에 요약 되어 있습니다. 다음 항목은 사양에 추가 된 새로운 기능:  
  
-   쉼표는 OpenMP 지시문에 사용할 수 있습니다. ([섹션 2.1](../../parallel/openmp/2-1-directive-format.md) 7 페이지).  
  
-   추가 `num_threads` 절. 이 절을 사용 하면 사용자가 특정 개수의 병렬 구문에 대 한 스레드를 요청할 수 ([섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에).  
  
-   `threadprivate` 지시문 정적 블록 범위 변수를 허용 하도록 확장 되었습니다 ([섹션 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) 페이지 23).  
  
-   C99 가변 길이 배열 형식은 완료 및 따라서 지정할 수 있습니다 아무 곳 이나 완전 한 형식에에서는 사용할 수, 예를 들어 목록에 `private`, `firstprivate`, 및 `lastprivate` 절 ([섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 페이지 25).  
  
-   병렬 영역에 전용 변수를 중첩 된 지시문에서 다시 개인으로 표시 될 수 있습니다 ([섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 페이지 25).  
  
-   `copyprivate` 절이 추가 되었습니다. 다른 구성원에 게 팀의 멤버 중 하나에서 값을 브로드캐스트할 개인 변수를 사용 하는 메커니즘을 제공 합니다. 것 (예를 들어, 각 수준에서 서로 다른 변수를 요구 하는 재귀)에서 어려울 수는 공유 변수를 제공 하는 경우 값에 대 한 공유 변수를 사용 하는 대신 합니다. `copyprivate` 절에 나타날 수는 **단일** 지시문 ([섹션 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) 페이지 32).  
  
-   타이밍 루틴의 추가 `omp_get_wtick` 및 `omp_get_wtime` MPI 루틴 비슷합니다. 이러한 함수는 벽 시계 시간을 수행 하는 데 필요한 ([섹션 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) 44 페이지 및 [단원 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) 페이지 45).  
  
-   부록 구현 정의 동작 OpenMP C/c + +에서의 목록과 함께 추가 되었습니다. 구현을 정의 하 고 이러한 경우의 동작을 문서화 하는 데 필요한 됩니다 ([부록 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) 97 페이지).  
  
-   다음과 같이 변경 명확 하 게 하거나 수정 C/c + +에 대 한 이전 OpenMP API 사양에는 기능 제공:  
  
    -   된다고의 동작 `omp_set_nested` 및 `omp_set_dynamic` 때 `omp_in_parallel` 0이 아닌 반환이 정의 되지 않습니다 ([3.1.7 섹션](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39, 페이지 및 [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지).  
  
    -   중첩 된 병렬 사용 되는 경우 지시문 중첩 설명이 명시 되었습니다 ([섹션 2.9](../../parallel/openmp/2-9-directive-nesting.md) 페이지 33).  
  
    -   병렬 영역에서 잠금을 초기화 및 잠금 소멸 함수를 호출할 수 있습니다 ([섹션 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) 42 페이지 및 [섹션 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) 42 페이지에).  
  
    -   추가 된 새 예제 ([부록 A](../../parallel/openmp/a-examples.md) 51 페이지).