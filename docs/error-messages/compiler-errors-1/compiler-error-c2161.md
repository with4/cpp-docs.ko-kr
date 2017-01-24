---
title: "컴파일러 오류 C2161 | Microsoft Docs"
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
  - "C2161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2161"
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매크로 정의 끝에 '\#\#'이 올 수 없습니다.  
  
 매크로 정의가 토큰 붙여넣기 연산자\(\#\#\)로 종료되었습니다.  
  
 다음 샘플에서는 C2161 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2161.cpp // compile with: /c #define mac(a,b) a   // OK #define mac(a,b) a##   // C2161  
```