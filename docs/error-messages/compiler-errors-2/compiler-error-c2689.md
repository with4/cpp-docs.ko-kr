---
title: "컴파일러 오류 C2689 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2689"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2689"
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2689
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : friend 함수는 지역 클래스 내에 정의할 수 없습니다.  
  
 friend 함수는 지역 클래스 내에 선언할 수는 있지만 정의할 수는 없습니다.  
  
 다음 샘플에서는 C2689 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2689.cpp  
// compile with: /c  
void g() {  
   void f2();  
   class X {  
      friend void f2(){}   // C2689  
      friend void f2();   // OK  
   };  
}  
```