---
title: 3.1.4 omp_get_thread_num 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad749b91470f7834169fe8ed734f1d627aa228e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686073"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num 함수
`omp_get_thread_num` 함수는 함수를 실행 하는 스레드의 해당 팀 내에서 스레드 수를 반환 합니다. 스레드 번호 첫 부분이 0 및 **omp_get_num_threads()**-1을 포함 합니다. 팀의 마스터 스레드는 스레드 0입니다.  
  
 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 직렬 지역에서 호출 된 경우 `omp_get_thread_num` 0을 반환 합니다. Serialize 된 중첩 된 병렬 영역 내부에서 호출 하는 경우이 함수는 0을 반환 합니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   `omp_get_num_threads` 함수, 참조 [단원 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지.