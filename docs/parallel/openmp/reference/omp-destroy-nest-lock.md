---
title: omp_destroy_nest_lock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_destroy_nest_lock
dev_langs: C++
helpviewer_keywords: omp_destroy_nest_lock OpenMP function
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8949f9fe49efab6b9a5fc2dd5a54b53ba58d9e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ompdestroynestlock"></a>omp_destroy_nest_lock
중첩 잠금 초기화를 취소 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `lock`  
 형식의 변수 [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) 를 사용 하 여 초기화 된 [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)합니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)합니다.  
  
## <a name="example"></a>예  
 참조 [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) 사용 하는 예제에 대 한 `omp_destroy_nest_lock`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)