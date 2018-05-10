---
title: OpenMP 환경 변수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02248b7725f2a4312f26984c798e7248463d2615
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-environment-variables"></a>OpenMP 환경 변수
OpenMP API에서 사용 되는 환경 변수에 대 한 링크를 제공 합니다.  
  
 다음과 같은 환경 변수를 포함 하는 표준 OpenMP의 Visual c + + 구현 합니다. 이러한 환경 변수는 프로그램 시작 시 읽히고 해당 값의 수정 사항을 런타임 시 무시 됩니다 (예를 들어를 사용 하 여 [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).  
  
|환경 변수|설명|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|실행 시간 OpenMP 병렬 영역에 있는 스레드의 수를 조정할 수 있는지 여부를 지정 합니다.|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|중첩 된 병렬 처리 하지 않을 지와 사용 하지 않도록 설정 하지 않으면 중첩 된 병렬 처리는 활성화 여부를 지정 `omp_set_nested`합니다.|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|최대 스레드 수 병렬 영역을 설정 하 여 덮어쓰지 않는 한 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 또는 [num_threads](../../../parallel/openmp/reference/num-threads.md)합니다.|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|동작을 수정 하는 [일정](../../../parallel/openmp/reference/schedule.md) 절 때 `schedule(runtime)` 에 지정 된 한 `for` 또는 `parallel for` 지시문입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 참조](../../../parallel/openmp/reference/openmp-library-reference.md)