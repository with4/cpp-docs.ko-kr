---
title: "Threadprivate 지시문을 사용 하 여 a. 26과 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6eda76c2-c4f1-4208-a900-e0ea98a53eca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1337405fc433ccfc609756cd83ff9e38eb55a79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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