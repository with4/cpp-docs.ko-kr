---
title: "컴파일러 오류 C2353 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2353"
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예외 사양이 허용되지 않습니다.  
  
 관리되는 클래스의 멤버 함수에 대한 예외 사양이 허용되지 않습니다.  
  
 다음 샘플에서는 C2353 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2353.cpp  
// compile with: /clr /c  
ref class X {  
   void f() throw(int);   // C2353  
   void f();   // OK  
};  
```