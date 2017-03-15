---
title: "A.10   Specifying Sequential Ordering | Microsoft Docs"
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
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.10   Specifying Sequential Ordering
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정렬 섹션 \([2.6.6 섹션](../../parallel/openmp/2-6-6-ordered-construct.md) 22 페이지\) 출력 병렬로 수행 되는 작업을 순차적으로 순서 지정에 사용할 수 있습니다.  다음 프로그램을 순서 대로 인덱스 출력.  
  
```  
#pragma omp for ordered schedule(dynamic)  
    for (i=lb; i<ub; i+=st)  
        work(i);  
void work(int k)  
{  
    #pragma omp ordered  
        printf_s(" %d", k);  
}  
```