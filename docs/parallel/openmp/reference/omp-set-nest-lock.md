---
title: omp_set_nest_lock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2ae23cfd58b55881ebaa25f55d121d7ab45f3b3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
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