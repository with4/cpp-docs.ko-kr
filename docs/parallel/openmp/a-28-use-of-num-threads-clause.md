---
title: "A.28   Use of num_threads Clause | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 26238da1-902c-49b4-9559-0fbc9eaf7f36
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.28   Use of num_threads Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제는 `num_threads` 절 \([섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지\).  병렬 영역에 최대 10 개의 스레드를 실행 합니다.  
  
```  
#include <omp.h>  
main()  
{  
    omp_set_dynamic(1);  
    ...  
    #pragma omp parallel num_threads(10)  
    {  
        ... parallel region ...  
    }  
}  
```