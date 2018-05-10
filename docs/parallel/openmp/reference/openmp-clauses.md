---
title: OpenMP 절 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7abe5a637a2a32c696f19f5ab9988f1be361f647
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-clauses"></a>OpenMP 절
OpenMP API에서 사용 되는 절에 대 한 링크를 제공 합니다.  
  
 Visual c + +에서는 다음 OpenMP 절을 지원합니다.  
  
|절|설명|  
|------------|-----------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|스레드가 마스터 스레드에 값에 대 한 액세스를 허용 된 [threadprivate](../../../parallel/openmp/reference/threadprivate.md) 변수입니다.|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|하나 이상의 변수 모든 스레드 간에 공유 되지 않아야 지정 합니다.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|병렬 영역에서 범위가 지정 되지 않은 변수 동작을 지정합니다.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|병렬 구문 하기 전에 존재 하기 때문에 각 스레드에 변수의 자체 인스턴스에 있어야 하 고 변수 값으로 변수를 초기화 해야 한다는 지정 합니다.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|직렬에서 또는 병렬에서 루프를 실행 해야 하는지를 지정 합니다.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|변수는 바깥쪽 컨텍스트에서 버전 개인 버전 최종 반복 (루프에 대 한 구문) 또는 마지막 섹션 (#pragma 섹션) 스레드가 실행의 같음 설정 되도록 지정 합니다.|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|지시문에서 암시적 장벽을 재정의합니다.|  
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|스레드 팀의 스레드 수를 설정합니다.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|병렬 처리에 필요한 [에 대 한](../../../parallel/openmp/reference/for-openmp.md) 문을 경우는 [정렬](../../../parallel/openmp/reference/ordered-openmp-directives.md) 지시문은 루프에서 사용 됩니다.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|각 스레드에 변수의 자체 인스턴스가 있어야 한다는 것을 지정 합니다.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|각 스레드에 private 되는 하나 이상의 변수에 병렬 영역 끝날 때 감소 작업의 제목을 지정 합니다.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|에 적용 된 [에 대 한](../../../parallel/openmp/reference/for-openmp.md) 지시문입니다.|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|하나 이상의 변수 모든 스레드 간에 공유 되지 않아야 지정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)