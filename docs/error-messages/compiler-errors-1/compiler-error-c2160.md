---
title: "컴파일러 오류 C2160 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2160"
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매크로 정의 시작에 '\#\#'이 올 수 없습니다.  
  
 매크로 정의가 토큰 붙여넣기 연산자\(\#\#\)로 시작되었습니다.  
  
 다음 샘플에서는 C2160을 생성합니다.  
  
```  
// C2160.cpp // compile with: /c #define mac(a,b) #a   // OK #define mac(a,b) ##a   // C2160  
```