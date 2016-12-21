---
title: "컴파일러 오류 C2258 | Microsoft Docs"
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
  - "C2258"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2258"
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2258
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

순수 구문이 잘못되었습니다. '\= 0'이어야 합니다.  
  
 순수 가상 함수를 잘못된 구문으로 선언했습니다.  
  
 다음 샘플에서는 C2258을 생성합니다.  
  
```  
// C2258.cpp // compile with: /c class A { public: void virtual func1() = 1; // C2258 void virtual func2() = 0;   // OK };  
```