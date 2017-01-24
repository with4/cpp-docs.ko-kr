---
title: "연산자를 &#39;&lt;keyword&gt;&#39;로 선언할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc33013"
  - "bc33013"
helpviewer_keywords: 
  - "BC33013"
ms.assetid: bfd805f4-e30e-4553-9cb7-2690595f0480
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연산자를 &#39;&lt;keyword&gt;&#39;로 선언할 수 없습니다.
연산자가 연산자 정의에 유효하지 않은 키워드로 선언되었습니다.  
  
 모든 연산자는 [Public](../Topic/Public%20\(Visual%20Basic\).md)과 [Shared](../Topic/Shared%20\(Visual%20Basic\).md)로 선언되어야 합니다. 또한 변환 연산자는 [Widening](../Topic/Widening%20\(Visual%20Basic\).md) 또는 [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md)로 선언됩니다\(둘 다 함께는 불가능\). 연산자 정의는 선택적으로 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) 또는 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md) 키워드를 포함할 수 있습니다.[Operator Statement](../Topic/Operator%20Statement.md)에 다른 모든 키워드는 허용되지 않습니다.  
  
 **오류 ID:** BC33013  
  
### 이 오류를 해결하려면  
  
-   연산자 정의에서 잘못된 키워드를 제거합니다.  
  
## 참고 항목  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)