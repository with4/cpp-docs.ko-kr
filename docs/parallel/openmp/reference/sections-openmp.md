---
title: "sections (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "section"
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sections OpenMP directive"
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# sections (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

모든 스레드 간에 나눌 수 있는 코드 섹션을 식별 합니다.  
  
## 구문  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `clause`\(선택적 요소\)  
 0 개 이상의 절입니다.  목록에 대 한 설명 부분에서 지원 절을 참조 하십시오.  **섹션**.  
  
## 설명  
 해당  **섹션** 지시문에 0 개 이상 포함 될 수 있습니다  **섹션** 지시문입니다.  
  
 **섹션** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 경우  **병렬** 도 지정 된 `clause` 어떤 절 여 받아들일 수 있는  **병렬** 또는  **섹션** 지시문을 제외 하 고 `nowait`.  
  
 자세한 내용은 [2.4.2 sections Construct](../../../parallel/openmp/2-4-2-sections-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
  **안녕하세요 스레드 0에서**  
**안녕하세요 스레드 0에서**   
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)