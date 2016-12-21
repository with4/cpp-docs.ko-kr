---
title: "컴파일러 오류 C3003 | Microsoft Docs"
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
  - "C3003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3003"
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'directive': 지시문 절 다음에는 OpenMP 지시문 이름이 올 수 없습니다.  
  
 OpenMP 지시문 이름이 OpenMP 지시문 절 다음에 올 수 없습니다.  
  
 다음 샘플에서는 C3003을 생성합니다.  
  
```  
// C3003.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x, y, z) for   // C3003 }  
```