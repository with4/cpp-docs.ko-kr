---
title: Num_threads 절 A.28 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26238da1-902c-49b4-9559-0fbc9eaf7f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12289192d056acac684f28712ccf2aa1423b6c3e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="a28---use-of-numthreads-clause"></a>A.28   num_threads 절 사용
다음 예제는 `num_threads` 절 ([섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에). 병렬 영역 최대 10 개 스레드가 실행 됩니다.  
  
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