---
title: "컴파일러 경고 (수준 1) C4114 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4114"
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동일한 형식 한정자를 두 번 이상 사용했습니다.  
  
 형식 선언 또는 정의에서 형식 한정자\(**const**, `volatile`, **signed** 또는 `unsigned`\)가 두 번 이상 사용되었습니다.  이는 Microsoft 확장\(\/Ze\)에서는 경고이며 ANSI 규격\(\/Za\)에서는 오류입니다.  
  
 다음 샘플에서는 C4114 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 다음 샘플에서는 C4114 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```