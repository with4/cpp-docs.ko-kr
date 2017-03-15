---
title: "omp_test_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_test_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_lock OpenMP function"
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# omp_test_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

잠금을 설정 하려면 시도 하지만 스레드 실행을 차단 하지 않습니다.  
  
## 구문  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `lock`  
 형식의 변수에 [omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) 로 초기화 된 [omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## 설명  
 자세한 내용은 [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
  **획득 한 스레드 1\-simple\_lock**  
**스레드 해제 1\-simple\_lock**  
**스레드 0\-simple\_lock 획득 하지 못했습니다.**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**스레드 0\-simple\_lock 획득 하지 못했습니다.**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**획득 한 스레드 2\-simple\_lock**  
**스레드 0\-simple\_lock 획득 하지 못했습니다.**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**스레드 0\-simple\_lock 획득 하지 못했습니다.**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**스레드 발표 2\-simple\_lock**  
**스레드 0\-simple\_lock 획득 하지 못했습니다.**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**획득 한 스레드 0\-simple\_lock**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**출시 된 스레드 0\-simple\_lock**  
**Simple\_lock를 가져올 수 없습니다 3\-스레드**  
**획득 한 스레드 3\-simple\_lock**  
**스레드 해제 3\-simple\_lock**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)