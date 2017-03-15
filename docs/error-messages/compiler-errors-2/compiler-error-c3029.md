---
title: "컴파일러 오류 C3029 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3029"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3029"
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3029
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': OpenMP 지시문의 데이터 공유 절에 한 번만 나타날 수 있습니다.  
  
 기호가 지시문의 하나 이상 절에서 두 번 이상 사용되었습니다. 기호는 지시문에 한 번만 사용할 수 있습니다.  
  
 다음 샘플에서는 C3029를 생성합니다.  
  
```  
// C3029.cpp // compile with: /openmp /link vcomps.lib #include "omp.h" int g_i; int main() { int i, x; #pragma omp parallel reduction(+ : x, x)   // C3029 ; #pragma omp parallel reduction(+ : x)   // OK ; #pragma omp parallel private(x) reduction(+ : x)   // C3029 ; #pragma omp parallel reduction(+ : x)   // OK ; }  
```