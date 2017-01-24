---
title: "private (OpenMP) | Microsoft Docs"
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
  - "private"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "private OpenMP clause"
ms.assetid: 772904a2-1345-4562-90e6-eb4dc85aea1a
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# private (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

각 스레드가 자체 인스턴스 변수를 가지도록 지정 합니다.  
  
## 구문  
  
```  
private(var)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`  
 개의 각 스레드에서 인스턴스 변수입니다.  
  
## 설명  
 **개인** 다음과 같은 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 자세한 내용은 [2.7.2.1 private](../../../parallel/openmp/2-7-2-1-private.md)를 참조하십시오.  
  
## 예제  
  
```  
// openmp_private.c  
// compile with: /openmp  
#include <windows.h>  
#include <assert.h>  
#include <stdio.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define SLEEP_THREAD 1  
#define NUM_LOOPS 2  
  
enum Types {  
   ThreadPrivate,  
   Private,  
   FirstPrivate,  
   LastPrivate,  
   Shared,  
   MAX_TYPES  
};  
  
int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};  
int nThreadPrivate;  
  
#pragma omp threadprivate(nThreadPrivate)  
#pragma warning(disable:4700)  
  
int main() {  
   int nPrivate = NUM_THREADS;  
   int nFirstPrivate = NUM_THREADS;  
   int nLastPrivate = NUM_THREADS;  
   int nShared = NUM_THREADS;  
   int nRet = 0;  
   int i;  
   int j;  
   int nLoop = 0;  
  
   nThreadPrivate = NUM_THREADS;  
   printf_s("These are the variables before entry "  
           "into the parallel region.\n");  
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);  
   printf_s("      nPrivate = %d\n", nPrivate);  
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);  
   printf_s("  nLastPrivate = %d\n", nLastPrivate);  
   printf_s("       nShared = %d\n\n", nShared);  
   omp_set_num_threads(NUM_THREADS);  
  
   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)  
   {  
      #pragma omp for schedule(static) lastprivate(nLastPrivate)  
      for (i = 0 ; i < NUM_THREADS ; ++i) {  
         for (j = 0 ; j < NUM_LOOPS ; ++j) {  
            int nThread = omp_get_thread_num();  
            assert(nThread < NUM_THREADS);  
  
            if (nThread == SLEEP_THREAD)  
               Sleep(100);  
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;  
            nSave[nThread][Private][j] = nPrivate;  
            nSave[nThread][Shared][j] = nShared;  
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;  
            nSave[nThread][LastPrivate][j] = nLastPrivate;  
            nThreadPrivate = nThread;  
            nPrivate = nThread;  
            nShared = nThread;  
            nLastPrivate = nThread;  
            --nFirstPrivate;  
         }  
      }  
   }  
  
   for (i = 0 ; i < NUM_LOOPS ; ++i) {  
      for (j = 0 ; j < NUM_THREADS ; ++j) {  
         printf_s("These are the variables at entry of "  
                  "loop %d of thread %d.\n", i + 1, j);  
         printf_s("nThreadPrivate = %d\n",  
                  nSave[j][ThreadPrivate][i]);  
         printf_s("      nPrivate = %d\n",  
                  nSave[j][Private][i]);  
         printf_s(" nFirstPrivate = %d\n",  
                  nSave[j][FirstPrivate][i]);  
         printf_s("  nLastPrivate = %d\n",  
                  nSave[j][LastPrivate][i]);  
         printf_s("       nShared = %d\n\n",  
                  nSave[j][Shared][i]);  
      }  
   }  
  
   printf_s("These are the variables after exit from "  
            "the parallel region.\n");  
   printf_s("nThreadPrivate = %d (The last value in the "  
            "master thread)\n", nThreadPrivate);  
   printf_s("      nPrivate = %d (The value prior to "  
            "entering parallel region)\n", nPrivate);  
   printf_s(" nFirstPrivate = %d (The value prior to "  
            "entering parallel region)\n", nFirstPrivate);  
   printf_s("  nLastPrivate = %d (The value from the "  
            "last iteration of the loop)\n", nLastPrivate);  
   printf_s("       nShared = %d (The value assigned, "  
            "from the delayed thread, %d)\n\n",  
            nShared, SLEEP_THREAD);  
}  
```  
  
  **이러한 변수 앞에 병렬 영역입니다.  nThreadPrivate \= 4**  
 **nPrivate \= 4**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 4**  
 **nShared \= 4**  
**이러한 항목의 스레드 0 1 루프의 변수입니다.  nThreadPrivate \= 4**  
 **nPrivate 1310720 \=**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 1245104**  
 **nShared \= 3**  
**이러한 항목의 루프 1의 스레드 1 변수입니다.  nThreadPrivate \= 4**  
 **nPrivate \= 4488**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 19748**  
 **nShared \= 0**  
**이러한 변수가 루프 1 스레드 2의 항목입니다.  nThreadPrivate \= 4**  
 **nPrivate \=\-132514848**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \=\-513199792**  
 **nShared \= 4**  
**이러한 항목 1 스레드의 3 루프의 변수입니다.  nThreadPrivate \= 4**  
 **nPrivate \= 1206**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 1204**  
 **nShared \= 2**  
**이러한 항목의 스레드 0 2 루프의 변수입니다.  nThreadPrivate \= 0**  
 **nPrivate \= 0**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 0**  
 **nShared \= 0**  
**이러한 항목의 스레드 1 2 루프의 변수입니다.  nThreadPrivate \= 1**  
 **nPrivate \= 1**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 1**  
 **nShared \= 1**  
**이러한 변수가 루프 2의 스레드 2의 항목입니다.  nThreadPrivate \= 2**  
 **nPrivate \= 2**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 2**  
 **nShared \= 2**  
**이러한 항목 2의 스레드 3 루프의 변수입니다.  nThreadPrivate \= 3**  
 **nPrivate \= 3**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 3**  
 **nShared \= 3**  
**이러한 병렬 영역에서 종료 한 후 변수입니다.  nThreadPrivate \= 0 \(마스터 스레드는 마지막 값\)**  
 **nPrivate \= 4 \(병렬 영역을 입력 하기 전에 값\)**  
 **nFirstPrivate \= 4 \(병렬 영역을 입력 하기 전에 값\)**  
 **nLastPrivate \= 3 \(루프의 마지막 반복에서 값\)**  
 **nShared \= 1 \(값이 할당을 지연 된 스레드에서 1\)**    
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)