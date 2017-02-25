---
title: "컴파일러 오류 C2013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2013"
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\>'가 없습니다.  
  
 `#include` 지시문에 닫는 꺾쇠 괄호가 없습니다. 오류를 해결하려면 닫는 대괄호를 추가합니다.  
  
 다음 샘플에서는 C2013을 생성합니다.  
  
```  
// C2013.cpp #include <stdio.h    // C2013  
```  
  
 해결 방법:  
  
```  
// C2013b.cpp // compile with: /c #include <stdio.h>  
```