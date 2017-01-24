---
title: "컴파일러 오류 C2150 | Microsoft Docs"
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
  - "C2150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2150"
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 비트 필드의 형식은 'int', 'signed int' 또는 'unsigned int'이어야 합니다.  
  
 비트 필드는 `int`, `signed` `int` 또는 `unsigned` `int`여야 합니다.  
  
 다음 샘플에서는 C2150을 생성합니다.  
  
```  
// C2150.cpp // compile with: /c struct A { float a : 8;    // C2150 int i : 8;   // OK };  
```