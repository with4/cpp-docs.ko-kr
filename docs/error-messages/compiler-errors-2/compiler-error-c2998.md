---
title: "컴파일러 오류 C2998 | Microsoft Docs"
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
  - "C2998"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2998"
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2998
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 템플릿 정의일 수 없습니다.  
  
 컴파일러에서 템플릿 정의에 사용되는 구문을 처리할 수 없습니다.  
  
 다음 샘플에서는 C2998을 생성합니다.  
  
```  
// C2998.cpp // compile with: /c template <class T> int x = 1018; // C2998  
```