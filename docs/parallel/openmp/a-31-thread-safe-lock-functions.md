---
title: "A.31   Thread-Safe Lock Functions | Microsoft Docs"
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
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.31   Thread-Safe Lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 C\+\+ 예제를 사용 하 여 잠금 병렬 영역에서 배열을 초기화 하는 방법을 보여 줍니다. `omp_init_lock` \([3.2.1 절](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) 페이지 42\).  
  
## 예제  
  
### 코드  
  
```  
// A_13_omp_init_lock.cpp  
// compile with: /openmp  
#include <omp.h>  
  
omp_lock_t *new_locks() {  
   int i;  
   omp_lock_t *lock = new omp_lock_t[1000];  
   #pragma omp parallel for private(i)  
   for (i = 0 ; i < 1000 ; i++)  
      omp_init_lock(&lock[i]);  
  
   return lock;  
}  
  
int main () {}  
```