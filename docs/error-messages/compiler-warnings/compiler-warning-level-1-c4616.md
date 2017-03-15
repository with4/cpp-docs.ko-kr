---
title: "컴파일러 경고 (수준 1) C4616 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4616"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4616"
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4616
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : 경고 번호 'number'은\(는\) 올바른 컴파일러 경고가 아닙니다.  
  
 [경고](../../preprocessor/warning.md) pragma에 지정한 경고 번호를 다시 할당할 수 없습니다.  pragma는 무시됩니다.  
  
 다음 샘플에서는 C4616 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4616.cpp  
// compile with: /W1 /c  
#pragma warning( disable : 0 )   // C4616  
#pragma warning( disable : 999 )   // OK  
#pragma warning( disable : 4998 )   // OK  
```