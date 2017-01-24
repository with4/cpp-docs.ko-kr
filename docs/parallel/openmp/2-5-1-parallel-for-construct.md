---
title: "2.5.1 parallel for Construct | Microsoft Docs"
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
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.5.1 parallel for Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**에 대 한 병렬** 지시문이에 대 한 바로  **병렬** 하나만 포함 하는 영역  **에 대 한** 지시문입니다.  구문에는  **에 대 한 병렬** 지시문은 다음과 같습니다:  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-line  
   for-loop  
```  
  
 모든 절이이 포함할 수 있습니다는  **병렬** 지시문 및  **에 대 한** 지시문을 제외 하 고는 `nowait` 와 동일한 의미 및 제한 사항 절.  의미는 명시적으로 지정 하는 동일을  **병렬** 지시문 바로 다음에  **에 대 한** 지시문입니다.  
  
## 상호 참조:  
  
-   **병렬** 지시문 참조  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.  
  
-   **에 대 한** 지시문 참조  [섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지입니다.  
  
-   데이터 특성 절을 참조 하십시오. [2.7.2 Data\-Sharing Attribute Clauses](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지입니다.