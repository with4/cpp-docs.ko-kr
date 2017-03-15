---
title: "3.2.2 omp_destroy_lock and omp_destroy_nest_lock Functions | Microsoft Docs"
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
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.2 omp_destroy_lock and omp_destroy_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 함수는 뾰족한 변수 잠금 확인  *잠금* 초기화 되지 않았습니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 이 루틴에 초기화 되지 않은 잠금이 해제 되거나 잠금 변수 중 하나를 호출 하는 정책 위반입니다.