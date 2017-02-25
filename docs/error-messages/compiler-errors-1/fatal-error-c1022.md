---
title: "심각한 오류 C1022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1022"
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 심각한 오류 C1022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#endif가 필요합니다.  
  
 `#if`, `#ifdef` 또는 `#ifndef` 지시문에 일치하는 `#endif` 지시문이 없습니다. 각 `#if`, `#ifdef` 또는 `#ifndef`에 일치하는 `#endif`가 있어야 합니다.  
  
 다음 샘플에서는 C1022를 생성합니다.  
  
```  
// C1022.cpp #define true 1 #if (true) #else #else    // C1022  
```  
  
 해결 방법:  
  
```  
// C1022b.cpp // compile with: /c #define true 1 #if (true) #else #endif  
```