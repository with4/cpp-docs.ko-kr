---
title: omp_unset_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 243ff6d2336d3e293d009f82ba4a39243e076f94
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690691"
---
# <a name="ompunsetlock"></a>omp_unset_lock
잠금을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void omp_unset_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `lock`  
 형식의 변수 [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) 를 사용 하 여 초기화 된 [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)스레드에서 소유 하 고 실행 중인 함수에, 합니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [3.2.4 omp_unset_lock and omp_unset_nest_lock 함수](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)합니다.  
  
## <a name="example"></a>예제  
 참조 [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) 사용 하는 예제에 대 한 `omp_unset_lock`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)