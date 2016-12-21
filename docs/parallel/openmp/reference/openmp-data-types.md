---
title: "OpenMP Data Types | Microsoft Docs"
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
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Data Types
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API에 사용 되는 데이터 형식에 대 한 링크를 제공 합니다.  
  
 Visual C\+\+ 구현 표준 openmp는 다음과 같은 데이터가 포함 됩니다.  
  
|데이터 형식|설명|  
|------------|--------|  
|[omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md)|잠금, 잠금을 사용할 수 있는지 여부 또는 잠금을 소유 하는 스레드가 상태를 저장 하는 형식입니다.|  
|[omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)|하나는 잠금에 대 한 정보는 다음으로 저장 하는 형식: 잠금을 사용할 수 있는 한 스레드의 id를 소유한 잠금 및 중첩 수 있는지 여부입니다.|  
  
## 참고 항목  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)