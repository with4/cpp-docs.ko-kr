---
title: "컴파일러 오류 C2293 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2293"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2293"
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2293
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 멤버 변수를 \_\_based 지정자로 사용할 수 없습니다.  
  
 `__based` 한정자에 대한 지정자는 비멤버 포인터여야 합니다.  
  
 다음 샘플에서는 C2293을 생성합니다.  
  
```  
// C2293.cpp // compile with: /c class A { static int *i; void __based(i) *bp;   // C2293 void *bp2;   // OK };  
```