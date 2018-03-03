---
title: "3.2.1 omp_init_lock and omp_init_nest_lock 함수 | Microsoft Docs"
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3802822465d6527e4c98a0be6a8c274d767b0f52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock and omp_init_nest_lock 함수
이러한 함수는 잠금을 초기화 하는 유일한 방법은 제공 합니다. 각 함수는 매개 변수와 관련 된 잠금 초기화 *잠금* 후속 호출에서 사용 하도록 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 초기 상태를 잠금 해제 되어 (즉, 소유 하는 스레드가 잠금을). 중첩 잠금 초기 중첩 개수는 0입니다. 이러한 루틴은 이미 초기화 되었습니다 잠금 변수 중 하나를 호출 하는 정책을 준수 하지 않는 경우