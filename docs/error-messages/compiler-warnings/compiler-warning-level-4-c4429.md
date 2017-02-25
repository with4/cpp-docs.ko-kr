---
title: "컴파일러 경고 (수준 4) C4429 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4429"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4429"
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4429
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

유니버설 문자 이름이 불완전하거나 형식이 잘못되었을 수 있습니다.  
  
 컴파일러에서 형식이 잘못된 유니버설 문자 이름일 수 있는 문자 시퀀스를 발견했습니다.  유니버설 문자 이름은 `\u` 뒤에 네 개의 16진수 값이 오거나, `\U` 뒤에 여덟 개의 16진수 값이 오는 형식입니다.  
  
 다음 샘플에서는 C4429 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4429.cpp  
// compile with: /W4 /WX  
int \ug0e4 = 0;   // C4429  
// Try the following line instead:  
// int \u00e4 = 0;   // OK, a well-formed universal character name.  
```