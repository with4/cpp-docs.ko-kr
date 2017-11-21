---
title: "경우 (OpenMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 381347686d8e63681b5d179e191546b8a5bf2f8b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="if-openmp"></a>if (OpenMP)
직렬에서 또는 병렬에서 루프를 실행 해야 하는지를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
if(expression)  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `expression`  
 (0이 아님)을 true로 평가 되 면 동시에 실행 하는 병렬 영역에서 코드를 발생 시키는 정수 식입니다. 식이 false (0) 이면 병렬 영역 (단일 스레드)에서 차례 대로 실행 됩니다.  
  
## <a name="remarks"></a>설명  
 `if`다음과 같은 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [섹션](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 참조 [2.3 parallel 구문](../../../parallel/openmp/2-3-parallel-construct.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
```Output  
val = 0, serialized  
val = 2, parallelized with 2 threads  
```  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)