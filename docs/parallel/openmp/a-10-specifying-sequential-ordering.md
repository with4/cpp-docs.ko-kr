---
title: "순차적 순서 지정 하는 a. 10 | Microsoft Docs"
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
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0afa88da12a14bafbba5b431fab045a19e4dedf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a10---specifying-sequential-ordering"></a>A.10   순차적 정렬 지정
정렬 섹션 ([섹션 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 페이지 22) 순차적으로 동시에 수행 된 작업에 출력을 정렬 하는 데 유용 합니다. 다음 프로그램은 인덱스 순서 대로 인쇄합니다.  
  
```  
#pragma omp for ordered schedule(dynamic)  
    for (i=lb; i<ub; i+=st)  
        work(i);  
void work(int k)  
{  
    #pragma omp ordered  
        printf_s(" %d", k);  
}  
```