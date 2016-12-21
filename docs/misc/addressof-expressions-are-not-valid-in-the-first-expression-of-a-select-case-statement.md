---
title: "&#39;Select Case&#39; 문의 첫 번째 식에서는 &#39;AddressOf&#39; 식을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36636"
  - "vbc36636"
helpviewer_keywords: 
  - "BC36636"
ms.assetid: 2ccc0ccc-d4d0-4910-8859-dedfa57c8126
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Select Case&#39; 문의 첫 번째 식에서는 &#39;AddressOf&#39; 식을 사용할 수 없습니다.
`Select Case` 문에서 테스트 식에 대해 `AddressOf` 식을 사용할 수 없습니다.`AddressOf` 식이 함수 대리자를 반환하고 `Select Case` 문의 테스트 식이 기본 데이터 형식이어야 합니다.  
  
 **오류 ID:** BC36636  
  
### 이 오류를 해결하려면  
  
-   코드를 검사하여 `If...Then...Else` 문과 같은 다른 조건부 생성이 적합한지 결정합니다.  
  
## 참고 항목  
 [AddressOf Operator](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [If...Then...Else Statement](../Topic/If...Then...Else%20Statement%20\(Visual%20Basic\).md)   
 [Select...Case Statement](../Topic/Select...Case%20Statement%20\(Visual%20Basic\).md)