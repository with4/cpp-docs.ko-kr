---
title: "잠금을 사용 하 여 A.16 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 612abe97de27b179f710b2b09811535829885c5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a16---using-locks"></a>A.16   Locks 사용
다음 예에서 (에 대 한 [섹션 3.2](../../parallel/openmp/3-2-lock-functions.md) 페이지 41) 잠금 함수에 인수 형식에 있어야 하는 참고 `omp_lock_t`, 올바르고 플러시 필요가 없습니다.  잠금 기능으로 인해 스레드가 첫 번째 중요 섹션에 항목을 기다리는 동안 유휴 상태가 될 수 있지만 두 번째 항목을 기다리는 동안 다른 작업을 수행할 수입니다.  `omp_set_lock` 함수 블록 이지만 `omp_test_lock` 함수는 작업을 수행 해야 하는 skip()에서 허용 하지 않습니다.  
  
## <a name="example"></a>예  
  
### <a name="code"></a>코드  
  
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