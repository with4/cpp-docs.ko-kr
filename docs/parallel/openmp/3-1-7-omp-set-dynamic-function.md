---
title: "3.1.7 omp_set_dynamic 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87cdd627dd01697fa3d3718a2dc769f4017630a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic 함수
**omp_set_dynamic** 함수 하거나 병렬 영역의 실행에 사용할 수 있는 스레드 수의 동적 조정을 해제 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 경우 *dynamic_threads* 평가 0이 아닌 값으로 후속 병렬 영역을 실행 하는 데 사용 되는 스레드 수가 조정 될 수 있습니다 자동으로 시스템 리소스를 최대한 활용 하려면 런타임 환경으로 합니다. 따라서 사용자가 지정 된 스레드 수는 최대 스레드 수입니다. 병렬 영역을 실행 하는 팀의 스레드 수가 병렬 영역 해당 기간에 대 한 고정 된 상태로 및 로부터 보고 되는 **omp_get_num_threads** 함수입니다.  
  
 경우 *dynamic_threads* 평가를 0으로 이상을 사용할 수 없습니다.  
  
 이 함수는 프로그램의 부분에서 호출 될 때 위에서 설명한 효과가 여기서는 **omp_in_parallel** 함수는 0을 반환 합니다. 프로그램의 일부에서 호출 되는 경우 여기서는 **omp_in_parallel** 0이 아닌 값을 반환 하는 함수,이 함수의 동작이 정의 되지 않습니다.  
  
 에 대 한 호출 **omp_set_dynamic** 보다 우선는 **OMP_DYNAMIC** 환경 변수입니다.  
  
 스레드 동적 조정에 대 한 기본값은 구현 시 정의 합니다. 결과적으로, 특정 개수의 제대로 실행 하기 위해 스레드에 의존 하는 사용자 코드는 동적 스레드 명시적으로 해제 해야 합니다. 구현은 스레드 수를 동적으로 조정 하는 기능은 제공 필요 하지 않지만 모든 플랫폼 간의 이식성을 지원 하려면 인터페이스를 제공 하는 데 필요 합니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **omp_get_num_threads** 함수, 참조 [단원 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지.  
  
-   **OMP_DYNAMIC** 환경 변수를 참조 [섹션 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 페이지 49에 있습니다.  
  
-   **omp_in_parallel** 함수, 참조 [섹션 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 페이지입니다.