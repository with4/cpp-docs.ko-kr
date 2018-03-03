---
title: "3.1.9 omp_set_nested 함수 | Microsoft Docs"
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
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0910e7df0ebd423b9967fd0eb7931b7434ba94fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested 함수
**omp_set_nested** 함수 사용 하거나 중첩 된 병렬 처리를 사용 하지 않도록 설정 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 경우 *중첩* 중첩 0으로 계산 병렬 처리 해제, 기본값, 그리고 중첩 된 병렬 영역은으로 serialize 되 고 현재 스레드에 의해 실행 됩니다. 경우 *중첩* 평가 0이 아닌 값에 중첩 된 병렬 처리 사용 되 고 중첩 된 병렬 영역 중첩된 팀을 구성 하기 위해 추가 스레드를 배포할 수 있습니다.  
  
 이 함수는 프로그램의 부분에서 호출 될 때 위에서 설명한 효과가 여기서는 **omp_in_parallel** 함수는 0을 반환 합니다. 프로그램의 일부에서 호출 되는 경우 여기서는 **omp_in_parallel** 0이 아닌 값을 반환 하는 함수,이 함수의 동작이 정의 되지 않습니다.  
  
 이 호출 하는 보다 우선은 **OMP_NESTED** 환경 변수입니다.  
  
 중첩 된 병렬 처리를 사용 하는 경우에 중첩 된 병렬 영역은 실행 하는 데 사용 되는 스레드 수는 구현 정의 합니다. 결과적으로, OpenMP 호환 구현 중첩 된 병렬 처리를 사용 하는 경우에 중첩 된 병렬 영역은 serialize 할 수 있습니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **OMP_NESTED** 환경 변수를 참조 [섹션 4.4](../../parallel/openmp/4-4-omp-nested.md) 페이지 49에 있습니다.  
  
-   **omp_in_parallel** 함수, 참조 [섹션 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 페이지입니다.