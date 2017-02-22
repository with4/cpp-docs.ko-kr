---
title: "컴파일러 오류 C3034 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3034"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3034"
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3034
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP 'directive1' 지시문은 'directive2' 지시문 내부에 직접 중첩될 수 없습니다.  
  
 일부 지시문은 중첩될 수 없습니다. 이 오류를 해결하려면 두 지시문의 문을 하나의 지시문 블록으로 병합하거나 연속 지시문을 생성할 수 있습니다.  
  
 다음 샘플에서는 C3034를 생성합니다.  
  
```  
// C3034.cpp // compile with: /openmp /link vcomps.lib int main() { #pragma omp single { #pragma omp single   // C3034 { ; } } // Two consecutive single clauses are OK. #pragma omp single { } #pragma omp single { } }  
```