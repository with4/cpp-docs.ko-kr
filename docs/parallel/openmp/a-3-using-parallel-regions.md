---
title: "병렬 영역을 사용 하 여 A.3 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be3489e924dab7faa50d26c7cb89af67b4034ca5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a3---using-parallel-regions"></a>A.3   병렬 영역 사용
`parallel` 지시문 ([섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 페이지 8) 성긴 병렬 프로그램에서 사용할 수 있습니다. 다음 예제에서는 병렬 영역에서 각 스레드에 결정 배열의 전역 부분 `x` 작업을 스레드 수를 기반으로 합니다.  
  
```  
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)  
{  
    iam = omp_get_thread_num();  
    np =  omp_get_num_threads();  
    ipoints = npoints / np;  
    subdomain(x, iam, ipoints);  
}  
```