---
title: 사용 하 여 단일 지시문 A.9 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc0e0e08b0b7bdea05bf4c627ae33cc42298c6dc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="a9---using-single-directives"></a>A.9   single 지시문 사용
다음 예제는 `single` 지시문 ([섹션 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) 페이지 15). 예제에서는 하나의 스레드만 (경험 하는 첫 번째 스레드가 일반적으로 `single` 지시문)는 진행률 메시지를 인쇄 합니다. 사용자는 스레드를 실행 하도록 가정 하면 안는 `single` 섹션. 다른 모든 스레드를 건너뜁니다 고 `single` 섹션 및 끝날 때 장벽에 중지는 `single` 생성 합니다. 다른 스레드에서 실행 중인 스레드의 기다리지 않고 계속 진행할 수 있습니다는 `single` 섹션은 `nowait` 절에 지정할 수는 `single` 지시문입니다.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```