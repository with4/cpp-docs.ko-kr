---
title: "(OpenMP)에 대 한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- for
dev_langs:
- C++
helpviewer_keywords:
- for OpenMP directive
ms.assetid: 8b54e034-9db2-4c1a-a2b1-72e14e930506
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab923dd43dfb29a458d12f57eb1ceefdb5539daf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="for-openmp"></a>for (OpenMP)
수행 된 작업을 발생 한 스레드 간에 나눠집니다 병렬 영역 내부 루프에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp [parallel] for [clauses]  
   for_statement  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `clause`(선택 사항)  
 0 개 이상의 절입니다. 지 원하는 절을 목록에 대 한 설명 섹션을 참조 **에 대 한**합니다.  
  
 `for_statement`  
 루프에 대 한 A입니다. 사용자 코드에서 정의 되지 않은 동작이 발생 합니다는 루프 인덱스 변수를 변경 합니다.  
  
## <a name="remarks"></a>설명  
 **에 대 한** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [schedule](../../../parallel/openmp/reference/schedule.md)  
  
 경우 **병렬** 도 지정 `clause` 모든 절에 허용 될 수는 **병렬** 또는 **에 대 한** 지시문을 제외 하 고 **nowait**.  
  
 자세한 내용은 참조 [2.4.1 for 구문](../../../parallel/openmp/2-4-1-for-construct.md)합니다.  
  
## <a name="example"></a>예  
  
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
  
```Output  
4 OpenMP threads were used.  
The sum of 1 through 10 is 55  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)