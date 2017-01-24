---
title: "컴파일러 오류 C3033 | Microsoft Docs"
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
  - "C3033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3033"
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 'clause' 절의 변수는 const 한정 형식이 될 수 없습니다.  
  
 특정 절에 전달된 값은 `const` 변수가 될 수 없습니다.  
  
 다음 샘플에서는 C3033을 생성합니다.  
  
```  
// C3033.cpp // compile with: /openmp /link vcomps.lib int main() { const int val = 1; int val2 = 1; #pragma omp parallel reduction(+ : val)   // C3033 ; #pragma omp parallel reduction(+ : val2)   // OK ; }  
```