---
title: "심각한 오류 C1070 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1070"
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 심각한 오류 C1070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 파일에서 \#if\/\#endif 쌍이 짝이 맞지 않습니다.  
  
 `#if`, `#ifdef` 또는 `#ifndef` 지시문에 해당하는 `#endif`가 없습니다.  
  
 다음 샘플에서는 C1070을 생성합니다.  
  
```  
// C1070.cpp #define TEST #ifdef TEST #ifdef TEST #endif // C1070  
```  
  
 해결 방법:  
  
```  
// C1070b.cpp // compile with: /c #define TEST #ifdef TEST #endif #ifdef TEST #endif  
```