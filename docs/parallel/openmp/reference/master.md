---
title: "마스터 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- master
dev_langs:
- C++
helpviewer_keywords:
- master OpenMP directive
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 726848412dbfc1fde515af64edf1db9f85b8d988
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="master"></a>master
마스터 threadshould만 실행할 프로그램의 한 섹션을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp master  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>설명  
 **마스터** 지시문 OpenMP 절을 지원 합니다.  
  
 [단일](../../../parallel/openmp/reference/single.md) 지시문을 사용 하면 코드의 섹션을 마스터 스레드에 반드시 단일 스레드에서 실행할지 지정할 수 있습니다.  
  
 자세한 내용은 참조 [2.6.1 master 구문](../../../parallel/openmp/2-6-1-master-construct.md)합니다.  
  
## <a name="example"></a>예  
  
```  
// omp_master.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
  
int main( )   
{  
    int a[5], i;  
  
    #pragma omp parallel  
    {  
        // Perform some computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] = i * i;  
  
        // Print intermediate results.  
        #pragma omp master  
            for (i = 0; i < 5; i++)  
                printf_s("a[%d] = %d\n", i, a[i]);  
  
        // Wait.  
        #pragma omp barrier  
  
        // Continue with the computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] += i;  
    }  
}  
```  
  
```Output  
a[0] = 0  
a[1] = 1  
a[2] = 4  
a[3] = 9  
a[4] = 16  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)