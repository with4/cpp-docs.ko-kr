---
title: "컴파일러 경고(수준 4) C4718 | Microsoft Docs"
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
  - "C4718"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4718"
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4718
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function call': 재귀 호출에 파생 작업이 없습니다. 삭제하고 있습니다.  
  
 함수가 재귀 호출을 포함하지만 그렇지 않은 경우 부수적인 효과가 없습니다. 이 함수에 대한 호출을 삭제하는 중입니다. 프로그램의 정확성에는 영향을 주지 않지만 동작에는 영향을 줍니다. 호출을 그대로 유지하면 런타임 스택 오버플로 예외가 발생할 수 있지만 호출을 삭제하면 이 가능성을 제거합니다.