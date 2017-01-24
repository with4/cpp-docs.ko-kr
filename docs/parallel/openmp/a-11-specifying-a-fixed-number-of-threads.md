---
title: "A.11   Specifying a Fixed Number of Threads | Microsoft Docs"
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
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.11   Specifying a Fixed Number of Threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일부 프로그램이 제대로 실행 스레드 수를 고정, 미리 지정한 숫자에 의존 합니다.  구현이 정의 된 스레드의 수를 동적 조정에 대 한 기본 설정 이기 때문에 동적 스레드 기능을 해제 하 고 명시적으로 이식성을 보장 하는 스레드 수를 설정 하려면 이러한 프로그램을 선택할 수 있습니다.  다음 예제를 사용 하 여이 작업을 수행 하는 방법을 보여 줍니다. `omp_set_dynamic` \([섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에\), 및 `omp_set_num_threads` \([3.1.1 구역](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지\):  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 이 예제에서는 16 스레드에 의해 실행 되는 경우 정확 하 게 프로그램을 실행 합니다.  구현 16 스레드를 지원할 수 없는 경우 동작이 예제에는 구현 시 정의 됩니다.  
  
 병렬 영역 실행 스레드 수를 동적 스레드 설정에 관계 없이 병렬 영역에는 동안 그대로 유지 됩니다.  동적 스레드 메커니즘 병렬 영역을 시작할 때 사용 하는 스레드 수를 결정 하 고 일정 기간 동안 지역 유지 합니다.