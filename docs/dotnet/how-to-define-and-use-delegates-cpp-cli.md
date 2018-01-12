---
title: "방법: 대리자 정의 및 사용 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: delegates
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f400a03f1b9ae877ee7ec681cb038698a92598a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-define-and-use-delegates-ccli"></a>방법: 대리자 정의 및 사용(C++/CLI)
이 문서에서는 C + 대리자 정의 및 사용 하는 방법을 보여 줍니다. + CLI 합니다.  
  
 .NET Framework 대리자의 수를 제공 하지만 때로는 해야할 새 대리자를 정의 합니다.  
  
 다음 코드 예제에서는 명명 된 대리자를 정의 `MyCallback`합니다. 이벤트 처리 코드-이 새 대리자가 실행 될 때 호출 되는 함수-의 반환 형식이 있어야 합니다. `void` 알아본는 <xref:System.String> 참조 합니다.  
  
 Main 함수에 정의 된 정적 메서드를 사용 하 여 `SomeClass` 를 인스턴스화하는 `MyCallback` 위임 합니다. 그러면 대리자 대리자 개체를 문자열을 "단일" 전송 하 여 볼 수 있듯이이 함수를 호출 하는 다른 방법을 됩니다. 다음, 추가 인스턴스 `MyCallback` 함께 연결 되어 있고 다음 대리자 개체를 한 번 호출 하 여 실행 합니다.  
  
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
  
 **출력**  
  
```Output  
static SomeClass::Func - single  
static SomeClass::Func - chained  
static SomeClass::Func - chained  
OtherClass::Method - chained, num = 99  
OtherClass::Method - chained, num = 100  
```  
  
 다음 코드 예제에는 값 클래스의 멤버와 함께 대리자를 연결 하는 방법을 보여 줍니다.  
  
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
  
 **출력**  
  
```Output  
test  
test  
```  
  
## <a name="how-to-compose-delegates"></a>대리자를 구성 하는 방법  
 사용할 수는 "`-`" 구성 요소 대리자 구성 된 대리자에서 제거 하는 연산자입니다.  
  
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
  
 **출력**  
  
```Output  
Invoking delegate a:  
Hello, A!  
Invoking delegate b:  
  Goodbye, B!  
Invoking delegate c:  
Hello, C!  
  Goodbye, C!  
Invoking delegate d:  
  Goodbye, D!  
```  
  
## <a name="pass-a-delegate-to-a-native-function-that-expects-a-function-pointer"></a>대리자를 전달 ^ 함수 포인터를 필요로 하는 네이티브 함수에  
 관리 되는 구성 요소에서 호출할 수 있습니다 함수를 사용 하는 네이티브 함수 포인터 매개 변수 있는 네이티브 함수 그런 후 호출할 수는 관리 되는 구성 요소의 대리자의 멤버 함수입니다.  
  
 이 샘플은 네이티브 함수를 내보내는.dll을 만듭니다.  
  
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
  
 다음 샘플.dll을 사용 하며 함수 포인터를 필요로 하는 네이티브 함수에 대리자 핸들을 전달 합니다.  
  
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
  
 **출력**  
  
```Output  
Call to Managed Function  
```  
  
## <a name="to-associate-delegates-with-unmanaged-functions"></a>관리 되지 않는 함수와 함께 대리자를 연결 하려면  
 대리자를 네이티브 함수를 연결 하려면 네이티브 함수를에서 래핑하는 관리 되는 형식 및 함수를 통해 호출할 수를 선언 해야 `PInvoke`합니다.  
  
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
  
 **출력**  
  
```Output  
hello  
```  
  
## <a name="to-use-unbound-delegates"></a>바인딩되지 않은 대리자를 사용 하려면  
 함수를 호출 하는 대리자를 호출할 때 형식의 인스턴스를 전달 하려면 바인딩되지 않은 대리자를 사용할 수 있습니다.  
  
 바인딩되지 않은 대리자는 컬렉션의 개체를 반복 하려는 경우에 특히 유용-를 사용 하 여 [각 항목에 대해에서](../dotnet/for-each-in.md) 키워드-각 인스턴스에서 멤버 함수를 호출 합니다.  
  
 인스턴스화를 선언 하는 방법은 및 호출 바인딩되며 대리자에 바인딩되지 않은:  
  
|작업|대리자 연결|바인딩되지 않은 대리자|  
|------------|---------------------|-----------------------|  
|선언|대리자 서명 대리자를 통해 호출 하려는 함수의 서명이 일치 해야 합니다.|대리자 서명의 첫 번째 매개 변수는 가장 유형의 `this` 호출 하려는 개체에 대 한 합니다.<br /><br /> 후 첫 번째 매개 변수는 대리자 서명 대리자를 통해 호출 하려는 함수의 서명이 일치 해야 합니다.|  
|인스턴스화합니다|바운드 대리자를 인스턴스화하는 인스턴스 함수 또는 전역 또는 정적 멤버 함수를 지정할 수 있습니다.<br /><br /> 인스턴스 함수를 지정 하려면 첫 번째 매개 변수 형식의 멤버 함수를 호출할 인스턴스 이며 두 번째 매개 변수를 호출 하려는 함수의 주소입니다.<br /><br /> 전역 또는 정적 멤버 함수를 호출 하려는 경우 전역 함수 이름 또는 정적 멤버 함수의 이름을 전달 됩니다.|바인딩되지 않은 대리자를 인스턴스화하면 호출할 함수의 주소로 전달 됩니다.|  
|호출|바운드 대리자를 호출할 때 대리자 서명에 따라 필요한 매개 변수에 전달 됩니다.|경계로 동일 대리자 설명 하지만 첫 번째 매개 변수를 호출 하려면 함수를 포함 하는 개체의 인스턴스를 이어야 합니다.|  
  
 이 샘플에는 선언, 인스턴스화 및 바인딩되지 않은 대리자를 호출 하는 방법을 보여 줍니다.  
  
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
  
 **출력**  
  
```Output  
2  
3  
2  
3  
2  
7  
8  
7  
8  
7  
```  
  
 다음 샘플에서는 바인딩되지 않은 대리자를 사용 하는 방법을 보여 줍니다. 및 [각 항목에 대해에서](../dotnet/for-each-in.md) 키워드를 컬렉션의 개체를 반복 하 고 각 인스턴스에서 멤버 함수를 호출 합니다.  
  
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
  
 이 샘플은 속성의 접근자 함수에 바인딩되지 않은 대리자를 만듭니다.  
  
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
  
 **출력**  
  
```Output  
11  
```  
  
 다음 샘플에 있는 하나의 인스턴스만 바인딩되어 있고 하나의 인스턴스만 바인딩되어 있지 않습니다. 멀티 캐스트 대리자를 호출 하는 방법을 보여 줍니다.  
  
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
  
 **출력**  
  
```Output  
in f(R ^ r)  
in f()  
```  
  
 다음 샘플에는 만들어 바인딩되지 않은 제네릭 대리자를 호출 하는 방법을 보여 줍니다.  
  
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
  
 **출력**  
  
```Output  
12  
14  
```  
  
## <a name="see-also"></a>참고 항목  
 [delegate(C++ 구성 요소 확장)](../windows/delegate-cpp-component-extensions.md)