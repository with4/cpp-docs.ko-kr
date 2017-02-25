---
title: "컴파일러 오류 C2436 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2436"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2436"
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 생성자 이니셜라이저 목록에 멤버 함수 또는 중첩 클래스가 있습니다.  
  
 생성자 이니셜라이저 목록에 있는 멤버 함수나 지역 클래스를 초기화할 수 없습니다.  
  
 다음 샘플에서는 C2436 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```