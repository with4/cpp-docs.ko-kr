---
title: "컴파일러 오류 C2805 | Microsoft Docs"
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
  - "C2805"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2805"
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2805
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이항 'operator operator'에 매개 변수가 너무 적습니다.  
  
 이항 연산자에 매개 변수가 없습니다.  
  
 다음 샘플에서는 C2805 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2805.cpp  
// compile with: /c  
class X {  
public:  
   X operator< ( void );   // C2805 must take one parameter  
   X operator< ( X );   // OK  
};  
```