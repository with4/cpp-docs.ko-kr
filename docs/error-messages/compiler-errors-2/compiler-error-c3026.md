---
title: "컴파일러 오류 C3026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3026"
ms.assetid: 3297060e-cc5b-4600-a2db-09bfc4ffa21f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'clause': 상수 식이 양수여야 합니다.  
  
 절에 정수 값을 전달했지만 값이 양수가 아닙니다. 숫자가 양수여야 합니다.  
  
## 예제  
 다음 샘플에서는 C3026을 생성합니다.  
  
```  
// C3026.cpp // compile with: /openmp /link vcomps.lib #include <stdio.h> #include "omp.h" int main() { int i; const int i1 = 0; #pragma omp parallel for num_threads(i1)   // C3026 for (i = 1; i <= 2; ++i) printf_s("Hello World - thread %d - iteration %d\n", omp_get_thread_num(), i); #pragma omp parallel for num_threads(i1 + 1)   // OK for (i = 1; i <= 2; ++i) printf_s("Hello World - thread %d - iteration %d\n", omp_get_thread_num(), i); }  
```