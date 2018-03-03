---
title: "병렬 구역 지정 A.8 | Microsoft Docs"
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
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db7decc4efb1a3f6bb457623489c84e0ad1ae1f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Parallel Sections 지정
다음 예에서 (에 대 한 [섹션 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) 페이지 14) 함수 *xaxis*, *yaxis*, 및 *zaxis* 동시에 실행할 수 있습니다. 첫 번째 `section` 지시문은 선택 사항입니다.  모든 `section` 지시문의 어휘 범위에 표시할 필요는 `parallel sections` 생성 합니다.  
  
```  
#pragma omp parallel sections  
{  
    #pragma omp section  
        xaxis();  
    #pragma omp section  
        yaxis();  
    #pragma omp section  
        zaxis();  
}  
```