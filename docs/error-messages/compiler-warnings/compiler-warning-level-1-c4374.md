---
title: "컴파일러 경고 (수준 1) C4374 | Microsoft Docs"
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
  - "C4374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4374"
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function1': 인터페이스 메서드는 비가상 메서드 'function2'에 의해 구현되지 않습니다.  
  
 컴파일러가 메서드 정의에서 [virtual](../../cpp/virtual-specifier.md) 키워드를 찾지 못했습니다.  
  
 다음 샘플에서는 C4374 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4374.cpp  
// compile with: /clr /W1 /c /WX  
public interface class I {  
   void f();  
};  
  
public ref struct B {  
   void f() {  
      System::Console::WriteLine("B::f()");  
   }  
};  
  
public ref struct C {  
   virtual void f() {  
      System::Console::WriteLine("C::f()");  
   }  
};  
  
public ref struct D : B, I {};   // C4374  
public ref struct E : C, I {};   // OK  
```