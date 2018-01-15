---
title: "3.2.4 omp_unset_lock and omp_unset_nest_lock 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc71c6c31a1d93b6e9c9cce2cd4f7830502a1a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock and omp_unset_nest_lock 함수
이러한 함수는 잠금 소유권을 해제 하는 방법 제공 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 이러한 각 함수에 대 한 인수는 함수를 실행 하는 스레드에서 소유 하는 초기화 된 잠금 변수를 가리켜야 합니다. 스레드가 해당 잠금을 소유 하지 않은 경우 동작이 정의 되지 않습니다.  
  
 간단한 잠금에 대 한는 `omp_unset_lock` 함수는 잠금 소유권에서 함수를 실행 하는 스레드를 해제 합니다.  
  
 중첩 잠금에 대 한는 `omp_unset_nest_lock` 함수는 중첩 개수 및 릴리스 결과 횟수가 0 이면 잠금 소유권에서 함수를 실행 하는 스레드입니다.