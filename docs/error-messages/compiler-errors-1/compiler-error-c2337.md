---
title: "컴파일러 오류 C2337 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2337"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2337"
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2337
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute name': 특성을 찾을 수 없습니다.  
  
 이 버전의 Visual C\+\+에서 지원되지 않는 특성을 사용했습니다.  
  
 다음 샘플에서는 C2337을 생성합니다.  
  
```  
// C2337.cpp // compile with: /c [emitidl]; [module(name="x")]; [grasshopper]   // C2337, not a supported attribute class a{};  
```