---
title: "심각한 오류 C1013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1013"
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 여는 괄호가 너무 많습니다.  
  
 단일 식에 너무 많은 괄호 수준이 포함되어 있습니다. 식을 단순화하거나 여러 개의 문으로 분리합니다.  
  
 Visual C\+\+ 6.0 SP3 이전 버전에서는 단일 식의 중첩된 괄호에 대한 제한이 59개였습니다. 현재 중첩된 괄호에 대한 제한은 256개입니다.