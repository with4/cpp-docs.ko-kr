---
title: "컴파일러 오류 C3011 | Microsoft Docs"
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
  - "C3011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3011"
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

병렬 영역 내부에서는 직접 인라인 어셈블리를 사용할 수 없습니다.  
  
 `omp` 병렬 영역은 인라인 어셈블리 명령을 포함할 수 없습니다.  
  
 다음 샘플에서는 C3011을 생성합니다.  
  
```  
// C3011.cpp // compile with: /openmp // processor: /x86 int main() { int   n = 0; #pragma omp parallel { _asm mov eax, n   // Delete this line to resolve this error. }   // C3011 }  
```