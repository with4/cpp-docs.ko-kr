---
title: "3.1.2 omp_get_num_threads Function | Microsoft Docs"
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
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.2 omp_get_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Omp\_get\_num\_threads** 함수가 스레드 현재 병렬 영역에서 호출 된 실행 팀의를 반환 합니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **Num\_threads** 절을는  **omp\_set\_num\_threads** 함수를 하는  **OMP\_NUM\_THREADS** 환경 변수 팀에서 스레드 수를 제어 합니다.  
  
 스레드는 사용자가 명시적으로 설정 되지 않았습니다 경우 기본 구현 시 정의 됩니다.  이 함수는 가장 가까운 바깥쪽 바인딩합니다  **병렬** 지시문입니다.  이 함수 호출 하는 프로그램의 일부 직렬 또는 연속 되는 중첩 된 병렬 영역에서 경우 1을 반환 합니다.  
  
## 상호 참조:  
  
-   **OMP\_NUM\_THREADS** 환경 변수를 참조 하십시오  [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 페이지입니다.  
  
-   **num\_threads** 절을 참조 하십시오  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.  
  
-   **병렬** 만드는 자세한 내용은  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.