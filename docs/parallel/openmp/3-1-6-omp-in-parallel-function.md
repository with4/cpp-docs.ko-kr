---
title: 3.1.6 omp_in_parallel 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22b491695d2ae49336d7d8998af64e724f344d87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686284"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 함수
**omp_in_parallel** 함수 병렬로 실행 되는 병렬 영역 동적 범위 내에서 호출 되 면 0이 아닌 값을 반환; 그렇지 않으면 0을 반환 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 이 함수는 serialize 되는 중첩 된 영역을 포함 하 여 병렬로 실행 되는 영역 내에서 호출 하는 경우 0이 아닌 값을 반환 합니다.