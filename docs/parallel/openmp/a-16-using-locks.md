---
title: "A.16   Using Locks | Microsoft Docs"
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
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.16   Using Locks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제에서 \(에 대 한  [섹션 3.2](../../parallel/openmp/3-2-lock-functions.md) 페이지 41\) 잠금 함수 인수 형식이 있어야 한다는 참고 `omp_lock_t`, 그를 플러시할 필요가 없습니다입니다.  잠금 기능으로 인해 스레드가 항목의 첫 번째 중요 한 섹션을 기다리는 동안 유휴 상태로 유지 될 수 있지만 두 항목에 대 한 기다리는 동안 다른 작업을 수행 합니다.  `omp_set_lock` 함수 블록 있지만 해당 `omp_test_lock` 함수 하지 않습니다, skip\(\)에서 해야 할 작업을 허용 합니다.  
  
## 예제  
  
### 코드  
  
```  
// omp_using_locks.c  
// compile with: /openmp /c  
#include <stdio.h>  
#include <omp.h>  
  
void work(int);  
void skip(int);  
  
int main() {  
   omp_lock_t lck;  
   int id;  
  
   omp_init_lock(&lck);  
   #pragma omp parallel shared(lck) private(id)  
   {  
      id = omp_get_thread_num();  
  
      omp_set_lock(&lck);  
      printf_s("My thread id is %d.\n", id);  
  
      // only one thread at a time can execute this printf  
      omp_unset_lock(&lck);  
  
      while (! omp_test_lock(&lck)) {  
         skip(id);   // we do not yet have the lock,  
                     // so we must do something else   
      }  
      work(id);     // we now have the lock  
                    // and can do the work   
      omp_unset_lock(&lck);  
   }  
   omp_destroy_lock(&lck);  
}  
```