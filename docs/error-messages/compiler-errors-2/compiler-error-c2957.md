---
title: "컴파일러 오류 C2957 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2957"
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delim': 왼쪽 구분 기호가 잘못되었습니다. '\<'가 필요합니다.  
  
 제네릭 클래스의 형식이 잘못되었습니다.  
  
 다음 샘플에서는 C2957을 생성합니다.  
  
```  
// C2957.cpp // compile with: /clr /LD generic << class T>   // C2957 // try the following line instead // generic < class T> gc class C {};  
```