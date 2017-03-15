---
title: "컴파일러 오류 C2586 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2586"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2586"
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2586
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 정의 변환 구문이 잘못되었습니다. 간접 참조가 잘못되었습니다.  
  
 변환 연산자의 간접 참조는 사용할 수 없습니다.  
  
 다음 샘플에서는 C2586 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// c2586.cpp  
// compile with: /c  
struct C {  
   * operator int();   // C2586  
   operator char();   // OK  
};  
```