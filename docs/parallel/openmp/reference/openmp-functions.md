---
title: "OpenMP 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caa41947f43189f52333106f80cce6f58b921f8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="openmp-functions"></a>OpenMP 함수
OpenMP API에서 사용 되는 함수에 대 한 링크를 제공 합니다.  
  
 다음 함수를 포함 하는 표준 OpenMP의 Visual c + + 구현 합니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|잠금을 초기화를 취소 합니다.|  
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|중첩 잠금 초기화를 취소 합니다.|  
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|런타임에서 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 하는 경우를 나타내는 값을 반환 합니다.|  
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|될 경우 병렬 영역 없이 사용할 수 있는 스레드 개수 보다 크거나 같은 정수를 반환 [num_threads](../../../parallel/openmp/reference/num-threads.md) 코드 내에서 해당 지점에서 정의 되었습니다.|  
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|중첩 된 병렬 처리를 사용할 수 있는지 여부를 나타내는 값을 반환 합니다.|  
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|함수를 호출할 때 사용할 수 있는 프로세서 수를 반환 합니다.|  
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|병렬 영역에 스레드 수를 반환합니다.|  
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|해당 스레드 팀 내에서 실행 중인 스레드의 스레드 수를 반환 합니다.|  
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|프로세서 클록 틱 간 시간 (초)을 반환합니다.|  
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|특정 시점에서 경과 된 시간 (초)에서 값을 반환 합니다.|  
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|병렬 영역 내부에서 호출 된 경우 0이 아닌 값을 반환 합니다.|  
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|단순 잠금을 초기화합니다.|  
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|잠금을 초기화합니다.|  
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|실행된 시간까지 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있다는 것을 나타냅니다.|  
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|블록은 잠금의 있을 때까지 실행을 스레드입니다.|  
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|블록은 잠금의 있을 때까지 실행을 스레드입니다.|  
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|중첩 된 병렬 처리가 가능 합니다.|  
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|스레드 수, 후속 병렬 영역에 설정 하 여 덮어쓰지 않는 한는 [num_threads](../../../parallel/openmp/reference/num-threads.md) 절.|  
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.|  
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|중첩 잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.|  
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|잠금을 해제 합니다.|  
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|중첩 잠금을 해제합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 참조](../../../parallel/openmp/reference/openmp-library-reference.md)