---
title: "Nowait 절을 사용 하 여 A.4 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf910f1223a4ccfdd85734ef9bd314d5664679ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a4---using-the-nowait-clause"></a>A.4   nowait 절 사용
병렬 영역 내부에서는 여러 독립 루프에 있는 경우 사용할 수 있습니다는 `nowait` 절 ([섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지)의 끝에 암시적된 장벽을 방지 하기 위해는 `for` 다음과 같이 지시문:  
  
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