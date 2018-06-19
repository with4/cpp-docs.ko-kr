---
title: 마스터 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- master
dev_langs:
- C++
helpviewer_keywords:
- master OpenMP directive
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df1cb8daf83f456c551f5b47646dce640e21c804
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686869"
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
  
## <a name="example"></a>예제  
  
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