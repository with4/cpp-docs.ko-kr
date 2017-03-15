---
title: "컴파일러 오류 C2232 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2232"
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'–\>': 왼쪽 피연산자에 'class\-key' 형식이 있습니다. '.'를 사용하세요.  
  
 `->` 연산자의 왼쪽에 있는 피연산자가 포인터가 아닙니다. 클래스, 구조체 또는 공용 구조체에 대해 마침표\(.\) 연산자를 사용하세요.  
  
 다음 샘플에서는 C2232를 생성합니다.  
  
```  
// C2232.c struct X { int member; } x, *px; int main() { x->member = 0;   // C2232, x is not a pointer px->member = 0; x.member = 0; }  
```