---
title: "방법: 대리자 정의 및 사용(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대리자"
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 대리자 정의 및 사용(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 에서 대리자가 사용되고 정의되는 방법을 보여줍니다.  
  
 .NET Framework 는 대리자의 수를 제공하지만, 때로는 새로운 대리자들을 정의해야 할 수 도 있습니다.  
  
 다음 예제 코드에서는 `MyCallback` 라는 대리자를 정의합니다.  이벤트 처리 코드\- 이 함수는 새로운 대리자가 발생될때 호출됩니다\- 는 `void` 의 형식을 반환해야하고 <xref:System.String> 참조를 받습니다.  
  
 Main 함수는 `MyCallback` 대리자를 인스턴스로 하는 `SomeClass` 에 의해 정의되는 정적인 메서드를 사용합니다.  대리자 개체로 "단일" 문자열을 보내는 것을 설명하는 것처럼, 대리자는 이 함수 호출의 대체 메서드가 됩니다.  그 다음, `MyCallback` 의 추가 인스턴스는 함께 연결되고 대리자 개체를 한 번 호출함으로써 실행됩니다.  
  
```  
// use_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
ref class SomeClass  
{  
public:  
   static void Func(String^ str)  
   {  
      Console::WriteLine("static SomeClass::Func - {0}", str);  
   }  
};  
  
ref class OtherClass  
{  
public:  
   OtherClass( Int32 n )   
   {  
      num = n;  
   }  
  
   void Method(String^ str)   
   {  
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",   
         str, num);  
   }  
  
   Int32 num;  
};  
  
delegate void MyCallback(String^ str);  
  
int main( )   
{  
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);     
   callback("single");   
  
   callback += gcnew MyCallback(SomeClass::Func);     
  
   OtherClass^ f = gcnew OtherClass(99);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   f = gcnew OtherClass(100);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   callback("chained");  
  
   return 0;  
}  
```  
  
 **Output**  
  
  **정적 SomeClass::Func \- single**  
**정적 SomeClass::Func \- chained**  
**정적 SomeClass::Func \- chained**  
**OtherClass::Method \- chained, num \= 99**  
**OtherClass::Method \- chained, num \= 100** 다음 코드 예제는 값 클래스의 멤버를 사용하여 대리자를 연결하는 방법을 보여줍니다.  
  
```  
// mcppv2_del_mem_value_class.cpp  
// compile with: /clr  
using namespace System;  
public delegate void MyDel();  
  
value class A {  
public:  
   void func1() {  
      Console::WriteLine("test");  
   }  
};  
  
int main() {  
   A a;  
   A^ ah = a;  
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a  
   f();  
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);  
   f2();  
}  
```  
  
 **Output**  
  
  **테스트**  
**테스트**   
## 대리자를 구성하는 방법  
 구성된 대리자로부터 구성요소 대리자를 제거하기 위해 "`-`" 연산자를 사용할 수 있습니다.  
  
```  
// mcppv2_compose_delegates.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDelegate(String ^ s);  
  
ref class MyClass {  
public:  
   static void Hello(String ^ s) {  
      Console::WriteLine("Hello, {0}!", s);  
   }  
  
   static void Goodbye(String ^ s) {  
      Console::WriteLine("  Goodbye, {0}!", s);  
   }  
};  
  
int main() {  
  
   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);  
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);  
   MyDelegate ^ c = a + b;  
   MyDelegate ^ d = c - a;  
  
   Console::WriteLine("Invoking delegate a:");  
   a("A");  
   Console::WriteLine("Invoking delegate b:");  
   b("B");  
   Console::WriteLine("Invoking delegate c:");  
   c("C");  
   Console::WriteLine("Invoking delegate d:");  
   d("D");  
}  
```  
  
 **Output**  
  
  **대리자 a 호출:**  
**Hello, A\!**  
**대리자 b 호출:**  
 **Goodbye, B\!**  
**대리자c 호출 :**  
**Hello, C\!**  
 **Goodbye, C\!**  
**대리자d 호출:**  
 **Goodbye, D\!**   
## 함수포인터를 제외한 원래 함수에 대한 대리자^를 전달합니다.  
 관리되는 구성요소로부터 원래 함수가 있는 함수 포인터 매개변수를 사용하여 원래 함수를 호출 할 수 있고, 그다음 관리되는 구성요소의 대리자의 멤버 함수를 호출할 수 있습니다.  
  
 이 샘플은 원래 함수를 내보내는 .dll을 만듭니다.  
  
```  
// delegate_to_native_function.cpp  
// compile with: /LD  
#include < windows.h >  
extern "C" {  
   __declspec(dllexport)  
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {  
      mgdFunc("Call to Managed Function");  
   }  
}  
```  
  
 다음 샘플은 .dll을 사용하고 팜수 포인터를 제외한 원래 함수의 대리자 핸들을 전달합니다.  
  
```  
// delegate_to_native_function_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
delegate void Del(String ^s);  
public ref class A {  
public:  
   void delMember(String ^s) {  
      Console::WriteLine(s);  
   }  
};  
  
[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]  
extern "C" void nativeFunction(Del ^d);  
  
int main() {  
   A ^a = gcnew A;  
   Del ^d = gcnew Del(a, &A::delMember);  
   nativeFunction(d);   // Call to native function  
}  
```  
  
 **Output**  
  
  **관리되는 함수를 호출합니다.**   
## 관리되지 않는 함수를 사용하여 대리자를 연결하는 것.  
 원래 함수를 사용하여 대리자를 연결하는 것은, 관리되는 형식에서 원래 함수를 래핑해야하고 `PInvoke` 통해 호출되는 함수를 선언해야합니다.  
  
```  
// mcppv2_del_to_umnangd_func.cpp  
// compile with: /clr  
#pragma unmanaged  
extern "C" void printf(const char*, ...);  
class A {  
public:  
   static void func(char* s) {  
      printf(s);  
   }  
};  
  
#pragma managed  
public delegate void func(char*);   
  
ref class B {  
   A* ap;  
  
public:  
   B(A* ap):ap(ap) {}  
   void func(char* s) {  
      ap->func(s);   
   }  
};  
  
int main() {  
   A* a = new A;  
   B^ b = gcnew B(a);  
   func^ f = gcnew func(b, &B::func);  
   f("hello");  
   delete a;  
}  
```  
  
 **Output**  
  
  **hello**   
## 바인딩 되지 않은 대리자들을 사용하는 것.  
 대리자가 호출될 때 호출하길 원하는 함수 형식의 인스턴스를 전달하기 위해 바인딩되지 않은 대리자를 사용할 수 있습니다.  
  
 만일 컬렉션\-[for each, in](../dotnet/for-each-in.md) 을 사용하는 키워드\-에서 개체를 통해 반복적으로 하길 원한다면, 바인딩되지 않은 대리자는 특히 유용하고 각 인스턴스에서 멤버 함수를 호출합니다.  
  
 선언하고 인스턴스화하며 바인딩된 대리자와 그렇지 않은 대리자를 사용하는 방법.  
  
|작업|바인딩된 대리자|바인딩되지 않은 대리자|  
|--------|--------------|------------------|  
|Declare|대리자 시그니처는 대리자를 통해 호출을 원하는 함수의 시그니처와 일치해야합니다.|대리자 시그니처의 첫 번째 매개 변수는 호출하기 원하는 개체에 대한 `this` 의 형식입니다.<br /><br /> 첫 번째 매개 변수이후, 대리자 시그니처는 대리자를 통해 호출하려는 함수의 시그니처와 일치 해야합니다.|  
|Instantiate|바인딩된 대리자를 인스턴스화 할때, 인스턴스 함수를 지정하거나 전역 또는 정적 멤버함수를 지정할 수 있습니다.<br /><br /> 인스턴스 함수를 지정하기 위해, 첫 번째 매개변수는 호출하길 원하는 멤버 함수에 대한 형식의 인스턴스이고, 두 번째 매개변수는 호출하길 원하는 함수의 주소입니다.<br /><br /> 만일 전역 또는 정적 멤버 함수를 호출하려면, 정적 멤버 함수의 이름 또는 전역 함수의 이름을 전달합니다.|바인딩되지 않은 대리자를 인스턴스화할 때, 호출 하려는 함수의 주소를 전달합니다.|  
|Call|바인딩된 대리자를 호출할 때, 대리자 시그니처를 필요로하는 매개변수를 전달합니다.|동일한 바인딩된 매개변수지만, 첫 번째 매개변수는 호출하길 원하는 함수를 포함하는 개체의 인스턴스여야 한다는 부분을 기억해야 합니다.|  
  
 이 샘플은 선언하는 것과 인스턴스화하는 것, 바인딩되지 않은 대리자들을 호출하는 방법을 설명합니다:  
  
```  
// unbound_delegates.cpp  
// compile with: /clr  
ref struct A {  
   A(){}  
   A(int i) : m_i(i) {}  
   void Print(int i) { System::Console::WriteLine(m_i + i);}  
  
private:  
   int m_i;  
};  
  
value struct V {  
   void Print() { System::Console::WriteLine(m_i);}  
   int m_i;  
};  
  
delegate void Delegate1(A^, int i);  
delegate void Delegate2(A%, int i);  
  
delegate void Delegate3(interior_ptr<V>);  
delegate void Delegate4(V%);  
  
delegate void Delegate5(int i);  
delegate void Delegate6();  
  
int main() {  
   A^ a1 = gcnew A(1);  
   A% a2 = *gcnew A(2);  
  
   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);  
   // delegate takes a handle  
   Unbound_Delegate1(a1, 1);  
   Unbound_Delegate1(%a2, 1);  
  
   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);  
   // delegate takes a tracking reference (must deference the handle)  
   Unbound_Delegate2(*a1, 1);  
   Unbound_Delegate2(a2, 1);  
  
   // instantiate a bound delegate to an instance member function  
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);  
   Bound_Del(1);  
  
   // instantiate value types  
   V v1 = {7};  
   V v2 = {8};  
  
   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);  
   Unbound_Delegate3(&v1);  
   Unbound_Delegate3(&v2);  
  
   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);  
   Unbound_Delegate4(v1);  
   Unbound_Delegate4(v2);  
  
   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);  
   Bound_Delegate3();  
}  
```  
  
 **Output**  
  
  **2**  
**3**  
**2**  
**3**  
**2**  
**7**  
**8**  
**7**  
**8**  
**7** 다음 예제는 바인딩되지 않은 대리자를 사용 하는 방법과 각 인스턴스에서 멤버 함수를 호출하고 컬렉션에서 개체를 통해 반복하기 위해 [for each, in](../dotnet/for-each-in.md) 를 사용하는 방법을 보여줍니다.  
  
```  
// unbound_delegates_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref class RefClass {  
   String^ _Str;  
  
public:  
   RefClass( String^ str ) : _Str( str ) {}  
   void Print() { Console::Write( _Str ); }  
};  
  
delegate void PrintDelegate( RefClass^ );  
  
int main() {  
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );  
  
   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );  
  
   for ( int i = 0; i < a->Length; ++i )  
      a[i] = gcnew RefClass( i.ToString() );  
  
   for each ( RefClass^ R in a )  
      d( R );  
  
   Console::WriteLine();  
}  
```  
  
 이 샘플은 속성의 접근자 함수들에 대해 바인딩되지 않은 대리자를 만듭니다.  
  
```  
// unbound_delegates_3.cpp  
// compile with: /clr  
ref struct B {  
   property int P1 {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
  
private:  
   int m_i;  
};  
  
delegate void DelBSet(B^, int);  
delegate int DelBGet(B^);  
  
int main() {  
   B^ b = gcnew B;  
  
   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);  
   delBSet(b, 11);  
  
   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);     
   System::Console::WriteLine(delBGet(b));  
}  
```  
  
 **Output**  
  
  **11** 다음 샘플에서는 멀티캐스트 대리자를 호출하는 방법을 보여는데, 하나의 인스턴스를 바인딩한 장소에서 인스턴스의 바인딩을 해제합니다.  
  
```  
// unbound_delegates_4.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int i) : m_i(i) {}  
  
   void f(R ^ r) {  
      System::Console::WriteLine("in f(R ^ r)");  
   }  
  
   void f() {  
      System::Console::WriteLine("in f()");  
   }  
  
private:  
   int m_i;  
};  
  
delegate void Del(R ^);  
  
int main() {  
   R ^r1 = gcnew R(11);  
   R ^r2 = gcnew R(12);  
  
   Del^ d = gcnew Del(r1, &R::f);  
   d += gcnew Del(&R::f);  
   d(r2);  
};  
```  
  
 **Output**  
  
  **in f\(R ^ r\)**  
**in f\(\)** 다음 예제는 바인딩되지 않은 제네릭 대리자를 호출하고 만드는 방법을 보여줍니다.  
  
```  
// unbound_delegates_5.cpp  
// compile with: /clr  
ref struct R {  
   R(int i) : m_i(i) {}  
  
   int f(R ^) { return 999; }  
   int f() { return m_i + 5; }  
  
   int m_i;  
};  
  
value struct V {  
   int f(V%) { return 999; }  
   int f() { return m_i + 5; }   
  
   int m_i;  
};  
  
generic <typename T>  
delegate int Del(T t);  
  
generic <typename T>  
delegate int DelV(T% t);  
  
int main() {     
   R^ hr = gcnew R(7);  
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));  
  
   V v;  
   v.m_i = 9;  
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );  
}  
```  
  
 **Output**  
  
  **12**  
**14**   
## 참고 항목  
 [delegate](../windows/delegate-cpp-component-extensions.md)