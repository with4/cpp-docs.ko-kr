---
title: "3.2.5 omp_test_lock and omp_test_nest_lock Functions | Microsoft Docs"
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
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.5 omp_test_lock and omp_test_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 함수에 잠금을 설정 하려고 하지만 스레드 실행을 차단 하지 않습니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 인수를 초기화 잠금을 변수에 지정 해야 합니다.  이러한 함수에서와 동일한 방식으로 잠금을 설정 하려고 `omp_set_lock` 및 `omp_set_nest_lock`, 스레드의 실행을 차단 하지 않는 것을 제외 하 고.  
  
 간단한 잠금에 대 한의 `omp_test_lock` 함수는 0이 아닌 반환 값, 잠금을 성공적으로 설정 되 면 그렇지 않은 경우 0을 반환 합니다.  
  
 Nestable 잠금에 대 한의 `omp_test_nest_lock` 함수 반환 값, 잠금을 성공적으로 설정 되 면 새 중첩 개수 계산 그렇지 않은 경우 0을 반환 합니다.