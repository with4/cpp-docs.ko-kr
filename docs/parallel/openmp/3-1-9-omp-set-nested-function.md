---
title: "3.1.9 omp_set_nested Function | Microsoft Docs"
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
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.9 omp_set_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Omp\_set\_nested** 함수를 사용 하거나 중첩 된 병렬 처리를 사용 하지 않습니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 경우  *중첩 된* 중첩 0으로 평가 병렬 처리 해제 되 고은 기본값인 및 중첩 된 병렬 영역은 serialize 되 고 현재 스레드에 의해 실행 됩니다.  경우  *중첩 된* 평가 중첩 된 병렬화를 0이 아닌 값으로 사용 하며 중첩 된 병렬 영역 중첩 된 팀을 구성 하는 데 추가 스레드를 배포할 수 있습니다.  
  
 이 함수 호출에서 일부 프로그램의 경우 위에서 설명한 효과가 어디에  **omp\_in\_parallel** 함수는 0을 반환 합니다.  프로그램의 일부에서 호출 되는 경우 위치는  **omp\_in\_parallel** 0이 아닌 값을 반환 하는 함수,이 함수의 동작은 정의 되지 않습니다.  
  
 이 호출에 대해 우선 순위를 갖는  **OMP\_NESTED** 환경 변수가 있습니다.  
  
 중첩 된 병렬 처리를 사용 하면 중첩 된 병렬 영역을 실행 하는 데 스레드 구현 시 정의 됩니다.  따라서 호환 OpenMP 병렬 영역은 중첩 된 경우에 중첩 된 병렬 처리를 사용 하면 serialize 될 수 있습니다.  
  
## 상호 참조:  
  
-   **OMP\_NESTED** 환경 변수를 참조 하십시오  [섹션 4.4](../../parallel/openmp/4-4-omp-nested.md) 49 페이지입니다.  
  
-   **omp\_in\_parallel** 작동, 참조 하십시오  [섹션 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 페이지에 있습니다.