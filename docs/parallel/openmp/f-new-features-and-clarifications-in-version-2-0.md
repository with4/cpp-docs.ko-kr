---
title: "F. New Features and Clarifications in Version 2.0 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# F. New Features and Clarifications in Version 2.0
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 부록에서는 OpenMP C\/C\+\+ 사양 버전 1.0에서 2.0 버전으로의 업그레이드에 대 한 주요 변경 사항을 요약 합니다.  다음은 사양에 추가 된 새 기능입니다.  
  
-   OpenMP 지시문에서 쉼표 사용할 수 \([섹션 2.1](../../parallel/openmp/2-1-directive-format.md) 7 페이지\)입니다.  
  
-   추가 `num_threads` 절.  이 절이 특정 수의 병렬 구문에 대 한 스레드를 요청 할 수 있습니다 \([섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지\).  
  
-   `threadprivate` 지시문 블록 범위 정적 변수를 사용할 수를 확장 되었습니다 \([섹션 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) 23 페이지\).  
  
-   C99 가변 길이 배열 전체 형식이 고 그러므로 아무 곳 이나 전체 형식 허용 되지, 예를 들어 목록에 지정 될 수 있습니다 `private`, `firstprivate`, 및 `lastprivate` 절 \([섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지\).  
  
-   Private 변수는 병렬 영역에는 중첩 된 지시문을 다시 비공개로 표시할 수 있습니다 \([2.7.2.1 섹션](../../parallel/openmp/2-7-2-1-private.md) 25 페이지\).  
  
-   `copyprivate` 절이 추가 되었습니다.  Private 변수를 사용 하 여 값 팀의 한 구성원에서 다른 구성원으로 방송 하는 메커니즘을 제공 합니다.  공유 변수 제공 \(각 수준에 서로 다른 변수를 필요로 합니다. 예를 들어, 있는 재귀\)에 어려운 때 공유 변수 값을 사용 하는 대신 것입니다.  `copyprivate` 절에 나타날 수 있습니다만  **단일** 지시문 \([2.7.2.8 섹션](../../parallel/openmp/2-7-2-8-copyprivate.md) 32 페이지\).  
  
-   타이밍 루틴을 추가 `omp_get_wtick` 및 `omp_get_wtime` MPI 루틴을 비슷합니다.  이러한 함수는 벽 클럭 타이밍을 수행 하는 데 필요한 있습니다 \([구역 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) 44 페이지 및  [3.3.2 절](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) 45 페이지\).  
  
-   부록 동작은 구현 시 정의에서 OpenMP C\/C\+\+의 목록을 추가 했습니다.  구현을 정의 하 고 이러한 경우에 동작을 문서화 하는 데 필요한 됩니다 \([부록 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) 97 페이지\).  
  
-   다음과 같은 변경 사항을 명확 하 게 설명 하거나 이전 OpenMP API 사양에 대 한 C\/C\+\+의 기능을 수정 하려면 사용할 수 있습니다.  
  
    -   설명이 추가 되었습니다 동작을 `omp_set_nested` 및 `omp_set_dynamic` 때 `omp_in_parallel` 0이 아닌 반환 정의 되지 않았습니다 \([섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39, 페이지 및  [3.1.9 섹션](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지\).  
  
    -   중첩 된 병렬 사용 하는 경우 중첩 지시문 설명이 추가 되었습니다 \([2.9 절](../../parallel/openmp/2-9-directive-nesting.md) 33 페이지\).  
  
    -   병렬 영역에는 잠금 초기화 및 잠금 소멸 함수를 호출할 수 있습니다 \([3.2.1 절](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) 페이지 42 및  [구역 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) 페이지 42\).  
  
    -   새로운 예제가 추가 되었습니다 \([부록 A](../../parallel/openmp/a-examples.md) 51 페이지\).