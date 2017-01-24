---
title: "omp_get_wtime | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_wtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_wtime OpenMP function"
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_wtime
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

특정 지점에서 값의 시간 \(초\)에서 경과 된 시간을 반환 합니다.  
  
## 구문  
  
```  
double omp_get_wtime( );  
```  
  
## 반환 값  
 일부 임의 했지만 일관성 있는 시점에서 값의 시간 \(초\)에서 경과 된 시간을 반환 합니다.  
  
## 설명  
 해당 지점 이후의 비교 수 있으므로 프로그램 실행 하는 동안 일관성을 유지 합니다.  
  
 자세한 내용은 [3.3.1 omp\_get\_wtime Function](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
  **시작 \= 594255.3671159324**  
**끝 \= 594256.3664474116**  
**diff 0.9993314791936427 \=**  
**wtick \= 2.793651148400146e\-007**  
**1\/wtick \= 3579545**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)