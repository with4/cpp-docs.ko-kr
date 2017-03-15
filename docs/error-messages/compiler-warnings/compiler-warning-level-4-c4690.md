---
title: "컴파일러 경고(수준 4) C4690 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4690"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4690"
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고(수준 4) C4690
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\[ emitidl\( pop \) \]: 데이터를 넣는 작업\(push\)보다 데이터를 꺼내는 작업\(pop\)이 많습니다.  
  
 [emitidl](../../windows/emitidl.md) 특성을 넣은 횟수보다 꺼낸 횟수가 한 번 더 많습니다.  
  
## 예제  
 다음 샘플에서는 C4690을 생성합니다.  
  
```  
// C4690.cpp // compile with: /c /W4 [emitidl(pop)];   // C4690 class x {};  
```