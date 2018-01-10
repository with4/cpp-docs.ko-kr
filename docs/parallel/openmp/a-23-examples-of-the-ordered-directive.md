---
title: "순서가 지정 된 지시문의 a. 23 예 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83d77bb4f064a7ee69b013b36de919b57486b3e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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