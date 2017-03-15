---
title: "3.1.3 omp_get_max_threads Function | Microsoft Docs"
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
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.3 omp_get_max_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Omp\_get\_max\_threads** 함수 이상이 경우 병렬 영역 없이 팀을 형성 하는 데 사용 하는 스레드 수가 되도록 보장 하는 정수를 반환 합니다는  **num\_threads** 절 한 코드에서 발생 될 시점에.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 다음은 값을 나타내는  **omp\_get\_max\_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 다음 병렬 영역을 사용 하는 경우는  **num\_threads** 특정 수의 스레드를 보장의 결과에서 요청 하는 절  **omp\_get\_max\_threads** 오래 보유 하지 않습니다.  
  
 **Omp\_get\_max\_threads** 함수의 반환 값을 사용 하 여 모든 스레드가 다음 병렬 영역에서 형성 된 팀에 대 한 충분 한 저장소를 동적으로 할당할 수 있습니다.  
  
## 상호 참조:  
  
-   **omp\_get\_num\_threads** 작동, 참조 하십시오  [구역 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지입니다.  
  
-   **omp\_set\_num\_threads** 작동, 참조 하십시오  [3.1.1 구역](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 페이지에 있습니다.  
  
-   **omp\_set\_dynamic** 작동, 참조 하십시오  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.  
  
-   **num\_threads** 절을 참조 하십시오  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.