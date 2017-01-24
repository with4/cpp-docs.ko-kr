---
title: "4.2 OMP_NUM_THREADS | Microsoft Docs"
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
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.2 OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_NUM\_THREADS** 환경 변수를 실행 하는 동안 사용할 스레드의 기본 개수 설정 번호를 호출 하 여 명시적으로 변경 하지 않는 한는  **omp\_set\_num\_threads** 라이브러리 루틴 또는 명시적으로  **num\_threads** 절에는  **병렬** 지시문입니다.  
  
 값은  **OMP\_NUM\_THREADS** 환경 변수는 양수 여야 합니다.  해당 스레드의 수를 동적 조정을 사용 여부 따라 달라 집니다.  규칙 간의 상호 작용에 대 한 포괄적인에는  **OMP\_NUM\_THREADS** 환경 변수 및 동적 조정 스레드, 8 페이지의 2.3 절을 참조 하십시오.  
  
 값을 지정 하지 않은 경우는  **OMP\_NUM\_THREADS** 환경 변수 또는 지정 된 값은 양의 정수 되었거나 값이 시스템에서 지원 하는 스레드의 최대 개수 보다 큰 경우 스레드를 사용 하 여 구현 시 정의 됩니다.  
  
 예를 들면 와 같은 형식입니다.  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## 상호 참조:  
  
-   **num\_threads** 절을 참조 하십시오  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.  
  
-   **omp\_set\_num\_threads** 작동, 참조 하십시오  [3.1.1 구역](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지에 있습니다.  
  
-   **omp\_set\_dynamic** 작동, 참조 하십시오  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.