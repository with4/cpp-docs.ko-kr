---
title: omp_set_dynamic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00ee1ad4c42e0d2f1303854cbd050e5601d0c3cd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
실행된 시간까지 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있다는 것을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `val`  
 런타임에 의해 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 하는 경우를 나타내는 값입니다.  0이 아니면 0 이면 런타임에서 스레드 수를 조정할 수, 런타임에서 스레드 수를 동적으로 조정 되지 않습니다.  
  
## <a name="remarks"></a>설명  
 스레드 수가에 의해 설정 된 값을 넘지 않는 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) 또는 [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)합니다.  
  
 사용 하 여 [omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) 의 현재 설정을 표시 하려면 `omp_set_dynamic`합니다.  
  
 에 대 한 설정을 `omp_set_dynamic` 의 설정을 재정의 합니다는 [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) 환경 변수입니다.  
  
 자세한 내용은 참조 [3.1.7 omp_set_dynamic 함수](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)합니다.  
  
## <a name="example"></a>예  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)