---
title: "A.8   Specifying Parallel Sections | Microsoft Docs"
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
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.8   Specifying Parallel Sections
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제에서는 \(에 대 한  [2.4.2 절](../../parallel/openmp/2-4-2-sections-construct.md) 페이지 14\) 함수  *xaxis*,  *yaxis*, 및  *zaxis* 동시에 실행할 수 있습니다.  첫 번째 `section` 지시어는 선택 사항입니다.  참고 모든 `section` 지시문의 어휘 범위에서 표시 해야는 `parallel``sections` 를 생성 합니다.  
  
```  
#pragma omp parallel sections  
{  
    #pragma omp section  
        xaxis();  
    #pragma omp section  
        yaxis();  
    #pragma omp section  
        zaxis();  
}  
```