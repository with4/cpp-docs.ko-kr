---
title: 목록 없이 플러시 지시문을 사용 하 여 A.14 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 9e63141a-d0c6-43a5-ac16-b0bd7c89b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dd4ad0246d097b252c486abaec7729ed1db4605
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694331"
---
# <a name="a14---using-the-flush-directive-without-a-list"></a>A.14   목록이 없는 flush 지시문 사용
다음 예제에서는 (에 대 한 [섹션 2.6.5](../../parallel/openmp/2-6-5-flush-directive.md) 페이지 20) 영향을 받는 공유 개체를 구별는 `flush` 영향을 받지 않는 공유 개체와에서 목록이 없는 지시문:  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
```  
// omp_flush_without_list.c  
#include <omp.h>  
  
int x, *p = &x;  
  
void f1(int *q)  
{  
    *q = 1;  
    #pragma omp flush  
    // x, p, and *q are flushed  
    //   because they are shared and accessible  
    // q is not flushed because it is not shared.  
}  
  
void f2(int *q)  
{  
    #pragma omp barrier  
    *q = 2;  
  
    #pragma omp barrier  
    // a barrier implies a flush  
    // x, p, and *q are flushed  
    //   because they are shared and accessible  
    // q is not flushed because it is not shared.  
}  
  
int g(int n)  
{  
    int i = 1, j, sum = 0;  
    *p = 1;  
  
    #pragma omp parallel reduction(+: sum) num_threads(10)  
    {  
        f1(&j);  
        // i, n and sum were not flushed  
        //   because they were not accessible in f1  
        // j was flushed because it was accessible  
        sum += j;  
        f2(&j);  
        // i, n, and sum were not flushed  
        //   because they were not accessible in f2  
        // j was flushed because it was accessible  
        sum += i + j + *p + n;  
    }  
    return sum;  
}  
  
int main()  
{  
}  
```