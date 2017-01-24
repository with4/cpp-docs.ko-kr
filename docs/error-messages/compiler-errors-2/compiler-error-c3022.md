---
title: "컴파일러 오류 C3022 | Microsoft Docs"
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
  - "C3022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3022"
ms.assetid: 9f1d444c-6c6e-48d9-9346-69128390aa33
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'clause': OpenMP 'directive' 지시문에서 'value'의 예약 종류가 잘못되었습니다.  
  
 지원되지 않는 값이 절에 전달되었습니다.  
  
 다음 샘플에서는 C3022를 생성합니다.  
  
```  
// C3022.cpp // compile with: /openmp /link vcomps.lib #include <stdio.h> #include "omp.h" int main() { int i; #pragma omp parallel for schedule(10)   // C3022 for (i = 0; i < 10; ++i) ; #pragma omp parallel for schedule(x)   // C3022 for (i = 0; i < 10; ++i) ; // OK #pragma omp parallel for schedule(runtime) for (i = 0; i < 10; ++i) ; }  
```