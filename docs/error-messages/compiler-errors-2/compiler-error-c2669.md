---
title: "컴파일러 오류 C2669 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2669"
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멤버 함수는 익명 공용 구조체에 사용할 수 없습니다.  
  
 익명 공용 구조체가 멤버 함수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2669 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  
## 참고 항목  
 [익명 공용 구조체](../../misc/anonymous-unions.md)