---
title: "컴파일러 오류 C3032 | Microsoft Docs"
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
  - "C3032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3032"
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 'clause' 절의 변수는 불완전한 형식 'type'이 될 수 없습니다.  
  
 특정 절에 전달되는 형식은 컴파일러에 완벽하게 표시되어야 합니다.  
  
 다음 샘플에서는 C3032를 생성합니다.  
  
```  
// C3032.cpp // compile with: /openmp /link vcomps.lib #include "omp.h" struct Incomplete; extern struct Incomplete inc; int main() { int i = 9; #pragma omp parallel private(inc)   // C3032 ; #pragma omp parallel private(i)     // OK ; }  
```