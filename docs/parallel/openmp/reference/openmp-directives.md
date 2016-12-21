---
title: "OpenMP Directives | Microsoft Docs"
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
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Directives
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API에 사용 되는 지시문에 대 한 링크를 제공 합니다.  
  
 Visual C\+\+ 다음 OpenMP 지시문을 지원합니다.  
  
|지시문|설명|  
|---------|--------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|지정 하는 자동으로 업데이트 되는 메모리 위치입니다.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|팀에서 모든 스레드를 동기화 합니다. 장애물 모든 스레드가 실행 될 때까지 모든 스레드는 장애물에 일시 중지 합니다.|  
|[critical](../../../parallel/openmp/reference/critical.md)|코드는 한 번에 하나의 스레드에서 실행 됩니다 지정 합니다.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|모든 스레드가 같은 보기 모든 공유 객체에 대 한 메모리를 지정 합니다.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|작업에서 발생 한 스레드 간에 나눌 수 있는 병렬 영역 내부 루프에 대 한.|  
|[master](../../../parallel/openmp/reference/master.md)|마스터 threadshould만의 프로그램을 실행을 지정 합니다.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)|아래는 병렬화 된 코드를 지정 합니다 순차 루프 다음과 같이 루프를 실행 해야 합니다.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|여러 스레드에서 동시에 실행 되는 코드는 병렬 영역을 정의 합니다.|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|모든 스레드 간에 나눌 수 있는 코드 섹션을 식별 합니다.|  
|[single](../../../parallel/openmp/reference/single.md)|코드 섹션을 마스터 스레드가 아닌 단일 스레드에서 실행 되도록 지정할 수 있습니다.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|변수를 스레드를 전용으로 지정 합니다.|  
  
## 참고 항목  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)