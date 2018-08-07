---
title: 고정된 개수의 스레드를 지정 하는 A.11 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71d09c470b76b61c6737566f7833334aeec6c63a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686541"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   고정된 수의 스레드 지정
일부 응용 프로그램 스레드를 제대로 실행할 고정, 미리 지정한 숫자에 의존 합니다.  구현에서 정의 된 스레드 수를 동적으로 조정에 대 한 기본 설정 이기 때문에 이러한 프로그램 동적 스레드 기능을 해제 하 고 명시적으로 이동성을 보장 하는 스레드 수를 설정 하도록 선택할 수 있습니다. 사용 하는 방법을 보여 주는 다음 예제 `omp_set_dynamic` ([섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 페이지 39), 및 `omp_set_num_threads` ([섹션 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 페이지 36):  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 이 예제에서는 프로그램 16 스레드에 의해 실행 된 경우에 올바르게를 실행 합니다. 구현은 16 스레드를 지원할 수 없는 경우이 예제에서는 동작은 구현 시 정의 합니다.  
  
 병렬 영역 실행 되는 스레드 수를 설정 하는 동적 스레드에 관계 없이 병렬 영역 중 일관적으로 유지 되는 참고 합니다. 동적 스레드 메커니즘 병렬 영역의 시작 부분에 사용할 스레드 수를 결정 영역의 기간에 대 한 상수 유지 합니다.