---
title: "A.5   Using the critical Directive | Microsoft Docs"
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
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.5   Using the critical Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제에서는 몇 가지 포함 되어 있습니다. `critical` 지시문 \([섹션 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 페이지\).  이 예제에서는 작업 되 고 큐에서 제거 작업 큐 모델을 보여 줍니다.  여러 스레드가 동일한 작업 큐에 대 한 보호 작업을 큐에 수 있습니다는 `critical` 섹션입니다.  이 예제에서는 두 개의 큐 아니기 때문에 의해 보호 됩니다 `critical` 지시문 이름이 다른  *xaxis* 및  *yaxis*.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```