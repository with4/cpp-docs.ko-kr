---
title: "컴파일러 오류 C3046 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3046"
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP '\#pragma omp sections' 영역에 구조화된 블록이 없습니다.  
  
 [섹션](../../parallel/openmp/reference/sections-openmp.md) 지시문에 빈 코드 블록이 있습니다.  
  
 다음 샘플에서는 C3046을 생성합니다.  
  
```  
// C3046.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { /* ++n2; #pragma omp section { ++n3; } */ }   // C3046 uncomment code to resolve this C3046 } }  
```