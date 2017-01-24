---
title: "omp_init_nest_lock | Microsoft Docs"
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
  - "omp_init_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_init_nest_lock OpenMP function"
ms.assetid: cf749ec5-de78-4186-9588-ac7c42b02463
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_init_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

잠금을 초기화합니다.  
  
## 구문  
  
```  
void omp_init_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `lock`  
 형식의 변수에 [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md).  
  
## 설명  
 초기 중첩 개수는 0입니다.  
  
 자세한 내용은 [3.2.1 omp\_init\_lock and omp\_init\_nest\_lock Functions](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_init_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t my_lock;  
  
void Test() {  
   int tid = omp_get_thread_num( );  
   omp_set_nest_lock(&my_lock);  
   printf_s("Thread %d - starting nested locked region\n", tid);  
   printf_s("Thread %d - ending nested locked region\n", tid);  
   omp_unset_nest_lock(&my_lock);  
}  
  
int main() {  
   omp_init_nest_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_nest_lock(&my_lock);  
            if (i % 3)   
               Test();  
            omp_unset_nest_lock(&my_lock);  
        }  
    }  
  
    omp_destroy_nest_lock(&my_lock);  
}  
```  
  
  **스레드 0\-중첩 된 시작 영역 잠금**  
**스레드 0\-중첩 된 잠긴된 영역 끝**  
**스레드 0\-중첩 된 시작 영역 잠금**  
**스레드 0\-중첩 된 잠긴된 영역 끝**  
**중첩 된 시작 3\-스레드 지역 잠겨**  
**스레드 종료 3\-잠긴된 영역 중첩**  
**중첩 된 시작 3\-스레드 지역 잠겨**  
**스레드 종료 3\-잠긴된 영역 중첩**  
**중첩 된 시작 3\-스레드 지역 잠겨**  
**스레드 종료 3\-잠긴된 영역 중첩**  
**중첩 된 시작 2\-스레드 지역 잠겨**  
**스레드 종료 2\-잠긴된 영역 중첩**  
**중첩 된 시작 2\-스레드 지역 잠겨**  
**스레드 종료 2\-잠긴된 영역 중첩**  
**중첩 된 시작 2\-스레드 지역 잠겨**  
**스레드 종료 2\-잠긴된 영역 중첩**  
**스레드 1\-중첩 된 시작 영역 잠금**  
**스레드 1\-중첩 된 잠긴된 영역 끝**  
**스레드 1\-중첩 된 시작 영역 잠금**  
**스레드 1\-중첩 된 잠긴된 영역 끝**  
**스레드 1\-중첩 된 시작 영역 잠금**  
**스레드 1\-중첩 된 잠긴된 영역 끝**  
**스레드 0\-중첩 된 시작 영역 잠금**  
**스레드 0\-중첩 된 잠긴된 영역 끝**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)