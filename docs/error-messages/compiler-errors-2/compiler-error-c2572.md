---
title: "컴파일러 오류 C2572 | Microsoft Docs"
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
  - "C2572"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2572"
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2572
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::member' : 기본 매개 변수 재정의. 매개 변수 param  
  
 기본 매개 변수는 재정의할 수 없습니다.  매개 변수에 다른 값이 필요한 경우에는 기본 매개 변수를 정의하지 않은 채로 두어야 합니다.  
  
 다음 샘플에서는 C2572 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2572.cpp  
// compile with: /c  
void f(int i = 1);   // function declaration  
  
// function definition  
void f(int i = 1) {}   // C2572  
  
// try the following line instead  
// void f(int i) {}  
```