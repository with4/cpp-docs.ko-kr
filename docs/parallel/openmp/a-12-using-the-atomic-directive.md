---
title: "원자성 지시문을 사용 하 여 A.12 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9aa619d9bbe635a41d15a39d6c05780a4416520e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a12---using-the-atomic-directive"></a>A.12   atomic 지시문 사용
다음 예제에서는 경합 상태를 방지 (의 요소를 동시에 업데이트할 *x* 여러 스레드에서)를 사용 하 여는 `atomic` 지시문 ([섹션 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) 페이지 19):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 사용 시의 이점은 `atomic` 지시문이이 예제에서 병렬로 발생 하는 x의 서로 다른 두 요소의 업데이트 수 있다는 점입니다. 경우는 `critical` 지시문 ([섹션 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 페이지에서) 다음의 요소를 업데이트 하는 모든 대신, 사용 된 *x* 직렬로 (하지만 하나에 없는 순서를 보장) 실행 합니다.  
  
 `atomic` 지시문은 C 또는 c + + 문 바로 다음에 적용 됩니다.  결과적으로 요소의 *y* 이 예제에서 자동으로 업데이트 되지 않습니다.