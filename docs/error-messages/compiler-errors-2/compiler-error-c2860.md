---
title: "컴파일러 오류 C2860 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2860"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2860"
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2860
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'void'는 '\(void\)'를 제외한 인수 형식일 수 없습니다.  
  
 `void` 형식은 다른 인수를 포함하는 인수 형식으로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2860 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2860.cpp  
// compile with: /c  
void profunc1(void, int i);   // C2860  
void func10(void);   // OK  
```