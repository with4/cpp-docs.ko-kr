---
title: "컴파일러 경고(수준 4) C4343 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4343"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4343"
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고(수준 4) C4343
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma optimize\("g",off\)는 \/Og 옵션을 재정의합니다.  
  
 이 경고는 IPF\(Itanium Processor Family\) 컴파일러에서만 사용되며 pragma [optimize](../../preprocessor/optimize.md)가 [\/Og](../../build/reference/og-global-optimizations.md) 컴파일러 옵션을 재정의했음을 보고합니다.  
  
 다음 샘플에서는 C4343을 생성합니다.  
  
```  
// C4343.cpp // compile with: /Og /W4 /LD // processor: IPF #pragma optimize ("g", off)   // C4343  
```