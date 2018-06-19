---
title: 순서가 지정 된 지시문의 a. 23 예 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37cc4ea9db8cbd1a7bf095e2bde0ae482053a584
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692758"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   ordered 지시문 예제
와 순서가 지정 된 섹션이 여러 개 있을 수는 `for` 으로 지정 된는 `ordered` 절. 첫 번째 예에서는 비규격 이므로 API 다음을 지정 합니다.  
  
 "포함 하는 루프의 반복은 `for` 구문을 실행 해서는 안 동일한 `ordered` 지시문 보다 하며 한 번 실행 하면 안 둘 이상의 `ordered` 지시문입니다." (참조 [섹션 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 페이지)  
  
 비규격이 예제에서는 모든 반복 순서가 지정 된 섹션 2를 실행합니다.  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 에서는 다음 규격 예제는 `for` 둘 이상의 함께 정렬 섹션:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```