---
title: "컴파일러 오류 C3007 | Microsoft Docs"
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
  - "C3007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3007"
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg': OpenMP 'directive' 지시문의 절이 인수를 사용하지 않습니다.  
  
 OpenMP 지시문에 인수가 있지만 지시문에서 인수를 사용하지 않습니다.  
  
 다음 샘플에서는 C3007을 생성합니다.  
  
```  
// C3007.c // compile with: /openmp int main() { #pragma omp parallel for ordered(2)   // C3007 }  
```