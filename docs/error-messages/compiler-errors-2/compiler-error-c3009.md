---
title: "컴파일러 오류 C3009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3009"
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'label': OpenMP 구조화된 블록 외부에서 내부로 점프할 수 없습니다.  
  
 코드가 OpenMP 블록 안이나 밖으로 점프할 수 없습니다.  
  
 다음 샘플에서는 C3009를 생성합니다.  
  
```  
// C3009.c // compile with: /openmp int main() { #pragma omp parallel { lbl2:; } goto lbl2;   // C3009 }  
```