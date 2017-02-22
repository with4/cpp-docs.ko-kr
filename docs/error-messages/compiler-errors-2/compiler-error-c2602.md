---
title: "컴파일러 오류 C2602 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2602"
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::Identifier'이\(가\) 기본 클래스 'class'의 멤버가 아닙니다.  
  
 `Identifier`는 기본 클래스에서 상속된 멤버가 아니므로 액세스할 수 없습니다.  
  
 다음 샘플에서는 C2602 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```