---
title: "컴파일러 경고(수준 1) C4077 | Microsoft Docs"
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
  - "C4077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4077"
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

알 수 없는 check\_stack 옵션입니다.  
  
 이전 **check\_stack** pragma 형식이 알 수 없는 인수와 함께 사용되었습니다. 인수는 `+`, `-`, `(on)`, `(off)`이거나 비어 있어야 합니다.  
  
 컴파일러가 해당 pragma를 무시하고 스택 검사를 변경되지 않은 상태로 그대로 둡니다.  
  
## 예제  
  
```  
// C4077.cpp // compile with: /W1 /LD #pragma check_stack yes // C4077 #pragma check_stack +    // Correct old form #pragma check_stack (on) // Correct new form  
```