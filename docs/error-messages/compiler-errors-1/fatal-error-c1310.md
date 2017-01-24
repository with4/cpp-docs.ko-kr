---
title: "심각한 오류 C1310 | Microsoft Docs"
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
  - "C1310"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1310"
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1310
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP에서는 프로필 기반 최적화를 사용할 수 없습니다.  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md)로 컴파일된 모든 모듈을 [\/LTCG:PGI](../../build/reference/ltcg-link-time-code-generation.md)와 연결할 수 없습니다.  
  
 다음 샘플에서는 C1310을 생성합니다.  
  
```  
// C1310.cpp // compile with: /openmp /GL /link /LTCG:PGI // C1310 expected int main() { int i = 0, j = 10; #pragma omp parallel { #pragma omp for for (i = 0; i < 0; i++) --j; } }  
```