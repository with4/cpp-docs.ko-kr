---
title: "OpenMP Clauses | Microsoft Docs"
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
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Clauses
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API에 사용 되는 절에 대 한 링크를 제공 합니다.  
  
 Visual C\+\+ 다음 OpenMP 절을 지원합니다.  
  
|절|설명|  
|-------|--------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|마스터 스레드 값에 액세스 하는 스레드 수는 [threadprivate](../../../parallel/openmp/reference/threadprivate.md) 변수입니다.|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|하나 이상의 변수 모든 스레드 간에 공유 하도록 지정 합니다.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|병렬 영역에 unscoped 변수 동작을 지정합니다.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|병렬 구문을 전에 있기 때문에 각 스레드가 자체 인스턴스 변수를 했는지와 변수의 값으로 변수를 초기화 해야 함을 지정 합니다.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|직렬 또는 병렬 루프 실행 여부를 지정 합니다.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|변수는 바깥쪽 컨텍스트에서 버전의 최종 반복 \(for 루프 구문\) 이나 마지막 구역 \(\# pragma 섹션\) 어떤 스레드가 실행 전용 버전을 같게 설정 되도록 지정 합니다.|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|지시문에서 암시적 장애물을 무시합니다.|  
|[num\_threads](../../../parallel/openmp/reference/num-threads.md)|스레드는 스레드 팀에 설정합니다.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|병렬에 필요한 [for](../../../parallel/openmp/reference/for-openmp.md) 문 경우는 [ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md) 지시문이 루프에서 사용 될 수 있습니다.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|각 스레드가 자체 인스턴스 변수를 가지도록 지정 합니다.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|각 스레드에 한정 되는 하나 이상의 변수 끝의 병렬 영역 축소 작업의 제목을 지정 합니다.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|적용 되는 [for](../../../parallel/openmp/reference/for-openmp.md) 지시문입니다.|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|하나 이상의 변수 모든 스레드 간에 공유 하도록 지정 합니다.|  
  
## 참고 항목  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)