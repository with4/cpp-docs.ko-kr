---
title: "Compiler Error C3353 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3353"
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compiler Error C3353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delegate': 대리자는 전역 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에서만 만들어질 수 있습니다.  
  
 [\_\_delegate](../../misc/delegate.md) 또는 [delegate](../../windows/delegate-cpp-component-extensions.md) 키워드로 선언된 대리자는 전역 범위에서만 선언할 수 있습니다.  
  
 다음 샘플에서는 C3353을 생성합니다.  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```