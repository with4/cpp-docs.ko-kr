---
title: 중요 한 지시문을 사용 하 여 A.5 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1a41e9664faaca24b6708c737a044828eb460bd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="a5---using-the-critical-directive"></a>A.5   critical 지시문 사용
다음 예제에서는 몇 개가 포함 되어 `critical` 지시문 ([섹션 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 페이지에서). 이 예제에서는 작업 큐에서 제거 되 고 작업 큐 모델을 보여 줍니다. 여러 스레드에서 동일한 작업 큐를 방지 하려면 큐 해제 작업에 있어야는 `critical` 섹션. 이 예에서 두 개의 큐는 독립적 이므로, 보호 `critical` 다른 이름의 지시문 *xaxis* 및 *yaxis*합니다.  
  
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