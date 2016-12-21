---
title: "for (OpenMP) | Microsoft Docs"
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
  - "for"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for OpenMP directive"
ms.assetid: 8b54e034-9db2-4c1a-a2b1-72e14e930506
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

작업에서 발생 한 스레드 간에 나눌 수 있는 병렬 영역 내부 루프에 대 한.  
  
## 구문  
  
```  
#pragma omp [parallel] for [clauses]  
   for_statement  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `clause`\(선택적 요소\)  
 0 개 이상의 절입니다.  목록에 대 한 설명 부분에서 지원 절을 참조 하십시오.  **에 대 한**.  
  
 `for_statement`  
 루프에 대 한 A입니다.  정의 되지 않은 동작 하면 사용자의 코드를 루프의 인덱스 변수 변경 되.  
  
## 설명  
 **에 대 한** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [에 nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [순서가 지정 된](../../../parallel/openmp/reference/ordered-openmp-directives.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [감소](../../../parallel/openmp/reference/reduction.md)  
  
-   [일정](../../../parallel/openmp/reference/schedule.md)  
  
 경우  **병렬** 도 지정 된 `clause` 어떤 절 여 받아들일 수 있는  **병렬** 또는  **에 대 한** 지시문을 제외 하 고  **에 nowait**.  
  
 자세한 내용은  [2.4.1 구조에 대 한](../../../parallel/openmp/2-4-1-for-construct.md).  
  
## 예제  
  
```  
// omp_for.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <math.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define NUM_START 1  
#define NUM_END 10  
  
int main() {  
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;  
   int nThreads = 0, nTmp = nStart + nEnd;  
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *   
                               unsigned(abs(nTmp))) / 2;  
   int nSumCalc = uTmp;  
  
   if (nTmp < 0)  
      nSumCalc = -nSumCalc;  
  
   omp_set_num_threads(NUM_THREADS);  
  
   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)  
   {  
      #pragma omp master  
      nThreads = omp_get_num_threads();  
  
      #pragma omp for  
      for (i=nStart; i<=nEnd; ++i) {  
            #pragma omp atomic  
            nSum += i;  
      }  
   }  
  
   if  (nThreads == NUM_THREADS) {  
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);  
      nRet = 0;  
   }  
   else {  
      printf_s("Expected %d OpenMP threads, but %d were used.\n",  
               NUM_THREADS, nThreads);  
      nRet = 1;  
   }  
  
   if (nSum != nSumCalc) {  
      printf_s("The sum of %d through %d should be %d, "  
               "but %d was reported!\n",  
               NUM_START, NUM_END, nSumCalc, nSum);  
      nRet = 1;  
   }  
   else  
      printf_s("The sum of %d through %d is %d\n",  
               NUM_START, NUM_END, nSum);  
}  
```  
  
  **4 OpenMP 스레드 사용 되었습니다.  1\-10의 55입니다.**    
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)