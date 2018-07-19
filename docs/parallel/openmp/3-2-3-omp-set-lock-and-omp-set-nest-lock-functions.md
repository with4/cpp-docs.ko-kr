---
title: 3.2.3 omp_set_lock and omp_set_nest_lock 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba24e923051eb887db2a81c1d9765d31a4ef7b24
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689716"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock and omp_set_nest_lock 함수
이러한 각 함수는 지정 된 잠금은 ´ ï ´ 다음 잠금을 설정 될 때까지 함수를 실행 하는 스레드를 차단 합니다. 잠금이 해제 된 경우 단순 잠금을 ´ ù. 잠겨 있지 또는 함수를 실행 하는 스레드에 의해 이미 소유 하는 경우 중첩 잠금 ´ ù. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 간단한 잠금에 대 한 인수는 `omp_set_lock` 함수 초기화 된 잠금 변수를 가리켜야 합니다. 잠금 소유권 함수를 실행 하는 스레드에 부여 됩니다.  
  
 중첩 잠금에 대 한 인수는 `omp_set_nest_lock` 함수 초기화 된 잠금 변수를 가리켜야 합니다. 중첩 수 증가 하 고 스레드가 권한이 부여 되는지 또는 잠금 소유권을 갖고 있습니다.