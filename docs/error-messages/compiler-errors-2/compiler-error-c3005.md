---
title: "컴파일러 오류 C3005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3005"
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'error\_text': OpenMP 'directive' 지시문에 예기치 못한 토큰이 있습니다.  
  
 OpenMP 지시문 형식이 잘못되었습니다.  
  
 다음 샘플에서는 C3005를 생성합니다.  
  
```  
// C3005.c // compile with: /openmp int main() { #pragma omp parallel + for   // C3005 }  
```  
  
 C3005는 pragma와 같은 줄에 여는 중괄호를 배치하면 발생할 수 있습니다.  
  
```  
// C3005b.c // compile with: /openmp int main() { #pragma omp parallel {   // C3005 put open brace on next line lbl2:; } goto lbl2; }  
```