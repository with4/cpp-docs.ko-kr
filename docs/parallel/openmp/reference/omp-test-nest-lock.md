---
title: "omp_test_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_test_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_nest_lock OpenMP function"
ms.assetid: 4c909bbe-80e0-4100-aca6-d415d7dc5294
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# omp_test_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Nestable 잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.  
  
## 구문  
  
```  
int omp_test_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `lock`  
 형식의 변수에 [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) 로 초기화 된 [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## 설명  
 자세한 내용은 [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_test_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t nestable_lock;      
  
int main() {  
   omp_init_nest_lock(&nestable_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num();  
      while (!omp_test_nest_lock(&nestable_lock))  
         printf_s("Thread %d - failed to acquire nestable_lock\n",  
                tid);  
  
      printf_s("Thread %d - acquired nestable_lock\n", tid);  
  
      if (omp_test_nest_lock(&nestable_lock)) {  
         printf_s("Thread %d - acquired nestable_lock again\n",  
                tid);  
         printf_s("Thread %d - released nestable_lock\n",   
                tid);  
         omp_unset_nest_lock(&nestable_lock);  
      }  
  
      printf_s("Thread %d - released nestable_lock\n", tid);  
      omp_unset_nest_lock(&nestable_lock);  
   }  
  
   omp_destroy_nest_lock(&nestable_lock);  
}  
```  
  
  **획득 한 스레드 1\-nestable\_lock**  
**스레드 0\-nestable\_lock 획득 하지 못했습니다.**  
**스레드 1\-취득 nestable\_lock 다시**  
**스레드 0\-nestable\_lock 획득 하지 못했습니다.**  
**스레드 해제 1\-nestable\_lock**  
**스레드 0\-nestable\_lock 획득 하지 못했습니다.**  
**스레드 해제 1\-nestable\_lock**  
**스레드 0\-nestable\_lock 획득 하지 못했습니다.**  
**획득 한 스레드 3\-nestable\_lock**  
**스레드 0\-nestable\_lock 획득 하지 못했습니다.**  
**3\-다시 획득 한 nestable\_lock 스레드**  
**스레드 0\-nestable\_lock 획득 하지 못했습니다.**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**스레드 해제 3\-nestable\_lock**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**스레드 해제 3\-nestable\_lock**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**획득 한 스레드 0\-nestable\_lock**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**획득 한 스레드 0\-nestable\_lock 다시**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**출시 된 스레드 0\-nestable\_lock**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**출시 된 스레드 0\-nestable\_lock**  
**Nestable\_lock를 가져올 수 없습니다 2\-스레드**  
**획득 한 스레드 2\-nestable\_lock**  
**획득 한 스레드 2\-nestable\_lock 다시**  
**스레드 발표 2\-nestable\_lock**  
**스레드 발표 2\-nestable\_lock**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)