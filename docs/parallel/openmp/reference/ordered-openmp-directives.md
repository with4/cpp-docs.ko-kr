---
title: "정렬 (OpenMP 지시문) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ordered
dev_langs: C++
helpviewer_keywords: ordered OpenMP directive
ms.assetid: e1aa703e-d07d-4f6a-9b2a-f4f25203d850
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6fa5db4e92603519314750886c28db7d097183b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ordered-openmp-directives"></a>ordered (OpenMP 지시문)
순차 루프와 같은 루프를 실행 해야 해당 코드는 병렬화 된에서 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp ordered  
   structured-block  
```  
  
## <a name="remarks"></a>설명  
 **정렬** 지시문의 동적 범위 내에 있어야 합니다.는 [에 대 한](../../../parallel/openmp/reference/for-openmp.md) 또는 **에 대 한 병렬** 를 생성 한 **정렬** 절.  
  
 **정렬** 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 참조 [2.6.6 ordered 구문](../../../parallel/openmp/2-6-6-ordered-construct.md)합니다.  
  
## <a name="example"></a>예  
  
```  
// omp_ordered.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
static float a[1000], b[1000], c[1000];  
  
void test(int first, int last)   
{  
    #pragma omp for schedule(static) ordered  
    for (int i = first; i <= last; ++i) {  
        // Do something here.  
        if (i % 2)   
        {  
            #pragma omp ordered   
            printf_s("test() iteration %d\n", i);  
        }  
    }  
}  
  
void test2(int iter)   
{  
    #pragma omp ordered  
    printf_s("test2() iteration %d\n", iter);  
}  
  
int main( )   
{  
    int i;  
    #pragma omp parallel  
    {  
        test(1, 8);  
        #pragma omp for ordered  
        for (i = 0 ; i < 5 ; i++)  
            test2(i);  
    }  
}  
```  
  
```Output  
test() iteration 1  
test() iteration 3  
test() iteration 5  
test() iteration 7  
test2() iteration 0  
test2() iteration 1  
test2() iteration 2  
test2() iteration 3  
test2() iteration 4  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)