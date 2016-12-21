---
title: "심각한 오류 C1018 | Microsoft Docs"
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
  - "C1018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1018"
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예기치 않은 \#elif입니다.  
  
 `#elif` 지시문이 `#if`, `#ifdef` 또는 `#ifndef` 구문 외부에 표시됩니다.`#elif`는 이러한 구문 중 하나 내에서만 사용합니다.  
  
 다음 샘플에서는 C1018을 생성합니다.  
  
```  
// C1018.cpp #elif      // C1018 #endif int main() {}  
```  
  
 해결 방법:  
  
```  
// C1018b.cpp #if 1 #elif #endif int main() {}  
```