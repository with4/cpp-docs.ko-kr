---
title: "master | Microsoft Docs"
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
  - "master"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "master OpenMP directive"
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# master
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

마스터 threadshould만의 프로그램을 실행을 지정 합니다.  
  
## 구문  
  
```  
#pragma omp master  
{  
   code_block  
}  
```  
  
## 설명  
 해당  **마스터** 지시문 OpenMP 절을 지원 합니다.  
  
 [single](../../../parallel/openmp/reference/single.md) 지시문을 사용 하면 코드 부분 마스터 스레드가 아닌 단일 스레드에서 실행 되도록 지정 합니다.  
  
 자세한 내용은 [2.6.1 master Construct](../../../parallel/openmp/2-6-1-master-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_master.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
  
int main( )   
{  
    int a[5], i;  
  
    #pragma omp parallel  
    {  
        // Perform some computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] = i * i;  
  
        // Print intermediate results.  
        #pragma omp master  
            for (i = 0; i < 5; i++)  
                printf_s("a[%d] = %d\n", i, a[i]);  
  
        // Wait.  
        #pragma omp barrier  
  
        // Continue with the computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] += i;  
    }  
}  
```  
  
  **\[0\] \= 0**  
**\[1\] \= 1**  
**\[2\] \= 4**  
**\[3\] \= 9**  
**\[4\] \= 16**   
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)