---
title: omp_set_nest_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e49a63fc4bc8d31583478ee6f61fe7b374bb9f0b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691016"
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock
블록은 잠금의 있을 때까지 실행을 스레드입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void omp_set_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `lock`  
 형식의 변수 [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) 를 사용 하 여 초기화 된 [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)합니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [3.2.3 omp_set_lock and omp_set_nest_lock 함수](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)합니다.  
  
## <a name="examples"></a>예제  
 참조 [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) 사용 하는 예제에 대 한 `omp_set_nest_lock`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)