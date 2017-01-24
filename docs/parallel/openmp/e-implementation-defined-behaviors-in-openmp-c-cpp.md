---
title: "E. Implementation-Defined Behaviors in OpenMP C/C++ | Microsoft Docs"
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
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# E. Implementation-Defined Behaviors in OpenMP C/C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 부록으로 "구현 시 정의"이이 API에서 설명 하는 동작을 요약 합니다.  각 동작의 기본 사양 설명 하는 상호 참조입니다.  
  
## 설명  
 구현을 정의 하 고 이러한 경우에 동작을 문서화 하는 데 필요한 이지만이 목록이 불완전할 수 있습니다.  
  
-   **스레드:** 병렬 영역 동적 조정의 스레드 수를 사용할 수 없습니다, 그리고 및 병렬 영역에 대해 요청 된 스레드 수를 실행 시간 시스템을 제공할 수 있는 수를 초과 하는 동안 발생 하는 경우 프로그램의 동작이 구현 \(pageref 페이지 참조\) 정의 되어 있습니다.  
  
     Visual C\+\+에서는 중첩 되지 않은 병렬 영역에 대 한 64 개 스레드 \(최대\) 제공 됩니다.  
  
-   **프로세서:** \(10 페이지 참조\) 실제로 스레드를 언제 든 지 호스트 실제 프로세서 구현을 정의 됩니다.  
  
     Visual C\+\+에서이 상수 되지 않고 운영 체제에 의해 제어 됩니다.  
  
-   **팀의 스레드 만들기:** 팀에서 병렬 중첩 된 영역을 실행 하는 스레드 수를 구현 시 정의 됩니다.\(10 페이지 참조\).  
  
     Visual C\+\+에서이 운영 체제에 의해 결정 됩니다.  
  
-   **schedule\(runtime\):** 결정 관련 일정 런타임까지 지연 됩니다.  일정 유형 및 청크 크기 런타임에 설정 하 여 선택할 수 있는 `OMP_SCHEDULE` 환경 변수입니다.  이 환경 변수를 설정 하지 않으면 결과 일정 구현 \(13 페이지 참조\) 정의 됩니다.  
  
     Visual C\+\+에서는 일정 형식입니다 `static` 와 청크 크기.  
  
-   **기본 예약:** 일정 절 없는 경우 기본 일정이 구현 \(13 페이지 참조\) 정의 됩니다.  
  
     Visual C\+\+를 기본 일정 유형입니다 `static` 와 청크 크기.  
  
-   **원자:** 여부는 구현 모두 대체 구현이 정의 된 것이 `atomic` 지시문과 함께  **중요 한** \(20 페이지 참조\) 고유 이름은 지시문입니다.  
  
     시각적으로 데이터를 수정 하는 경우 c에서 [atomic](../../parallel/openmp/reference/atomic.md) 자연 정렬 수 없습니다 또는 1 바이트 또는 2 바이트 이면 해당 속성에 맞는 긴 모든 원자 연산 하나의 중요 섹션을 사용 합니다.  그렇지 않으면 중요 섹션 사용 되지 않습니다.  
  
-   **omp\_get\_num\_threads:** 스레드는 사용자가 명시적으로 설정 되지 않았습니다 경우 기본 구현 시 정의 됩니다 \(9 페이지를 참조 하십시오 및  [구역 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지\).  
  
     Visual C\+\+의 기본 스레드 수에 프로세서 수와입니다.  
  
-   **omp\_set\_dynamic:** 동적 스레드 조정에 대 한 기본 구현 시 정의 됩니다 \(참조 하십시오  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 페이지 39\).  
  
     Visual C\+\+의 기본입니다 `FALSE`.  
  
-   **omp\_set\_nested:** 중첩 된 병렬 처리를 사용 하면 중첩 된 병렬 영역을 실행 하는 데 스레드 구현 시 정의 됩니다 \(참조 하십시오  [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 페이지 40\).  
  
     Visual C\+\+의 스레드 수를 운영 체제에 의해 결정 됩니다.  
  
-   `OMP_SCHEDULE`환경 변수: 기본값은 환경 변수의 구현 시 정의 됩니다 \(참조 하십시오  [구역 4.1](../../parallel/openmp/4-1-omp-schedule.md) 48 페이지\).  
  
     Visual C\+\+에서는 일정 형식입니다 `static` 와 청크 크기.  
  
-   `OMP_NUM_THREADS`환경 변수:에 대 한 값을 지정 하는 경우는 `OMP_NUM_THREADS` 환경 변수 또는 지정 된 값은 양의 정수 없거나 값이 시스템에서 지원 하는 스레드의 최대 개수 보다 큰 경우 스레드를 사용 하 여 구현 시 정의 됩니다 경우 \(참조 하십시오  [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 페이지\).  
  
     Visual C\+\+에서 값을 지정 하는 경우 0 또는 이하의 스레드의 수를 프로세서 수와입니다.  값 64 보다 큰 경우 스레드 수를 64입니다.  
  
-   `OMP_DYNAMIC`환경 변수: 기본값은 구현 시 정의 됩니다 \(참조 하십시오  [단원 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 페이지 49\).  
  
     Visual C\+\+의 기본입니다 `FALSE`.