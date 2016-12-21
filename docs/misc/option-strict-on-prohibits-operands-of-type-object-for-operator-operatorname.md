---
title: "Option Strict On에서는 &#39;&lt;operatorname&gt;&#39; 연산자에 대해 Object 형식의 피연산자를 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30038"
  - "vbc30038"
helpviewer_keywords: 
  - "BC30038"
ms.assetid: eb047d36-1fb4-460d-ae98-c76f31a89bed
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 &#39;&lt;operatorname&gt;&#39; 연산자에 대해 Object 형식의 피연산자를 사용할 수 없습니다.
개체 변수에 대해 정의된 유일한 연산자는 `Is` 및 `TypeOf...Is`입니다.`Option Strict`가 `On`일 때 모든 피연산자는 지정된 연산자에 대해 정의된 데이터 형식이어야 합니다.  
  
 **오류 ID:** BC30038  
  
### 이 오류를 해결하려면  
  
-   `CInt` 또는 `CStr`와 같은 적절한 형식 변환 함수를 사용하여 피연산자를 연산자에 대해 정의된 데이터 형식으로 변환합니다.  
  
## 참고 항목  
 [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [Type Conversion Functions](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md)