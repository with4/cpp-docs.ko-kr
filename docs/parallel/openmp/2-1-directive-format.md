---
title: "2.1 Directive Format | Microsoft Docs"
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
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.1 Directive Format
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP 지시문의 구문은 문법에서 공식적으로 지정한  [부록 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md), 한 비공식적 같이:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 각 지시문으로 시작  **\# pragma omp**, 다른 \(비\-OpenMP 또는 공급 업체 확장을 OpenMP\) pragma 지시문 이름이 같은 충돌의 가능성을 줄일 수 있습니다.  지시문의 나머지 부분은 컴파일러 지시문은 C 및 C\+\+ 표준의 규칙을 따릅니다.  특히, 공백을 전과 후 사용할 수 있습니다의  **\#**, 지시문에 단어를 구분 공백을 경우에 따라 사용 해야 합니다.  전처리 토큰 뒤에  **\# pragma omp** 매크로 대체 될 수 있습니다.  
  
 지시문은 대\/소문자 구분 합니다.  절에서 지시문이 나타나는 순서는 중요 하지 않습니다.  지시문의 절 각 절의 설명에 나열 된 제한 사항에 따라 필요에 따라 반복 될 수 있습니다.  경우  *변수 목록* 표시는 절에만 변수를 지정 해야 합니다.  하나의  *지시문 이름* 당 지시문을 지정할 수 있습니다.  예를 들어, 다음 지시문은 사용할 수 없습니다.  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 OpenMP 지시문 구조화 된 블록 이어야 최대 하나 그 문에 적용 됩니다.