---
title: "OpenMP Environment Variables | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OpenMP Environment Variables
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API에 사용 되는 환경 변수에 대 한 링크를 제공 합니다.  
  
 Visual C\+\+ 표준 OpenMP 구현 다음 환경 변수를 포함합니다.  프로그램을 시작할 때 이러한 환경 변수 읽기 및 해당 값에 대 한 수정 런타임에 무시 됩니다 \(예를 들어,를 사용 하 여 [\_putenv, \_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)\).  
  
|환경 변수|설명|  
|-----------|--------|  
|[OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|실행 시간 OpenMP 병렬 영역에 스레드 수를 조정할 수 있는지 여부를 지정 합니다.|  
|[OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md)|중첩 된 병렬 처리 활성화 또는 비활성화를 하지 않으면 중첩 된 병렬 처리를 사용할지 여부를 지정 `omp_set_nested`.|  
|[OMP\_NUM\_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|최대 스레드 병렬 영역에 의해 재정의 되지 않으면 설정 하는 [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 또는 [num\_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP\_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|동작을 수정 하는 [schedule](../../../parallel/openmp/reference/schedule.md) 절 때 `schedule(runtime)` 에 지정 된는 `for` 또는 `parallel for` 지시문.|  
  
## 참고 항목  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)