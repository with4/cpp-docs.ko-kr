---
title: "3.1.6 omp_in_parallel Function | Microsoft Docs"
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
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.6 omp_in_parallel Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Omp\_in\_parallel** 병렬 영역; 병렬로 실행의 동적 범위 내에서 호출 되는 경우 함수를 0이 아닌 값 반환 그렇지 않은 경우 0을 반환합니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 이 함수의 지역 serialize 된 중첩된 영역을 포함 하 여 병렬로 실행 내에서 호출 하면 0이 아닌 값을 반환 합니다.