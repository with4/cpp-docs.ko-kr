---
title: 4.2 OMP_NUM_THREADS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c2b766d0e3be9b4f1d272a6e3fa205cfcb87039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
**OMP_NUM_THREADS** 해당 번호를 호출 하 여 명시적으로 변경 하지 않으면 기본 실행 하는 동안 사용할 스레드 수 설정 하는 환경 변수는 **omp_set_num_threads** 라이브러리 루틴 또는 명시적 **num_threads** 절에는 **병렬** 지시문입니다.  
  
 값은 **OMP_NUM_THREADS** 환경 변수는 양의 정수 여야 합니다. 스레드 수의 동적 조정을 활성화 되어 있는지 여부에 미치는 영향에 따라 다릅니다. 다양 한 간의 상호 작용 하는 방법에 대 한 규칙에 대 한는 **OMP_NUM_THREADS** 환경 변수 및 동적 조정 스레드 8 페이지 섹션 2.3을 참조 하세요.  
  
 경우에 대 한 지정 된 값은 **OMP_NUM_THREADS** 환경 변수를 지정한 값이 양의 정수 또는 시스템 수 값이 최대 스레드 수를 초과 하는 경우 또는 지원를 사용 하는 스레드 수 구현 시 정의 됩니다.  
  
 예제:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **num_threads** 절 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.  
  
-   **omp_set_num_threads** 함수, 참조 [섹션 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지.  
  
-   **omp_set_dynamic** 함수, 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.