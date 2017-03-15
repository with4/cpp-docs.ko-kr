---
title: "OpenMP Functions | Microsoft Docs"
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
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Functions
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API에 사용 되는 함수에 대 한 링크를 제공 합니다.  
  
 Visual C\+\+ 구현 표준 openmp는 다음 기능을 포함합니다.  
  
|Function|설명|  
|--------------|--------|  
|[omp\_destroy\_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|잠금을 초기화 하지 않습니다.|  
|[omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Nestable 잠금을 초기화 하지 않습니다.|  
|[omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|실행된 시간에 따라 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있는 경우를 나타내는 값을 반환 합니다.|  
|[omp\_get\_max\_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|스레드 병렬 영역 없이 하는 경우 사용할 수 있는 것 이상의 정수를 반환 합니다. [num\_threads](../../../parallel/openmp/reference/num-threads.md) 코드에 정의 된 시점입니다.|  
|[omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md)|중첩 된 병렬 처리 가능 여부를 나타내는 값을 반환 합니다.|  
|[omp\_get\_num\_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|이 함수를 호출할 때 사용할 수 있는 프로세서의 수를 반환 합니다.|  
|[omp\_get\_num\_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|병렬 영역에 스레드 수를 반환합니다.|  
|[omp\_get\_thread\_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|스레드가 스레드 팀 내의 실행 스레드 수를 반환 합니다.|  
|[omp\_get\_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|초 사이의 프로세서 클록 틱 수를 반환합니다.|  
|[omp\_get\_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|특정 지점에서 값의 시간 \(초\)에서 경과 된 시간을 반환 합니다.|  
|[omp\_in\_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|병렬 영역 내에서 호출 하는 경우 0이 아닌 값을 반환 합니다.|  
|[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)|간단한 잠금을 초기화합니다.|  
|[omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|잠금을 초기화합니다.|  
|[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|실행된 시간에 따라 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있는 나타냅니다.|  
|[omp\_set\_lock](../../../parallel/openmp/reference/omp-set-lock.md)|잠금을 사용할 수 있을 때까지 실행 스레드를 차단.|  
|[omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|잠금을 사용할 수 있을 때까지 실행 스레드를 차단.|  
|[omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md)|중첩 된 병렬 처리 가능 합니다.|  
|[omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|재정의 하지 않으면 스레드 후속 병렬 영역에 설정 된 [num\_threads](../../../parallel/openmp/reference/num-threads.md) 절.|  
|[omp\_test\_lock](../../../parallel/openmp/reference/omp-test-lock.md)|잠금을 설정 하려면 시도 하지만 스레드 실행을 차단 하지 않습니다.|  
|[omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Nestable 잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.|  
|[omp\_unset\_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|에 잠금을 해제합니다.|  
|[omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Nestable 잠금을 해제합니다.|  
  
## 참고 항목  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)