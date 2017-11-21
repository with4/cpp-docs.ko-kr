---
title: "C99 가변 길이 배열 A.27 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 673eeb7229524b17c12a9a40c64380e4e5bb5feb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="a27---use-of-c99-variable-length-arrays"></a>A.27   C99 가변 길이 배열 사용
다음 예제에서 C99 가변 길이 배열 (VLAs)를 사용 하는 방법을 보여 줍니다.는 `firstprivate` 지시문 ([섹션 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) 26 페이지).  
  
> [!NOTE]
>  Visual c + +에서 가변 길이 배열은 현재 지원 되지 않습니다.  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```