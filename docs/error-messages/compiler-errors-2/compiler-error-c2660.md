---
title: "컴파일러 오류 C2660 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2660"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2660"
ms.assetid: 2e01a1db-4f00-4df6-a04d-cb6f70a6922b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 컴파일러 오류 C2660
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수는 number개의 매개 변수를 사용하지 않습니다.  
  
 함수가 잘못된 개수의 매개 변수를 통해 호출되었습니다.  
  
 C2660은 이름이 동일한 MFC 멤버 함수가 아니라 Windows API 함수를 잘못 호출한 경우에 발생할 수 있습니다.  이 문제를 해결하려면 다음을 수행하십시오.  
  
-   멤버 함수 호출의 형식을 따르도록 함수 호출을 조정합니다.  
  
-   범위 결정 연산자\(`::`\)를 사용하여 컴파일러가 전역 이름 범위에서 함수 이름을 검색하도록 합니다.  
  
## 예제  
 다음 샘플에서는 C2660 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2660.cpp  
void func( int, int ) {}  
  
int main() {  
   func( 1 );   // C2660 func( int ) not declared  
   func( 1, 0 );   // OK  
}  
```  
  
## 예제  
 C2660은 관리되는 형식의 Dispose 메서드를 직접 호출하려고 하는 경우에도 발생할 수 있습니다.  자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 를 참조하십시오.  다음 샘플에서는 C2660 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2660_a.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Threading;  
  
void CheckStatus( Object^ stateInfo ) {}  
  
int main() {  
   ManualResetEvent^ event = gcnew ManualResetEvent( false );     
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );  
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );  
  
   stateTimer->Dispose();   // C2660  
   stateTimer->~Timer();   // OK  
}  
```  
  
## 예제  
 C2660은 파생 클래스가 함수를 숨기는 경우에 발생합니다.  
  
```  
// C2660b.cpp  
// C2660 expected  
#include <stdio.h>  
  
class f {  
public:  
   void bar() {  
      printf_s("in f::bar\n");  
    }  
};  
  
class f2 : public f {  
public:  
   void bar(int i){printf("in f2::bar\n");}  
   // Uncomment the following line to resolve.  
   // using f::bar;   // - using declaration added  
   // or  
   // void bar(){__super::bar();}  
};  
  
int main() {  
   f2 fObject;  
   fObject.bar();  
}  
```  
  
## 예제  
 C2660은 인덱싱된 속성을 잘못 호출하는 경우에 발생할 수 있습니다.  
  
```  
// C2660c.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(1.9) {}  
   property double MyProp[] {  
      double get(int i) {  
         return d;  
      }  
   }   // end MyProp definition  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   System::Console::WriteLine(MyX->MyProp(1));   // C2660  
   System::Console::WriteLine(MyX->MyProp[1]);   // OK  
}  
```  
  
## 예제  
 C2660은 인덱싱된 속성을 잘못 호출하는 경우에 발생할 수 있습니다.  
  
```  
// C2660d.cpp  
// compile with: /clr  
ref class A{  
public:  
   property int default[int,int] {  
      int get(int a, int b) {  
         return a + b;  
      }  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   int x = a[3][5];   // C2660  
   int x2 = a[3,5];   // OK  
}  
```  
  
## 예제  
 C2660은 템플릿 클래스에 새 연산자를 정의했지만 해당 형식이 바깥쪽 형식이 아닌 개체를 새 연산자가 만드는 경우에 발생할 수 있습니다.  
  
```  
// C2660e.cpp  
// compile with: /c  
#include <malloc.h>  
  
template <class T> class CA {  
private:  
    static T** line;  
   void* operator new (size_t, int i) {   
      return 0;  
   }  
   void operator delete(void* pMem, int i) {  
      free(pMem);  
   }  
  
public:  
   CA () { new (1) T(); }   // C2660  
   // try the following line instead  
   // CA () { new (1) CA<int>(); }  
};  
  
typedef CA <int> int_CA;  
  
void AAA() {  
   int_CA  list;  
}  
```