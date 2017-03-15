---
title: "컴파일러 오류 C3654 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3654"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3654"
ms.assetid: 57d96e3f-6bbb-4eaa-934b-26c23b4ceb2e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3654
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'text' : 명시적 재정의에 구문 오류가 있습니다.  
  
 명시적 재정의에 예기치 않은 문자열이 있습니다.  자세한 내용은 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3654 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3654.cpp  
// compile with: /clr /c  
public ref struct B {  
   virtual void f() = 0;  
   virtual void g() = 0;  
   virtual void h() = 0;  
};  
  
public ref struct Q : B {  
   virtual void f() = B::f, 3 {}   // C3654  
   // try the following line instead  
   // virtual void g() = B::g, B::h {}  
};  
```