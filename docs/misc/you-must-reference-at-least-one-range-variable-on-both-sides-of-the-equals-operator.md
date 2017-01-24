---
title: "&#39;Equals&#39; 연산자의 양쪽에서 범위 변수를 하나 이상 참조해야 합니다. | Microsoft Docs"
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
  - "vbc36622"
  - "bc36622"
helpviewer_keywords: 
  - "BC36622"
ms.assetid: 8d301227-131d-4977-b3ff-1fc4e427f8fa
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Equals&#39; 연산자의 양쪽에서 범위 변수를 하나 이상 참조해야 합니다.
'Equals' 연산자의 양쪽에서 범위 변수를 하나 이상 참조해야 합니다. \<variable\(s\)\> 범위 변수는 'Equals' 연산자의 한 쪽에 표시되어야 하며 \<variable\(s\)\> 범위 변수는 다른 쪽에 표시되어야 합니다.  
  
 LINQ 쿼리에 조인할 컬렉션에 대해 식별된 범위 변수는 식별된 컬렉션에 따라 `Equals` 연산자의 반대쪽에 있어야 합니다. 즉, 조인 중인 컬렉션 중 하나에 대해 식별된 범위 변수는 조인 중인 다른 컬렉션의 범위 변수에 대해 `Equals` 연산자의 반대쪽에 있어야 합니다. 각 컬렉션의 범위 변수를 `Equals` 연산자의 같은 쪽에 함께 사용할 수 없습니다.  
  
 조인 중인 각 컬렉션의 변수 중 적어도 하나는 `Equals` 연산자의 양쪽에서 참조되어야 합니다.  
  
 **오류 ID:** BC36622  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)   
 [Join Clause](../Topic/Join%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [From Clause](../Topic/From%20Clause%20\(Visual%20Basic\).md)   
 [Select Clause](../Topic/Select%20Clause%20\(Visual%20Basic\).md)