---
title: "A.27   Use of C99 Variable Length Arrays | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.27   Use of C99 Variable Length Arrays
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C99 가변 길이 배열 \(VLAs\)를 사용 하는 방법에는 다음 예제를 보여 줍니다. 한 `firstprivate` 지시문 \([2.7.2.2 섹션](../../parallel/openmp/2-7-2-2-firstprivate.md) 26 페이지\).  
  
> [!NOTE]
>  가변 길이 배열 Visual C\+\+의 현재 지원 되지 않습니다.  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```