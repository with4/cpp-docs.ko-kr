---
title: "컴파일러 오류 C3668 | Microsoft Docs"
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
  - "C3668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3668"
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' : 재정의 지정자 'override'가 있는 메서드가 기본 클래스 메서드를 재정의하지 않았습니다.  
  
 함수에서 존재하지 않는 함수를 재정의하려고 했습니다.  
  
 자세한 내용은 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3668 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3668.cpp  
// compile with: /c  
__interface I {  
   void f(int);   // virtual by default  
};  
  
class J {  
public:  
   void g(int);  
   virtual void h(int);  
};  
  
struct R : I,J {  
   virtual void f() override {}   // C3668  
   virtual void f(int) override {}   // OK  
  
   virtual void g(int) override {}   // C3668  
   virtual void h(int) override {}   // OK  
};  
```