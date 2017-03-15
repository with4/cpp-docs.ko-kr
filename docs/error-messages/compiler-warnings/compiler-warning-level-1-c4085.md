---
title: "컴파일러 경고(수준 1) C4085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4085"
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 경고(수준 1) C4085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pragma 매개 변수는 'on' 또는 'off'이어야 합니다.  
  
 pragma에 **on** 또는 **off** 매개 변수가 필요합니다. pragma가 무시됩니다.  
  
 다음 샘플에서는 C4085를 생성합니다.  
  
```  
// C4085.cpp // compile with: /W1 /LD #pragma optimize( "t", maybe )  // C4085  
```