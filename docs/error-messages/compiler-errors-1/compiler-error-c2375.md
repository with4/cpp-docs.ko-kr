---
title: "컴파일러 오류 C2375 | Microsoft Docs"
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
  - "C2375"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2375"
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2375
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 재정의. 링크가 다릅니다.  
  
 함수가 다른 링크 지정자를 사용하여 이미 선언되었습니다.  
  
 다음 샘플에서는 C2375를 생성합니다.  
  
```  
// C2375.cpp // compile with: /Za /c extern void func( void ); static void func( void );   // C2375 static void func2( void );   // OK  
```