---
title: "3.2.4 omp_unset_lock and omp_unset_nest_lock Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.4 omp_unset_lock and omp_unset_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잠금 소유권을 해제 하는 방법 다음이 기능을 제공 합니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 각이 함수 인수 함수 실행 스레드가 소유한 잠금 초기화 변수에 지정 해야 합니다.  스레드에서 잠금을 소유 하지 않는 경우 동작이 정의 되지 않습니다.  
  
 간단한 잠금에 대 한의 `omp_unset_lock` 함수에서 잠금 소유권 함수를 실행 하는 스레드를 해제 합니다.  
  
 Nestable 잠금에 대 한의 `omp_unset_nest_lock` 감소는 중첩 수 및 릴리스 결과 횟수가 0이 되는 경우 잠금 소유권에서 함수를 실행 하는 스레드가 작동 됩니다.