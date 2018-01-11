---
title: "OpenMP 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51d501139d0610d670f7d646dc985a694a5b741c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="openmp-directives"></a>OpenMP 지시문
OpenMP API에서 사용 되는 지시문에 대 한 링크를 제공 합니다.  
  
 Visual c + +에서는 다음과 같은 OpenMP 지시문을 지원합니다.  
  
|지시문|설명|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|지정 하는 원자적으로 업데이트할 수 있는 메모리 위치 합니다.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|팀;의 모든 스레드를 동기화합니다. 장벽, 모든 스레드는 장벽 실행 될 때까지 모든 스레드가 일시 중지 합니다.|  
|[critical](../../../parallel/openmp/reference/critical.md)|한 번에 코드를 한 스레드에서 실행할지를 지정 합니다.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|모든 스레드가 공유 모든 개체에 대 한 메모리의 동일한 보기를 갖도록 지정 합니다.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|수행 된 작업을 발생 한 스레드 간에 나눠집니다 병렬 영역 내부 루프에 대 한 합니다.|  
|[master](../../../parallel/openmp/reference/master.md)|마스터 threadshould만 실행할 프로그램의 한 섹션을 지정 합니다.|  
|[정렬](../../../parallel/openmp/reference/ordered-openmp-directives.md)|순차 루프와 같은 루프를 실행 해야 해당 코드는 병렬화 된에서 지정 합니다.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|여러 스레드에서 동시에 실행 되는 코드의 병렬 영역을 정의 합니다.|  
|[섹션](../../../parallel/openmp/reference/sections-openmp.md)|모든 스레드가에서 나눌 수 있는 코드 섹션을 식별 합니다.|  
|[single](../../../parallel/openmp/reference/single.md)|코드의 섹션을 마스터 스레드에 반드시 단일 스레드에서 실행할지 지정할 수 있습니다.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|변수는 스레드에 private 임을 지정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [절](../../../parallel/openmp/reference/openmp-clauses.md)