---
title: "omp_set_dynamic | Microsoft Docs"
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
  - "omp_set_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_dynamic OpenMP function"
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

실행된 시간에 따라 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있는 나타냅니다.  
  
## 구문  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `val`  
 런타임에서 다음 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있는 경우를 나타내는 값입니다.  0이 아닌 경우 0 이면 공용 언어 런타임은 스레드를 조정할 수 있습니다, 런타임 스레드 수를 동적으로 조정 합니다 없습니다.  
  
## 설명  
 스레드 수를 설정 하 값 초과 하지 않아야 합니다 [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 또는 [OMP\_NUM\_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 사용 [omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) 의 현재 설정을 표시 하려면 `omp_set_dynamic`.  
  
 설정에 대 한 `omp_set_dynamic` 의 설정 보다 우선 합니다는 [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) 환경 변수입니다.  
  
 자세한 내용은 [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
  **1**  
**1**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)