---
title: A.1 한 간단한 반복을 병렬로 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b2fbac6ce31d2dbc56a4ef6d9fe87c14d5ee16
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686128"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   병렬로 단일 루프 실행
다음 예제에서는 사용 하 여 간단한 루프를 병렬화 하는 `parallel for` 지시문 ([2.5.1 섹션](../../parallel/openmp/2-5-1-parallel-for-construct.md) 페이지 16). 루프 반복 변수 기본적으로 private 이므로 개인 절에 명시적으로 지정할 필요는 없습니다.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```