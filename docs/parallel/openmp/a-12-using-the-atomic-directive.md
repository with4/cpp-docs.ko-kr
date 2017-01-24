---
title: "A.12   Using the atomic Directive | Microsoft Docs"
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
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.12   Using the atomic Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음은 경합 상태를 피할 수 \(동시 업데이트 요소의  *x* 여러 스레드에서\)를 사용 하 여는 `atomic` 지시문 \([섹션 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) 19 페이지\):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 사용 하는 장점은 `atomic` 이 예제에서는 지시문이이 업데이트 하는 동시에 발생 하는 x의 서로 다른 요소를 두 개 있습니다.  경우는 `critical` 지시문 \([2.6.2 섹션](../../parallel/openmp/2-6-2-critical-construct.md) 18 페이지\)의 요소를 모두 업데이트 한 다음 대신 사용 된  *x* 직렬로 \(어떤에 순서를 보장할 것\) 실행 될 것입니다.  
  
 참고 해당 `atomic` 지시문 바로 그 다음만 C 또는 C\+\+ 문으로 적용 됩니다.  요소는 결과  *y* 이 예제에서는 자동으로 업데이트 되지 않습니다.