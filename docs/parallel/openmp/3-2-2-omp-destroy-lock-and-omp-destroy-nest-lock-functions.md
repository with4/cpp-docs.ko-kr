---
title: "3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d0b91fd311581235a893a0b3f4f383e724f9aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수
이러한 함수 되도록 뾰족한는 잠금 변수에 *잠금* 초기화 되지 않았습니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 이러한 루틴 초기화 되지 않았거나 잠금 해제는 잠금 변수 중 하나를 호출 하는 정책을 준수 하지 않는 경우