---
title: "컴파일러 오류 C2184 | Microsoft Docs"
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
  - "C2184"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2184"
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2184
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': \_\_except 식의 형식이 잘못되었습니다. 정수여야 합니다.  
  
 형식이 [\_\_except](../../c-language/try-except-statement-c.md) 문에서 사용되었지만 형식이 허용되지 않습니다.  
  
 다음 샘플에서는 C2184를 생성합니다.  
  
```  
// C2184.cpp void f() { int * p; __try{} __except(p){};   // C2184 }  
```  
  
 해결 방법:  
  
```  
// C2184b.cpp // compile with: /c void f() { int i = 0; __try{} __except(i){}; }  
```