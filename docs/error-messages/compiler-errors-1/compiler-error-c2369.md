---
title: "컴파일러 오류 C2369 | Microsoft Docs"
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
  - "C2369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2369"
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'array': 재정의. 첨자가 다릅니다.  
  
 배열이 다른 아래 첨자로 이미 선언되었습니다.  
  
 다음 샘플에서는 C2369를 생성합니다.  
  
```  
// C2369.cpp // compile with: /c int a[10]; int a[20];   // C2369 int b[20];   // OK  
```