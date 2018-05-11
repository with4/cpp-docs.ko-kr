---
title: 3.3.1 omp_get_wtime 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71296d23df72464ed730713566c95e2403760a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime 함수
`omp_get_wtime` 함수 반환 배정밀도 부동 소수점 값 경과 된 벽 시계 시간을 몇 가지 "과거의 지정 시간" 이후의 초 단위입니다.  실제 "과거의 지정 시간"은 선택적 요소 이지만를 응용 프로그램의 실행 하는 동안 변경 하지 않도록 보장 됩니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 다음 예제와 같이 전 까지의 경과 시간을 측정 하는 함수를 사용할 수는 것으로 예상 됩니다.  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 반환 되는 시간 된 상태인 "스레드 단위 시간" 응용 프로그램에 참여 하는 모든 스레드에서 전체적으로 일치 하도록 않아도 되는 것입니다.