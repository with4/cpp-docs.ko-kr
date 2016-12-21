---
title: "컴파일러 오류 C3045 | Microsoft Docs"
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
  - "C3045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3045"
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP 'sections' 지시문 다음에는 복합 문이 와야 합니다. '{'가 없습니다.  
  
 괄호로 구분된 코드 블록이 [sections](../../parallel/openmp/reference/sections-openmp.md) 지시문 뒤에 나와야 합니다.  
  
 다음 샘플에서는 C3045를 생성합니다.  
  
```  
// C3045.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections ++n2;   // C3045 #pragma omp sections   // OK { ++n3; } } }  
```