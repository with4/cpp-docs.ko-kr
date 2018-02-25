---
title: omp_set_num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce4768c60480e20a48dd3b41d608216259c81530
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
스레드 수, 후속 병렬 영역에 설정 하 여 덮어쓰지 않는 한는 [num_threads](../../../parallel/openmp/reference/num-threads.md) 절.  
  
## <a name="syntax"></a>구문  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `num_threads`  
 병렬 영역에 있는 스레드의 수입니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [3.1.1 omp_set_num_threads 함수](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)합니다.  
  
## <a name="example"></a>예  
 참조 [omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) 사용 하는 예제에 대 한 `omp_set_num_threads`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)