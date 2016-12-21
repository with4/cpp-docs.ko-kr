---
title: "3.2.3 omp_set_lock and omp_set_nest_lock Functions | Microsoft Docs"
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
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.3 omp_set_lock and omp_set_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 각 함수 지정한 잠금 사용할 수 있으며 다음 잠금을 설정 될 때까지 함수를 실행 하는 스레드를 차단 합니다.  간단한 잠금 잠금이 해제 된 경우에 사용할 수 있습니다.  Nestable 잠금 잠긴 경우 또는 함수 실행 스레드에 의해 이미 소유 하는 경우 사용할 수 있습니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 간단한 잠금 인수에 대 한의 `omp_set_lock` 함수는 초기화 잠금을 변수를 가리켜야 합니다.  잠금 소유권 함수를 실행 하는 스레드를 부여 됩니다.  
  
 Nestable 잠금 인수에 대 한의 `omp_set_nest_lock` 함수는 초기화 잠금을 변수를 가리켜야 합니다.  중첩 수가 증가 하 고 스레드 허용 됩니다 또는 잠금 소유권을 유지 합니다.