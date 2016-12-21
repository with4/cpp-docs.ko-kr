---
title: "컴파일러 경고 (수준 1) C4227 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4227"
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오래된 구문을 사용했습니다 : 참조의 한정자가 무시됩니다.  
  
 `const` 또는 `volatile`과 같은 한정자를 C\+\+ 참조에 사용하는 것은 오래된 방법입니다.  
  
## 예제  
  
```  
// C4227.cpp  
// compile with: /W1 /c  
int j = 0;  
int &const i = j;   // C4227  
```