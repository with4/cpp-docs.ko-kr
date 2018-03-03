---
title: "3.1.3 omp_get_max_threads 함수 | Microsoft Docs"
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
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13aee27dc04afb8414a89bb8f30a98c8e73fb694
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads 함수
**omp_get_max_threads** 함수 반환 하는 경우 병렬 영역 없이 팀을 구성 하는 데 사용할 스레드의 수 이상이 되도록 보장 하는 정수는 **num_threads** 절 코드에서 해당 지점에서 경험할 수 있었습니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 다음의 값에 하 한을 표현 **omp_get_max_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 경우에 후속 병렬 영역에서 사용 하는 **num_threads** 절 특정 개수의 스레드가 보증은 결과의 하한값에 요청을 **omp_get_max_threads** 긴 보류 없습니다.  
  
 **omp_get_max_threads** 후속 병렬 영역에서 형성 된 팀의 모든 스레드에 대 한 충분 한 저장소를 동적으로 할당할 함수의 반환 값을 사용할 수 있습니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **omp_get_num_threads** 함수, 참조 [단원 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지.  
  
-   **omp_set_num_threads** 함수, 참조 [섹션 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지.  
  
-   **omp_set_dynamic** 함수, 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.  
  
-   **num_threads** 절 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.