---
title: 스레드로부터 안전한 잠금 함수 A.31 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efac1091b2245b9368451e8b5148bbfe478410f4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690444"
---
# <a name="a31---thread-safe-lock-functions"></a>A.31   스레드로부터 안전한 Lock 함수
다음 c + + 예제를 사용 하 여 병렬 영역에서 잠금 배열을 초기화 하는 방법을 보여 줍니다 `omp_init_lock` ([섹션 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) 42 페이지에).  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
```  
// A_13_omp_init_lock.cpp  
// compile with: /openmp  
#include <omp.h>  
  
omp_lock_t *new_locks() {  
   int i;  
   omp_lock_t *lock = new omp_lock_t[1000];  
   #pragma omp parallel for private(i)  
   for (i = 0 ; i < 1000 ; i++)  
      omp_init_lock(&lock[i]);  
  
   return lock;  
}  
  
int main () {}  
```