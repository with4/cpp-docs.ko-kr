---
title: Threadprivate 지시문을 사용 하 여 a. 26과 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6eda76c2-c4f1-4208-a900-e0ea98a53eca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b74325ec96702838aaaf9be62d398178c8c2902
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="a26---using-the-threadprivate-directive"></a>A.26   threadprivate 지시문 사용
다음 예에서는 사용 하는 방법을 보여 줍니다는 `threadprivate` 지시문 ([2.7.1 섹션](../../parallel/openmp/2-7-1-threadprivate-directive.md) 23 페이지) 각 스레드는 별도 카운터를 제공 합니다.  
  
 **예제 1:**  
  
```  
int counter = 0;  
#pragma omp threadprivate(counter)  
  
int sub()  
{  
    counter++;  
    return(counter);  
}  
```  
  
 **예제 2:**  
  
```  
int sub()  
{  
    static int counter = 0;  
    #pragma omp threadprivate(counter)  
    counter++;  
    return(counter);  
}  
```