---
title: "컴파일러 오류 C3048 | Microsoft Docs"
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
  - "C3048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3048"
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\#pragma omp atomic' 다음에 나오는 식의 형식이 잘못되었습니다.  
  
 원자성 지시문이 잘못 지정되었습니다.  
  
 다음 샘플에서는 C3048을 생성합니다.  
  
```  
// C3048.cpp // compile with: /openmp vcomps.lib #include "omp.h" #include <stdio.h> int main() { int a[10]; omp_set_num_threads(4); #pragma omp parallel { #pragma omp atomic a[0] = 1;   // C3048 // try the following line instead // a[0] += 1; } }  
```