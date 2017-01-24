---
title: "컴파일러 경고(수준 1) C4122 | Microsoft Docs"
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
  - "C4122"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4122"
ms.assetid: 9a83eb0d-8708-42f7-988a-b0b6f2f646a0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4122
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': alloc\_text는 C 링크가 있는 함수에만 적용될 수 있습니다.  
  
 **alloc\_text** pragma는 **extern c**로 선언된 함수에만 적용됩니다. 외부 C\+\+ 함수와 함께 사용할 수 없습니다.  
  
 pragma가 무시됩니다.