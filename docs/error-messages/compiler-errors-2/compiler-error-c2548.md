---
title: "컴파일러 오류 C2548 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2548"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2548"
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2548
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::member' : 매개 변수 parameter에 대한 기본 매개 변수가 없습니다.  
  
 기본 매개 변수 목록에 매개 변수가 없습니다.  매개 변수 목록에 기본 매개 변수를 제공한 경우에는 이후의 모든 매개 변수에 대한 기본 매개 변수를 정의해야 합니다.  
  
## 예제  
 다음 샘플에서는 C2548 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2548.cpp  
// compile with: /c  
void func( int = 1, int, int = 3);  // C2548  
  
// OK  
void func2( int, int, int = 3);  
void func3( int, int = 2, int = 3);  
```