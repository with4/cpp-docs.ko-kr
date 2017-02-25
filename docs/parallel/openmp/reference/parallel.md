---
title: "parallel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "parallel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parallel OpenMP directive"
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# parallel
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

여러 스레드에서 동시에 실행 되는 코드는 병렬 영역을 정의 합니다.  
  
## 구문  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `clause`\(선택적 요소\)  
 0 개 이상의 절입니다.  목록에 대 한 설명 부분에서 지원 절을 참조 하십시오.  **병렬**.  
  
## 설명  
 해당  **병렬** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num\_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **병렬**  함께 사용할 수 있습니다에서 [sections](../../../parallel/openmp/reference/sections-openmp.md) 및 [for](../../../parallel/openmp/reference/for-openmp.md) 지시문입니다.  
  
 자세한 내용은 [2.3 parallel Construct](../../../parallel/openmp/2-3-parallel-construct.md)를 참조하십시오.  
  
## 예제  
 다음 샘플 스레드 수를 설정 하 고 병렬 영역을 정의 하는 방법을 보여 줍니다.  기본적으로 스레드 시스템에서 논리 프로세서 수를 같습니다.  예를 들어, 하이퍼스레딩을 사용할 수 있는 하나의 물리적 프로세서에 있는 컴퓨터의 경우 두 개의 논리 프로세서와 두 개의 스레드를 해야 합니다.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
  **안녕하세요 스레드 0에서**  
**안녕하세요 스레드 1에서**  
**안녕하세요 스레드 2에서**  
**안녕하세요에서 스레드 3**   
## 주석  
 출력 순서 다른 시스템에서 다를 수 있습니다 노트.  
  
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)