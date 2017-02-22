---
title: "omp_nest_lock_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_nest_lock_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_nest_lock_t OpenMP data type"
ms.assetid: fceac9fb-96d2-42b0-af19-c9b078380618
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# omp_nest_lock_t
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

잠금에 대 한 정보는 다음으로 보유 하 고 있는 형식: 잠금을 사용할 수 있는 한 스레드의 id를 소유한 잠금 및 중첩 수 있는지 여부입니다.  
  
 다음 함수 사용  **omp\_nest\_lock\_t**:  
  
-   [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)  
  
-   [omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)  
  
-   [omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)  
  
-   [omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)  
  
-   [omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)  
  
 자세한 내용은 [3.2 Lock Functions](../../../parallel/openmp/3-2-lock-functions.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) 를 사용 하는 예에 대 한  **omp\_nest\_lock\_t**.  
  
## 참고 항목  
 [Data Types](../../../parallel/openmp/reference/openmp-data-types.md)