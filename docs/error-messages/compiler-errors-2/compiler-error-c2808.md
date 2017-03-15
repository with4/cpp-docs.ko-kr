---
title: "컴파일러 오류 C2808 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2808"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2808"
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2808
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단항 'operator operator'에 형식 매개 변수가 너무 많습니다.  
  
 단항 연산자가 비 void 매개 변수 목록을 사용합니다.  
  
 다음 샘플에서는 C2808 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2808.cpp  
// compile with: /c  
class X {  
public:  
   X operator! ( X );   // C2808 nonvoid parameter list  
   X operator! ( void );   // OK  
};  
  
```