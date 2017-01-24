---
title: "3.1.1 omp_set_num_threads Function | Microsoft Docs"
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
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.1 omp_set_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_set_num_threads` 함수 설정 기본 스레드 수를 지정 하지 않은 대 한 후속 병렬 영역에는 `num_threads` 절.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 매개 변수 값  *num\_threads* 은 양의 정수 여야 합니다.  해당 스레드의 수를 동적 조정을 사용 여부 따라 달라 집니다.  규칙 간의 상호 작용에 대 한 포괄적인에는 `omp_set_num_threads` 함수 및 동적 스레드를 조정 8 페이지의 2.3 절을 참조 하십시오.  
  
 이 함수 호출에서 일부 프로그램의 경우 위에서 설명한 효과가 어디에 `omp_in_parallel` 함수는 0을 반환 합니다.  프로그램의 일부에서 호출 되는 경우 위치는 `omp_in_parallel` 0이 아닌 값을 반환 하는 함수,이 함수의 동작은 정의 되지 않습니다.  
  
 이 호출에 대해 우선 순위를 갖는 `OMP_NUM_THREADS` 환경 변수가 있습니다.  호출 하 여 설정할 수 있습니다 하는 스레드 수를 기본값은 `omp_set_num_threads` 하거나 설정 하는 `OMP_NUM_THREADS` 환경 변수 수 있습니다 명시적으로 재정의할 수 하나의  **병렬** 지시문을 지정 하는 `num_threads` 절.  
  
## 상호 참조:  
  
-   `omp_set_dynamic`작동, 참조 하십시오  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.  
  
-   `omp_get_dynamic`작동, 참조 하십시오  [섹션 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) 40 페이지에 있습니다.  
  
-   `OMP_NUM_THREADS`환경 변수를 참조 하십시오  [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48, 페이지 및 섹션 2.3 8 페이지입니다.  
  
-   `num_threads`절을 참조 하십시오  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지