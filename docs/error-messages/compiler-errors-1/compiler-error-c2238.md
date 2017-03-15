---
title: "컴파일러 오류 C2238 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2238"
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token' 앞에 예기치 않은 토큰이 있습니다.  
  
 잘못된 토큰이 있습니다.  
  
 다음 샘플에서는 C2238을 생성합니다.  
  
```  
// C2238.cpp // compile with: /c class v { virtual: int vvv;   // C2238 };  
```