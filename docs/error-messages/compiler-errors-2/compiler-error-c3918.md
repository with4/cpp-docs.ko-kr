---
title: "컴파일러 오류 C3918 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3918"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3918"
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3918
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member'은\(는\) 데이터 멤버여야 합니다.  
  
 C3918 오류는 이벤트와 관련된 여러 가지 원인으로 인해 발생할 수 있습니다.  
  
## 예제  
 C3918 오류는 현재 컨텍스트에서 클래스 멤버가 필요하기 때문에 발생할 수 있습니다.  다음 샘플에서는 C3918 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3918.cpp  
// compile with: /clr /c  
public ref class C {  
public:  
   System::Object ^ o;  
   delegate void Del();  
  
   event Del^ MyEvent {  
      void add(Del^ev) {  
         if ( MyEvent != nullptr) {}   // C3918  
         if ( o != nullptr) {}   // OK  
   }  
   void remove(Del^){}  
   }  
};  
```  
  
## 예제  
 또한 trivial 이벤트가 null인지 확인하려고 하는 경우에도 C3918이 발생할 수 있습니다. 즉, 이벤트 이름으로 이벤트에 대한 지원 저장소 대리자에 더 이상 직접 액세스할 수 없습니다.  
  
 다음 샘플에서는 C3918 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3918_2.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int MyDel(int);  
  
interface struct IEFace {  
   event MyDel ^ E;  
};  
  
ref struct EventSource : public IEFace {  
   virtual event MyDel ^ E;  
   void Fire_E(int i) {  
      if (E)   // C3918  
         E(i);  
   }  
};  
```  
  
## 예제  
 C3918은 이벤트에 대한 알림 신청을 잘못한 경우에도 발생할 수 있습니다.  다음 샘플에서는 C3918 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3918_3.cpp  
// compile with: /clr /c  
using namespace System;  
  
public delegate void del();  
  
public ref class A {  
public:  
   event del^ e {  
      void add(del ^handler ) {  
         d += handler;  
      }  
  
      void remove(del ^handler) {  
         d -= handler;  
      }  
  
      void raise() {   
         d();  
      }  
   }  
  
   del^ d;  
   void f() {}  
  
   A() {  
      e = gcnew del(this, &A::f);   // C3918  
      // try the following line instead  
      // e += gcnew del(this, &A::f);  
      e();  
   }  
};  
  
int main() {  
   A a;  
}  
```