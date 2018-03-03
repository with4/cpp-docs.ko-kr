---
title: "Lastprivate 절을 사용 하 여 A.6 | Microsoft Docs"
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
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1744787e1dfb90fa9af93db5dba4eecd600b4334
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   lastprivate 절 사용
경우에 따라 올바르게 실행 루프의 마지막 반복을 변수에 할당 되는 값에 따라 달라 집니다. 이러한 프로그램에 대 한 인수 같은 모든 변수를 나열 해야 합니다.는 `lastprivate` 절 ([2.7.2.3 섹션](../../parallel/openmp/2-7-2-3-lastprivate.md) 페이지 27) 하는 변수의 값 루프 순차적으로 실행 될 때와 동일 합니다.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 위의 예제에서는 값 `i` 병렬 영역의 끝에 용량이 됩니다 `n-1`, 순차적 경우에서.