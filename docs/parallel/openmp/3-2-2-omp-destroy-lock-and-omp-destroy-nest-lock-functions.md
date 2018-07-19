---
title: 3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33c21ec9ca07651480748ac705ea6b9e4dcf8e94
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686297"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수
이러한 함수 되도록 뾰족한는 잠금 변수에 *잠금* 초기화 되지 않았습니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 이러한 루틴 초기화 되지 않았거나 잠금 해제는 잠금 변수 중 하나를 호출 하는 정책을 준수 하지 않는 경우