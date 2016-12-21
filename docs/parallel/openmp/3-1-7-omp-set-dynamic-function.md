---
title: "3.1.7 omp_set_dynamic Function | Microsoft Docs"
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
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.7 omp_set_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Omp\_set\_dynamic** 함수 영역 병렬 실행에 사용할 스레드 수를 동적 조정을 사용할지 여부.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 경우  *dynamic\_threads* 평가 0이 아닌 값으로 시스템 리소스를 최대한 활용 하는 런타임 환경에 의해 다음 병렬 영역을 실행 하는 데 사용 되는 스레드 수를 자동으로 조정할 수 있습니다.  따라서 스레드는 사용자가 지정한 최대 스레드 수입니다.  스레드 병렬 영역 실행 팀의 병렬 영역 해당 기간 동안 고정 하 고 보고 되는  **omp\_get\_num\_threads** 함수입니다.  
  
 경우  *dynamic\_threads* 계산 0으로 동적 조정 사용할 수 없습니다.  
  
 이 함수 호출에서 일부 프로그램의 경우 위에서 설명한 효과가 어디에  **omp\_in\_parallel** 함수는 0을 반환 합니다.  프로그램의 일부에서 호출 되는 경우 위치는  **omp\_in\_parallel** 0이 아닌 값을 반환 하는 함수,이 함수의 동작은 정의 되지 않습니다.  
  
 호출을  **omp\_set\_dynamic** 보다 우선권을 갖습니다 있는  **OMP\_DYNAMIC** 환경 변수입니다.  
  
 스레드 동적 조정에 대 한 기본 구현 시 정의 됩니다.  따라서 스레드 올바른 실행을 위해 특정 수에 따라 달라 집니다 사용자 코드 동적 스레드를 명시적으로 해제 해야 합니다.  구현 스레드 수를 동적으로 조정할 수 있도록 하는 데 필요한 있지만 모든 플랫폼에 걸쳐 이동성을 지원 하기 위해 인터페이스를 제공할 필요가 없습니다.  
  
## 상호 참조:  
  
-   **omp\_get\_num\_threads** 작동, 참조 하십시오  [구역 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지입니다.  
  
-   **OMP\_DYNAMIC** 환경 변수를 참조 하십시오  [단원 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 페이지입니다.  
  
-   **omp\_in\_parallel** 작동, 참조 하십시오  [섹션 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 페이지에 있습니다.