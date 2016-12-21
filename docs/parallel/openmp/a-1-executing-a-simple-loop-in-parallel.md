---
title: "A.1   Executing a Simple Loop in Parallel | Microsoft Docs"
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
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.1   Executing a Simple Loop in Parallel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제에서는 사용 하는 단순한 루프를 병렬화 하는 `parallel for` 지시문 \([섹션 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) 16 페이지\).  루프 반복 변수는 기본적으로 private 이므로 개인 절에 명시적으로 지정할 필요가 없습니다.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```