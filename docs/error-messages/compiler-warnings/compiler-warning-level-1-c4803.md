---
title: "컴파일러 경고 (수준 1) C4803 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4803"
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 1) C4803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' : raise 메서드에 이벤트 'event'의 저장소 클래스와 다른 저장소 클래스가 있습니다.  
  
 이벤트 메서드에는 이벤트 선언에 있는 저장소 클래스와 같은 저장소 클래스가 있어야 하므로  컴파일러에서 이벤트의 메서드에 저장소 클래스가 같아지도록 적용합니다.  
  
 인터페이스에서 이벤트를 구현하는 클래스가 있으면 이 경고가 발생합니다.  컴파일러에서 인터페이스의 이벤트에 대한 raise 메서드를 암시적으로 생성하지 않습니다.  클래스에 해당 인터페이스를 구현할 때 컴파일러에서 raise 메서드를 암시적으로 생성하고 해당 메서드는 가상이 아니므로 경고가 발생합니다.  
  
 경고를 해제하는 방법에 대한 자세한 내용은 [warning](../../preprocessor/warning.md) pragma를 참조하십시오.  
  
## 예제  
 C4803은 **\/clr**를 사용할 때 발생할 수 있습니다.  이벤트 사용에 대한 자세한 내용은 [event](../../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C4803 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  
  
## 예제  
 C4803은 **\/clr:oldSyntax**를 사용할 때 발생할 수 있습니다.  다음 샘플에서는 C4803 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4803_b.cpp  
// compile with: /clr:oldSyntax /W1  
using namespace System;  
  
public __delegate void Del();  
  
__gc struct E {  
   Del* _pd1;  
   virtual __event void add_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Combine(_pd1, pd1));  
   }  
  
   virtual __event void remove_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Remove(_pd1, pd1));  
   }  
  
   __event void raise_E1 () {   // C4803, add virtual  
      if (_pd1)  
         _pd1->Invoke();  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E* ep = new E;  
   ep->E1 += new Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= new Del(ep, &E::func);  
   ep->E1();  
}  
```