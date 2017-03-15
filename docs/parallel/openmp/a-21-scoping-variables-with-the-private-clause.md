---
title: "A.21   Scoping Variables with the private Clause | Microsoft Docs"
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
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.21   Scoping Variables with the private Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값은 `i` 및 `j` 다음 예제에서 끝낼 때 병렬 영역에서 정의 되어 있지 않습니다.  
  
```  
int i, j;  
i = 1;  
j = 2;  
#pragma omp parallel private(i) firstprivate(j)  
{  
  i = 3;  
  j = j + 2;  
}  
printf_s("%d %d\n", i, j);  
```  
  
 에 대 한 자세한 내용은 `private` 절을 참조 하십시오  [섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 페이지.