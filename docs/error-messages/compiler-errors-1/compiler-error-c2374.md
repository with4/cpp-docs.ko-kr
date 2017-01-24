---
title: "컴파일러 오류 C2374 | Microsoft Docs"
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
  - "C2374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2374"
ms.assetid: 73b51965-e91c-4e21-9732-f71c1449d22e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 재정의. 여러 번 초기화했습니다.  
  
 식별자를 두 번 이상 초기화했습니다.  
  
 다음 샘플에서는 C2374를 생성합니다.  
  
```  
// C2374.cpp // compile with: /c int i = 0; int i = 1;   // C2374 int j = 1;   // OK  
```