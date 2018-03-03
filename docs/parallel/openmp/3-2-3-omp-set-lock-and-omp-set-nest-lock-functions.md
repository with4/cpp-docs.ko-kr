---
title: "3.2.3 omp_set_lock and omp_set_nest_lock 함수 | Microsoft Docs"
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
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e709e43a0b32b68bc34c4e76e8680ae371e30670
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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