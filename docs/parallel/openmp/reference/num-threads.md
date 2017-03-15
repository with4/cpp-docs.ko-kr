---
title: "num_threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_threads OpenMP clause"
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

스레드는 스레드 팀에 설정합니다.  
  
## 구문  
  
```  
num_threads(num)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `num`  
 스레드 수  
  
## 설명  
 `num_threads` 절이 같은 기능을 [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 함수입니다.  
  
 `num_threads`다음 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [parallel](../../../parallel/openmp/reference/parallel.md) 를 사용 하는 예에 대 한 `num_threads` 절.  
  
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)