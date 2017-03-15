---
title: "if (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "if OpenMP clause"
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# if (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

직렬 또는 병렬 루프 실행 여부를 지정 합니다.  
  
## 구문  
  
```  
if(expression)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `expression`  
 True \(0이\)로 계산 되는 경우, 동시에 수행 하는 병렬 영역에는 코드에서 발생 정수 식입니다.  식이 false \(0\)가 되 면 병렬 영역 \(단일 스레드에서만\) 일련의 실행 됩니다.  
  
## 설명  
 `if`다음 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
  **val \= 0, 직렬화**  
**val \= 2, 2 스레드를 병렬화**   
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)