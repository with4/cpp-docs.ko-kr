---
title: "3.1.2 omp_get_num_threads 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d595fd47b87bbc3fd7701fc847821c73169a23e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads 함수
**omp_get_num_threads** 함수 반환 스레드 수가 현재 호출 될 병렬 영역을 실행 하는 팀에 있습니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **num_threads** 절에서 **omp_set_num_threads** 함수 및 **OMP_NUM_THREADS** 팀의 스레드 수를 제어 하는 환경 변수입니다.  
  
 스레드 수는 사용자가 명시적으로 설정 되지 않았습니다, 하는 경우 구현에서 정의 된 기본값은입니다. 이 함수는 가장 가까운 바깥쪽 바인딩할 **병렬** 지시문입니다. Serialize 된 중첩 된 병렬 영역 또는 프로그램의 직렬 부분에서 호출 하는 경우이 함수는 1을 반환 합니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **OMP_NUM_THREADS** 환경 변수 참조 [섹션 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 코어 48 개 페이지에 있습니다.  
  
-   **num_threads** 절 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.  
  
-   **병렬** 생성, 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.