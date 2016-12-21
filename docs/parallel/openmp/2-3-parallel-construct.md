---
title: "2.3 parallel Construct | Microsoft Docs"
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
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.3 parallel Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 지시문은 영역을 여러 스레드에서 동시에 실행 되는 프로그램의 병렬 영역을 정의 합니다.  이 병렬 실행을 시작 하는 기본 구조입니다.  
  
```  
#pragma omp parallel [clause[ [, ]clause] ...] new-line  
   structured-block  
```  
  
 해당  *절*  다음 중 하나입니다.  
  
 **경우 \(** *스칼라 식* **\)**  
  
 **개인 \(** *변수 목록* **\)**  
  
 **firstprivate \(** *변수 목록* **\)**  
  
 **default\(shared &#124; none\)**  
  
 **공유 \(** *변수 목록* **\)**  
  
 **copyin \(** *변수 목록* **\)**  
  
 **reduction\(** *operator* **:**  *variable\-list* **\)**  
  
 **num\_threads \(** *정수 식* **\)**  
  
 다음 경우 중 하나에 스레드 병렬 구문을 발견 되 면 팀의 스레드가 만들어집니다.  
  
-   더  **경우** 절 존재입니다.  
  
-   **경우** 식이 0이 아닌 값으로 계산 됩니다.  
  
 이 스레드가 스레드 수가 0, 팀의 마스터 스레드 상태가 및 지역 팀, 마스터 스레드를 포함 하 여 모든 스레드를 병렬로 실행할.  경우 값의  **경우** 식 0이 고, 지역 serialize 됩니다.  
  
 요청 된 스레드 수를 결정 하려면 다음 규칙을 순서에 간주 됩니다.  해당 조건을 충족 하는 첫 번째 규칙이 적용 됩니다.  
  
1.  경우는  **num\_threads** 절이 있는 경우 다음 요청 스레드 정수 식입니다.  
  
2.  경우는  **omp\_set\_num\_threads** 라이브러리 함수 호출 하 고 요청 된 스레드 수를 가장 최근에 실행 호출에서 인수의 값입니다.  
  
3.  경우 환경 변수  **OMP\_NUM\_THREADS** 이 환경 변수 값을 요청 된 스레드 수를 확인 한 다음 정의 됩니다.  
  
4.  위의 방법을 사용 하는 경우 요청 된 스레드 수를 구현 시 정의 됩니다.  
  
 경우는  **num\_threads** 절 되어 있는 다음 요청 스레드를 대체는  **omp\_set\_num\_threads** 라이브러리 함수 또는  **OMP\_NUM\_THREADS** 환경 변수를 적용 하 여 병렬 영역에만.  다음 병렬 영역에서 영향을 받지 않습니다.  
  
 또한 병렬 영역을 실행 하는 스레드 스레드 동적 조정을 사용 여부 따라 달라 집니다.  다음 동적 조정을 사용 하지 않으면 요청 된 스레드 수를 병렬 영역을 실행 합니다.  다음 동적 조정을 사용 하는 경우 최대 병렬 영역 실행 스레드가 요청 된 스레드 수가입니다.  
  
 병렬 영역 수를 동적 조정 하는 동안 발생 하는 경우 스레드가 해제 되 고 실행 시간 시스템을 제공할 수 있는 번호 병렬 영역에 대해 요청 된 스레드 수를 초과, 프로그램의 동작은 구현 시 정의 됩니다.  구현 예를 들어, 해당 프로그램의 실행을 인터럽트 수 있습니다, 또는 병렬 영역 serialize 할 수 있습니다.  
  
 **Omp\_set\_dynamic** 라이브러리 함수 및 해당  **OMP\_DYNAMIC** 사용 및 동적 조정의 스레드를 사용 하지 않도록 설정 하려면 환경 변수를 사용할 수 있습니다.  
  
 실제로 스레드를 언제 든 지 호스트 실제 프로세서의 수는 구현 시 정의 됩니다.  만든 스레드는 팀에서 병렬 영역 해당 기간 동안 그대로 유지.  사용자가 명시적으로 또는 자동으로 다른 한 병렬 영역에서 런타임 시스템에 의해 변경할 수 있습니다.  
  
 동적 범위를 병렬 영역 내에 포함 된 문은 각 스레드에 의해 실행 되 고 각 스레드는 다른 스레드에서 다른 경로 문을 실행할 수 있습니다.  어휘 범위를 병렬 영역 외부에서 발생 하는 지시문으로 분리 된 지시문 라고도 합니다.  
  
 병렬 영역 끝에는 암시적된 장애물이입니다.  마스터 스레드는 팀만 병렬 영역 끝에 실행이 계속 됩니다.  
  
 다른 병렬 구조는 스레드 병렬 영역 실행 팀에서 발견 한 새로운 팀을 만들고 새 팀의 마스터가 됩니다.  중첩 된 병렬 영역에는 기본적으로 serialize 됩니다.  따라서 기본적으로 중첩 된 병렬 영역에서는 하나의 스레드로 구성 된 팀에서 실행 됩니다.  런타임 라이브러리 함수를 사용 하 여 기본 동작을 변경할 수 있습니다  **omp\_set\_nested** 또는 환경 변수  **OMP\_NESTED**.  그러나 팀에서 병렬 중첩 된 영역을 실행 하는 스레드 수를 구현 시 정의 됩니다.  
  
 제한에는  **병렬** 지시어는 다음과 같습니다.  
  
-   최대 하나의  **경우** 절 지시문에 나타날 수 있습니다.  
  
-   여부 하나 안에 if 효과 면 지정 되지 않은 식 또는  **num\_threads** 식입니다.  
  
-   A  **throw** 내 병렬 영역 계속 같은 구조화 된 블록의 동적 범위 내에서 실행 될 및 throw 동일한 스레드에서 catch 해야 실행 됩니다.  
  
-   단일  **num\_threads** 절 지시문에 나타날 수 있습니다.  **Num\_threads** 식의 병렬 영역 컨텍스트 외부 평가 되 고 양수 값으로 계산 되어야 합니다.  
  
-   계산 순서는  **경우**  및  **num\_threads** 절을 지정 하지 않습니다.  
  
## 상호 참조:  
  
-   **개인**,  **firstprivate**,  **기본**,  **공유**,  **copyin**, 및  **감소**  절을 참조 하십시오.  [2.7.2 섹션](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지입니다.  
  
-   **OMP\_NUM\_THREADS** 환경 변수  [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 페이지입니다.  
  
-   **omp\_set\_dynamic** 라이브러리 함수를 참조 하십시오  [3.1.7 섹션](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.  
  
-   **OMP\_DYNAMIC** 환경 변수를 참조 하십시오  [단원 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 페이지입니다.  
  
-   **omp\_set\_nested** 작동, 참조 하십시오  [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지에 있습니다.  
  
-   **OMP\_NESTED** 환경 변수를 참조 하십시오  [섹션 4.4](../../parallel/openmp/4-4-omp-nested.md) 49 페이지입니다.  
  
-   **omp\_set\_num\_threads** 라이브러리 함수를 참조 하십시오  [3.1.1 구역](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지에 있습니다.