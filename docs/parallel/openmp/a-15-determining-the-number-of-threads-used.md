---
title: "A.15   Determining the Number of Threads Used | Microsoft Docs"
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
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.15   Determining the Number of Threads Used
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잘못 된 다음 예제를 살펴보십시오 \(에 대 한  [구역 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지\):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 `omp_get_num_threads()` 호출 1을 반환 코드를 직렬 부분에 따라서  *np* 항상 앞의 예제에서 1로 됩니다.  병렬 영역에 배포 되는 스레드 수를 결정 하려면 호출 병렬 영역 내부에 있어야 합니다.  
  
 다음 예제에서는 스레드의 수에 대 한 쿼리를 포함 하지 않고이 프로그램을 다시 작성 하는 방법을 보여 줍니다.  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```