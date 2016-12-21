---
title: "3.3.1 omp_get_wtime Function | Microsoft Docs"
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
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.1 omp_get_wtime Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_wtime` 함수 반환 이중 정밀도 부동 소수점 값 경과 된 벽 시계 시간 이후 일부 "시간 이전에 는" \(초\)에서입니다.  실제 "시간" 과거에서 이지만 응용 프로그램을 실행 하는 동안 변경 하지 않도록 보장 됩니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 함수는 다음 예제와 같이 경과 된 시간을 측정 합니다 사용 됩니다 것으로 예상 됩니다.  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 반환 되는 시간 "스레드 단위 시간"은 전체적으로 일관 된 응용 프로그램에 참여 하는 모든 스레드 간 수 하지 않아도 의미에서입니다.