---
title: "심각한 오류 C1016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1016"
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 심각한 오류 C1016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#ifdef에 식별자가 필요합니다.\#ifndef에 식별자가 필요합니다.  
  
 조건부 컴파일 지시문\([\#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) 또는 `#ifndef`\)에 평가할 식별자가 없습니다. 오류를 해결하려면 식별자를 지정합니다.  
  
 다음 샘플에서는 C1016을 생성합니다.  
  
```  
// C1016.cpp #ifdef   // C1016 #define FC1016 #endif int main() {}  
```  
  
 해결 방법:  
  
```  
// C1016b.cpp #ifdef X #define FC1016 #endif int main() {}  
```