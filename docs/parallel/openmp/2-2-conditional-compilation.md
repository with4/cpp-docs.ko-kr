---
title: "2.2 Conditional Compilation | Microsoft Docs"
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
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.2 Conditional Compilation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_**OPENMP** 매크로 이름으로 10 진수 상수 OpenMP 규격 구현에서 정의 됩니다  *yyyymm*, 연도 및 월 승인 된 사양의 될 것입니다.  이 매크로의 제목을 수 없습니다는  **\# define** 또는  **\# undef** 전처리 지시문입니다.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 공급 업체 확장 Openmp를 정의 하는 경우 추가로 미리 정의 된 매크로 지정할 수 있습니다.