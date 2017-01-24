---
title: "컴파일러 오류 C3021 | Microsoft Docs"
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
  - "C3021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3021"
ms.assetid: 0cef6d97-e267-438a-ac8b-0daf5bbbc2cf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg': OpenMP 'directive' 지시문에서 인수가 비어 있습니다.  
  
 OpenMP 지시문에 인수가 필요합니다.  
  
## 예제  
 다음 샘플에서는 C3021을 생성합니다.  
  
```  
// C3021.cpp // compile with: /openmp #include <stdio.h> #include "omp.h" int g = 0; int main() { int x, y, i; #pragma omp parallel for schedule(static,)   // C3021 for (i = 0; i < 10; ++i) ; #pragma omp parallel for schedule()   // C3021 for (i = 0; i < 10; ++i) printf_s("Hello world, thread %d, iteration %d\n", omp_get_thread_num(), i); #pragma omp parallel reduction()   // C3021 ; #pragma omp parallel reduction(+ :)   // C3021 ; // // The following shows correct syntax examples. // #pragma omp parallel reduction(+ : x, y) ; #pragma omp parallel reduction(* : x, y) ; #pragma omp parallel reduction(- : x, y) ; #pragma omp parallel reduction(& : x, y) ; #pragma omp parallel reduction(^ : x, y) ; #pragma omp parallel reduction(| : x, y) ; #pragma omp parallel reduction(&& : x, y) ; #pragma omp parallel reduction(|| : x, y) ; }  
```