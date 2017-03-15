---
title: "심각한 오류 C1020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1020"
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 심각한 오류 C1020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예기치 않은 \#endif입니다.  
  
 `#endif` 지시문에 일치하는 `#if`, `#ifdef` 또는 `#ifndef` 지시문이 없습니다. 각 `#endif`에 일치하는 지시문이 있어야 합니다.  
  
 다음 샘플에서는 C1020을 생성합니다.  
  
```  
// C1020.cpp #endif     // C1020  
```  
  
 해결 방법:  
  
```  
// C1020b.cpp // compile with: /c #if 1 #endif  
```