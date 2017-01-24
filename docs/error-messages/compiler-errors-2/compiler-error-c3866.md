---
title: "컴파일러 오류 C3866 | Microsoft Docs"
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
  - "C3866"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3866"
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3866
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수 호출에 인수 목록이 없습니다.  
  
 비정적 멤버 함수 안에서 소멸자나 종료자 호출에 인수 목록이 없습니다.  
  
 다음 샘플에서는 C3866 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```