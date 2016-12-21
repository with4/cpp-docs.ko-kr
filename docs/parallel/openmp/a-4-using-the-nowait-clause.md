---
title: "A.4   Using the nowait Clause | Microsoft Docs"
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
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.4   Using the nowait Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

병렬 영역 내에서 여러 개의 독립 루프가 있는 경우 사용할 수 있습니다의 `nowait` 절 \([섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지\) 끝에 있는 암시적된 장애물을 피하기 위해의 `for` 지시문을 다음과 같습니다:  
  
```  
#pragma omp parallel  
{  
    #pragma omp for nowait  
        for (i=1; i<n; i++)  
             b[i] = (a[i] + a[i-1]) / 2.0;  
    #pragma omp for nowait  
        for (i=0; i<m; i++)  
            y[i] = sqrt(z[i]);  
}  
```