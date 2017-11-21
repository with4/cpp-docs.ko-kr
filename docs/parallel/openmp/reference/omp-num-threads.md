---
title: OMP_NUM_THREADS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_NUM_THREADS
dev_langs: C++
helpviewer_keywords: OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2139ecfc719bd6e5836a67d9387b3ff2f4289bc6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
최대 스레드 수 병렬 영역을 설정 하 여 덮어쓰지 않는 한 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 또는 [num_threads](../../../parallel/openmp/reference/num-threads.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `num`  
 Visual c + + 구현에서 64 최대 병렬 영역에서 원하는 스레드의 최대 수입니다.  
  
## <a name="remarks"></a>설명  
 **OMP_NUM_THREADS** 환경 변수 재정의 될 수 있습니다는 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 함수 또는 [num_threads](../../../parallel/openmp/reference/num-threads.md)합니다.  
  
 기본값 `num` Visual c + + OpenMP 표준의 구현을 하이퍼 스레딩을 Cpu를 포함 하는 가상 프로세서의 수입니다.  
  
 자세한 내용은 참조 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)합니다.  
  
## <a name="example"></a>예제  
 다음 명령 집합의 **OMP_NUM_THREADS** 를 16으로 환경 변수:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 다음 명령은의 현재 설정을 표시는 **OMP_NUM_THREADS** 환경 변수:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>참고 항목  
 [환경 변수](../../../parallel/openmp/reference/openmp-environment-variables.md)