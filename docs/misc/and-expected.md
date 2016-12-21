---
title: "&#39;And&#39;가 필요합니다. | Microsoft Docs"
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
  - "vbc36620"
  - "bc36620"
helpviewer_keywords: 
  - "BC36620"
ms.assetid: b3d21d4d-86c0-44d2-8afc-c19d375e9ddd
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;And&#39;가 필요합니다.
`And` 이외의 다른 비교 연산자가 사용되어 `Join` 또는 `Group Join` 절에서 두 개 이상의 `Equals` 연산자를 결합하였습니다.`And` 연산자만 `Join` 또는 `Group Join` 절에서 여러 `Equals` 연산자를 결합할 수 있습니다.  
  
 **오류 ID:** BC36620  
  
### 이 오류를 해결하려면  
  
1.  `Equals` 절의 구조체를 바꾸고 `And` 연산자만 사용하여 비교합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim petOwnersJoin = From pers In people _  
                        Join pet In pets _  
                        On pet.Owner Equals pers And _  
                           pet.Name = pers.PetName_  
                        Select pers, pet  
    ```  
  
## 참고 항목  
 [How to: Combine Data with Joins](../Topic/How%20to:%20Combine%20Data%20with%20LINQ%20by%20Using%20Joins%20\(Visual%20Basic\).md)   
 [Join Clause](../Topic/Join%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)