---
title: "컴파일러 오류 C3008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3008"
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg': OpenMP 'directive' 지시문의 인수에 닫는 '\)'가 없습니다.  
  
 인수를 사용하는 OpenMP 지시문에 닫는 괄호가 없습니다.  
  
 다음 샘플에서는 C3008을 생성합니다.  
  
```  
// C3008.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x   // C3008 // Try the following line instead: #pragma omp parallel shared(x) { } }  
```