---
title: "3.2.1 omp_init_lock and omp_init_nest_lock Functions | Microsoft Docs"
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.1 omp_init_lock and omp_init_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 함수는 lock을 초기화 하는 유일한 수단을 제공 합니다.  각각의 함수 매개 변수와 관련 된 잠금 초기화  *잠금* 후속 호출에 사용 합니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 초기 상태 잠금이 해제 되었습니다 \(즉, 스레드는 잠금을 소유 하 고\).  Nestable 잠금에 대 한 초기 중첩 개수는 0입니다.  이미 초기화 된 잠금 변수를 이러한 루틴 중 하나를 호출 하는 정책 위반입니다.