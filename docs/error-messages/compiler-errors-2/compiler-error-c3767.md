---
title: "컴파일러 오류 C3767 | Microsoft Docs"
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
  - "C3767"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3767"
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3767
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 후보 함수에 액세스할 수 없습니다.  
  
 클래스에 정의된 friend 함수가 전역 네임스페이스 범위에서 정의되고 선언된 것으로 간주되지 않습니다.  그러나 인수 종속성을 조회하여 찾을 수 있습니다.  
  
 C3767은 컴파일러의 변경 사항으로 인해 발생할 수도 있습니다. **\/clr** 컴파일에서 네이티브 형식은 이제 기본적으로 private입니다. 자세한 내용은 [형식 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)를 참조하십시오.  
  
 다음 샘플에서는 C3767 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3767a.cpp  
// compile with: /clr  
using namespace System;  
public delegate void TestDel();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;  
};  
  
public ref class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass^ patient = gcnew MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass^ x = gcnew MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2^ y = gcnew MyClass2();  
   y->Test();  
};  
```  
  
 다음 샘플에서는 C3767 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3767b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__delegate void TestDel();  
  
public __gc class MyClass {  
public:  
   static __event TestDel * MyClass_Event;  
};  
  
public __gc class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass* patient = new MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass* x = new MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2 * y = new MyClass2();  
   y->Test();  
};  
```  
  
 다음 샘플에서는 C3767 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3767c.cpp  
// compile with: /clr /c  
  
ref class Base  {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
ref class Der : public Base {  
   void Method() {  
      ((Base^)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 다음 샘플에서는 C3767 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3767d.cpp  
// compile with: /clr:oldSyntax /c  
  
__gc class Base {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
__gc class Der : public Base {  
   void Method() {  
      ((Base*)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 Visual C\+\+ .NET 2002에서는 컴파일러가 기호를 조회하는 방법을 변경했습니다.  이전에는 일부 경우에 지정된 네임스페이스에서 컴파일러가 자동으로 기호를 찾았습니다.  지금은 인수 종속성 조회를 사용합니다.  
  
 다음 샘플에서는 C3767 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3767e.cpp  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3767 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
 Visual C\+\+ .NET 2003 및 Visual C\+\+ .NET 2002에서 유효한 코드의 경우 클래스 범위에서 friend를 선언하고 네임스페이스 범위에서 이를 정의합니다.  
  
```  
// C3767f.cpp  
class MyClass {  
   int m_private;  
   friend void func();  
};  
  
void func() {  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main() {  
   func();  
}  
```