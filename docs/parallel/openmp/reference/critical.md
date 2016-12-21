---
title: "critical | Microsoft Docs"
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
  - "Critical"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "critical OpenMP directive"
ms.assetid: 2ab87d6d-5ca4-43ae-9f0a-1f517a6a2bab
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# critical
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

코드입니다만 실행 하도록 스레드를 한 번에 지정 됩니다.  
  
## 구문  
  
```  
#pragma omp critical [(name)]  
{  
   code_block  
}  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 \(`name`\) \(optional\)  
 중요 한 코드를 식별 하는 이름입니다.  Note이 이름을 괄호로 묶어야 합니다.  
  
## 설명  
 **중요 한** 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 [2.6.2 critical Construct](../../../parallel/openmp/2-6-2-critical-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_critical.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
#define SIZE 10  
  
int main()   
{  
    int i;  
    int max;  
    int a[SIZE];  
  
    for (i = 0; i < SIZE; i++)   
    {  
        a[i] = rand();  
        printf_s("%d\n", a[i]);  
    }  
  
    max = a[0];  
    #pragma omp parallel for num_threads(4)  
        for (i = 1; i < SIZE; i++)   
        {  
            if (a[i] > max)  
            {  
                #pragma omp critical  
                {  
                    // compare a[i] and max again because max   
                    // could have been changed by another thread after   
                    // the comparison outside the critical section  
                    if (a[i] > max)  
                        max = a[i];  
                }  
            }  
        }  
  
    printf_s("max = %d\n", max);  
}  
```  
  
  **41**  
**18467**  
**6334**  
**26500**  
**19169**  
**15724**  
**11478**  
**29358**  
**26962**  
**24464**  
**29358 max \=**   
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)