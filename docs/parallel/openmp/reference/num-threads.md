---
title: num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b9d12b8216033b5ffe6499290f1c2b5742152b2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="numthreads"></a>num_threads
스레드 팀의 스레드 수를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `num`  
 스레드 수  
  
## <a name="remarks"></a>설명  
 `num_threads` 절과 같은 기능에는 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 함수입니다.  
  
 `num_threads` 다음과 같은 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 참조 [2.3 parallel 구문](../../../parallel/openmp/2-3-parallel-construct.md)합니다.  
  
## <a name="example"></a>예  
 참조 [병렬](../../../parallel/openmp/reference/parallel.md) 사용 하는 예제에 대 한 `num_threads` 절.  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)