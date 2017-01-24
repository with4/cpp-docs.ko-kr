---
title: "2.5.2 parallel sections Construct | Microsoft Docs"
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
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.2 parallel sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**평행 단면** 은  지시문 제공 가기 양식을 지정 하는 데는  **병렬** 영역이 하나만 포함 된  **섹션** 지시문입니다.  의미는 명시적으로 지정 하는 동일을  **병렬** 지시문 바로 다음에  **섹션** 지시문입니다.  구문에는  **평행 단면** 은 지시문은 다음과 같습니다:  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block  ]  
   ...  
}  
```  
  
 *절* 동의 절 중 하나가 될 수 있습니다 있는  **병렬** 및  **섹션** 지시문을 제외 하 고는  **에 nowait** 절.  
  
## 상호 참조:  
  
-   **병렬** 지시문 참조  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.  
  
-   **구역** 지시문을 참조  [2.4.2 절](../../parallel/openmp/2-4-2-sections-construct.md) 14 페이지입니다.