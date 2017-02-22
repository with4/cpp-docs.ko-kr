---
title: "컴파일러 경고(수준 1) C4006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4006"
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고(수준 1) C4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#undef에 식별자가 필요합니다.  
  
 `#undef` 지시문에서 정의 해제할 식별자를 지정하지 않았습니다. 지시문이 무시됩니다. 이 경고를 해결하려면 식별자를 지정해야 합니다. 다음 샘플에서는 C4006을 생성합니다.  
  
```  
// C4006.cpp // compile with: /W1 #undef   // C4006 // try.. // #undef TEST int main() { }  
```