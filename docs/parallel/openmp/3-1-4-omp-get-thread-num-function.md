---
title: "3.1.4 omp_get_thread_num Function | Microsoft Docs"
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
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.4 omp_get_thread_num Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_thread_num` 함수가 스레드 수, 해당 팀 내에서 함수를 실행 하는 스레드를 반환 합니다.  스레드 번호 첫 부분이 0 사이 및  **omp\_get\_num\_threads\(\)**\-1 까지입니다.  마스터 스레드는 팀의 스레드 0입니다.  
  
 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 직렬 지역에서 호출 하는 경우 `omp_get_thread_num` 0을 반환 합니다.  연속 되는 중첩 된 병렬 영역 내에서 호출 하는 경우이 함수는 0을 반환 합니다.  
  
## 상호 참조:  
  
-   `omp_get_num_threads`작동, 참조 하십시오  [구역 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지입니다.