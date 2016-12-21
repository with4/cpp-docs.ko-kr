---
title: "컴파일러 오류 C2039 | Microsoft Docs"
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
  - "C2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2039"
ms.assetid: f9dfd521-9b36-4454-a69c-d63f45b606bb
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' : 'identifier2'의 멤버가 아닙니다.  
  
 구조체, 클래스 또는 공용 구조체의 멤버를 코드에서 잘못 호출하거나 참조하고 있습니다.  
  
## 예제  
 다음 샘플에서는 C2039 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2039.cpp  
struct S {  
   int mem0;  
} s, *pS = &s;  
  
int main() {  
   pS->mem1 = 0;   // C2039 mem1 is not a member  
   pS->mem0 = 0;   // OK  
}  
```  
  
## 예제  
 다음 샘플에서는 C2039 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2039_b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine( "{0}", DateTime::get_Now());   // C2039  
   Console::WriteLine( "{0}", DateTime::Now);   // OK  
   Console::WriteLine( "{0}", DateTime::Now::get());   // OK  
}  
```  
  
## 예제  
 다음 샘플에서는 C2039 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2039_c.cpp  
// compile with: /clr /c  
ref struct S {  
   property int Count {  
     int get();  
     void set(int i){}  
   };  
};  
  
int S::get_Count() { return 0; }   // C2039  
int S::Count::get() { return 0; }   // OK  
```  
  
## 예제  
 C2039는 기본 인덱서에 잘못 액세스하려는 경우에도 발생할 수 있습니다.  다음 샘플에서는 C\#으로 작성된 구성 요소를 정의합니다.  
  
```  
// C2039_d.cs  
// compile with: /target:library  
// a C# program  
[System.Reflection.DefaultMember("Item")]  
public class B {  
   public int Item {  
      get { return 13; }  
      set {}  
   }  
};  
```  
  
## 예제  
 다음 샘플에서는 C2039 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2039_e.cpp  
// compile with: /clr  
using namespace System;  
#using "c2039_d.dll"  
  
int main() {  
   B ^ b = gcnew B;  
   int n = b->default;   // C2039  
   // try the following line instead  
   // int n = b->Item;  
   Console::WriteLine(n);  
}  
```  
  
## 예제  
 제네릭을 사용하는 경우에도 C2039가 발생할 수 있습니다.  다음 샘플에서는 C2039 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2039_f.cpp  
// compile with: /clr  
interface class I {};  
  
ref struct R : public I {  
   virtual void f3() {}  
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f3();   // C2039  
   safe_cast<R^>(t)->f3();   // OK  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
## 예제  
 C2039 오류는 관리되는 리소스 또는 관리되지 않는 리소스를 해제하려고 하는 경우에 발생할 수 있습니다.  자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 를 참조하십시오.  
  
 다음 샘플에서는 C2039 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2039_g.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Threading;  
  
void CheckStatus( Object^ stateInfo ) {}  
  
int main() {  
   ManualResetEvent^ event = gcnew ManualResetEvent( false );     
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );  
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );  
  
   ((IDisposable ^)stateTimer)->Dispose();   // C2039  
  
   stateTimer->~Timer();   // OK  
}  
```