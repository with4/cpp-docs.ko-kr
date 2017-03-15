---
title: "omp_init_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_init_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_init_lock OpenMP function"
ms.assetid: 7a65e3e2-2e31-4645-964c-c1e82e2a4d0e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# omp_init_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

간단한 잠금을 초기화합니다.  
  
## 구문  
  
```  
void omp_init_lock(  
   omp_lock_t *lock  
);  
```  
  
#### 매개 변수  
 `lock`  
 형식의 변수에 [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md).  
  
## 설명  
 자세한 내용은 [3.2.1 omp\_init\_lock and omp\_init\_nest\_lock Functions](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_init_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t my_lock;  
  
int main() {  
   omp_init_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num( );  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_lock(&my_lock);  
         printf_s("Thread %d - starting locked region\n", tid);  
         printf_s("Thread %d - ending locked region\n", tid);  
         omp_unset_lock(&my_lock);  
      }  
   }  
  
   omp_destroy_lock(&my_lock);  
}  
```  
  
  **스레드 시작 0\-지역 잠겨**  
**0\-잠긴 종료 스레드 지역**  
**스레드 시작 0\-지역 잠겨**  
**0\-잠긴 종료 스레드 지역**  
**스레드 시작 0\-지역 잠겨**  
**0\-잠긴 종료 스레드 지역**  
**스레드 시작 0\-지역 잠겨**  
**0\-잠긴 종료 스레드 지역**  
**스레드 시작 0\-지역 잠겨**  
**0\-잠긴 종료 스레드 지역**  
**스레드 1 시작\-지역 잠겨**  
**잠긴 끝나는 1\-스레드 지역**  
**스레드 1 시작\-지역 잠겨**  
**잠긴 끝나는 1\-스레드 지역**  
**스레드 1 시작\-지역 잠겨**  
**잠긴 끝나는 1\-스레드 지역**  
**스레드 1 시작\-지역 잠겨**  
**잠긴 끝나는 1\-스레드 지역**  
**스레드 1 시작\-지역 잠겨**  
**잠긴 끝나는 1\-스레드 지역**  
**스레드 시작 2\-지역 잠겨**  
**잠긴 스레드 종료 2\-지역**  
**스레드 시작 2\-지역 잠겨**  
**잠긴 스레드 종료 2\-지역**  
**스레드 시작 2\-지역 잠겨**  
**잠긴 스레드 종료 2\-지역**  
**스레드 시작 2\-지역 잠겨**  
**잠긴 스레드 종료 2\-지역**  
**스레드 시작 2\-지역 잠겨**  
**잠긴 스레드 종료 2\-지역**  
**스레드 시작 3\-영역 잠금**  
**잠긴 스레드 종료 3\-지역**  
**스레드 시작 3\-영역 잠금**  
**잠긴 스레드 종료 3\-지역**  
**스레드 시작 3\-영역 잠금**  
**잠긴 스레드 종료 3\-지역**  
**스레드 시작 3\-영역 잠금**  
**잠긴 스레드 종료 3\-지역**  
**스레드 시작 3\-영역 잠금**  
**잠긴 스레드 종료 3\-지역**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)