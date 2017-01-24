---
title: "OMP_NUM_THREADS | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_NUM_THREADS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NUM_THREADS OpenMP environment variable"
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

최대 스레드 병렬 영역에 의해 재정의 되지 않으면 설정 하는 [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 또는 [num\_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## 구문  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `num`  
 최대 64에는 Visual C\+\+ 구현에 병렬 영역에 사용할 스레드 수입니다.  
  
## 설명  
 **OMP\_NUM\_THREADS** 환경 변수를 재정의 하 여 해당 [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 함수 또는 [num\_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 기본값은 `num` 는 Visual C\+\+ OpenMP 표준의 구현 하이퍼스레딩 Cpu 등 가상 프로세서의 수입니다.  
  
 자세한 내용은 [4.2 OMP\_NUM\_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)를 참조하십시오.  
  
## 예제  
 다음 명령 집합을  **OMP\_NUM\_THREADS** 16 환경 변수:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 다음 명령을 한 현재 설정을 표시 하는  **OMP\_NUM\_THREADS** 환경 변수:  
  
```  
set OMP_NUM_THREADS  
```  
  
## 참고 항목  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)