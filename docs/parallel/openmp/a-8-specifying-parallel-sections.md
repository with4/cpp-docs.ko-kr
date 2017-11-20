---
title: "병렬 구역 지정 A.8 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d369c2e3a0d326ab4c835a30681f3dbe50f789f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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