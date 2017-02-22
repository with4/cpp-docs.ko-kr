---
title: "컴파일러 오류 C2142 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2142"
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수 선언이 서로 다릅니다. 가변 매개 변수를 그 중 하나에만 지정했습니다.  
  
 함수의 한쪽 선언 부분에는 가변 매개 변수 목록이 포함되지만,  다른 한쪽에는 포함되지 않습니다.  ANSI C\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서만 그렇습니다.  
  
 다음 샘플에서는 C2142 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```