---
title: "3.1.4 omp_get_thread_num 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7b968d103631dafcdd2132cb749ae8feed30085
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
  
-   `omp_get_num_threads`함수, 참조 [단원 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 페이지.