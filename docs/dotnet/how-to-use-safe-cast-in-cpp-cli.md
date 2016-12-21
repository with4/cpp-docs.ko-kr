---
title: "방법: C++/CLI에서 safe_cast 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "safe_cast 키워드[C++], 업캐스팅"
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++/CLI에서 safe_cast 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 응용 프로그램에서 safe\_cast를 사용하는 방법을 보여줍니다.  [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]에서 safe\_cast에 대한 추가 정보는, [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)를 참조하십시오.  
  
## 업캐스팅  
 업캐스트는 파생 된 형식을 해당 기본 클래스 중 하나로 캐스팅하는 것입니다.  이 캐스트는 안전하고 명시적인 캐스트 표기법을 요구하지 않습니다.  다음 예제는 `safe_cast`를 사용하거나 그것 없이 업캐스팅을 수행하는 방법을 보여줍니다.  
  
```  
// safe_upcast.cpp  
// compile with: /clr  
using namespace System;  
interface class A {  
   void Test();  
};  
  
ref struct B : public A {  
   virtual void Test() {  
      Console::WriteLine("in B::Test");  
   }  
  
   void Test2() {  
      Console::WriteLine("in B::Test2");  
   }  
};  
  
ref struct C : public B {  
   virtual void Test() override {  
      Console::WriteLine("in C::Test");  
   };  
};  
  
int main() {  
   C ^ c = gcnew C;  
  
   // implicit upcast  
   B ^ b = c;  
   b->Test();  
   b->Test2();  
  
   // upcast with safe_cast  
   b = nullptr;  
   b = safe_cast<B^>(c);  
   b->Test();  
   b->Test2();  
}  
```  
  
  **in C::Test**  
**in B::Test2**  
**in C::Test**  
**in B::Test2**   
## 다운캐스팅  
 다운캐스트는 기본 클래스에서 기본 클래스에서 파생 된 클래스로 캐스팅됩니다.  다운캐스트는 런타임에 주소 지정된 개체가 실제로 파생된 개체를 주소 지정하는 경우에만 안전합니다.  `static_cast`, `safe_cast`가 동적 검사를 수행하는 것과는 달리, 변환이 실패했을 경우 <xref:System.InvalidCastException>를 발생시킵니다.  
  
```  
// safe_downcast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class A { void Test(); };  
  
ref struct B : public A {  
   virtual void Test() {   
      Console::WriteLine("in B::Test()");  
   }  
  
   void Test2() {   
      Console::WriteLine("in B::Test2()");  
   }  
};  
  
ref struct C : public B {  
   virtual void Test() override {   
      Console::WriteLine("in C::Test()");  
   }  
};  
  
interface class I {};  
  
value struct V : public I {};  
  
int main() {  
   A^ a = gcnew C();  
   a->Test();  
   B^ b = safe_cast<B^>(a);  
   b->Test();  
   b->Test2();  
  
   V v;   
   I^ i = v;   // i boxes V  
   V^ refv = safe_cast<V^>(i);   
  
   Object^ o = gcnew B;  
   A^ a2= safe_cast<A^>(o);  
}  
```  
  
  **in C::Test\(\)**  
**in C::Test\(\)**  
**in B::Test2\(\)**   
## 사용자 정의 변환을 통한 safe\_cast  
 다음 예제는 사용자 정의 변환을 호출하는 `safe_cast`을 사용할 수 있는 방법을 보여줍니다.  
  
```  
// safe_cast_udc.cpp  
// compile with: /clr  
using namespace System;  
value struct V;  
  
ref struct R {  
   int x;  
   R() {  
      x = 1;  
   }  
  
   R(int argx) {  
      x = argx;  
   }  
  
   static operator R::V^(R^ r);  
};  
  
value struct V {  
   int x;  
   static operator R^(V& v) {  
      Console::WriteLine("in operator R^(V& v)");  
      R^ r = gcnew R();  
      r->x = v.x;    
      return r;  
   }  
  
   V(int argx) {  
      x = argx;  
   }  
};  
  
   R::operator V^(R^ r) {  
      Console::WriteLine("in operator V^(R^ r)");  
      return gcnew V(r->x);  
   }  
  
int main() {  
   bool fReturnVal = false;  
   V v(2);  
   R^ r = safe_cast<R^>(v);   // should invoke UDC  
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC  
}  
```  
  
  **in operator R^\(V& v**  
**in operator V^\(R^ r\)**   
## safe\_cast 및 boxing 작업  
 **boxing**  
  
 boxing은 컴파일러\-주입, 사용자 정의 변환으로서 정의됩니다.  따라서 CLR 힙에서 값을 상자에 넣기 위해서 `safe_cast`를 사용할 수 있습니다.  
  
 다음 샘플은 간단한 boxing과 사용자 정의 값 형식을 보여줍니다.  `safe_cast`는 원시 스택에 놓인 값 형식 변수를 상자에 넣으므로, 가비지 수집 힙에서 변수에 할당될 수 있습니다.  
  
```  
// safe_cast_boxing.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct I {};  
  
value struct V : public I {   
   int m_x;  
  
   V(int i) : m_x(i) {}  
};  
  
int main() {  
   // box a value type  
   V v(100);  
   I^ i = safe_cast<I^>(v);  
  
   int x = 100;  
   V^ refv = safe_cast<V^>(v);  
   int^ refi = safe_cast<int^>(x);  
}  
```  
  
 다음 예제는 `safe_cast` 작업에서 사용자 정의 변환보다 우선권을 가진 boxing을 보여줍니다.  
  
```  
// safe_cast_boxing_2.cpp  
// compile with: /clr  
static bool fRetval = true;  
  
interface struct I {};  
value struct V : public I {  
   int x;  
  
   V(int argx) {  
      x = argx;  
   }  
  
   static operator I^(V v) {  
      fRetval = false;  
      I^ pi = v;  
      return pi;  
   }  
};  
  
ref struct R {  
   R() {}  
   R(V^ pv) {}  
};  
  
int main() {  
   V v(10);  
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"  
}  
```  
  
 **unboxing**  
  
 unboxing은 컴파일러\-주입, 사용자 정의 변환으로서 정의됩니다.  따라서 CLR 힙에서 값을 상자에서 꺼내기 위해서 `safe_cast`를 사용할 수 있습니다.  
  
 unboxing은 사용자 정의 변환이지만, boxing과는 달리 unboxing은 명시적으로, 즉 `static_cast`, C\-style cast 또는 `safe_cast`에 의해 수행됩니다. unboxing은 암시적으로 수행되지 않습니다.  
  
```  
// safe_cast_unboxing.cpp  
// compile with: /clr  
int main() {  
   System::Object ^ o = 42;  
   int x = safe_cast<int>(o);  
}  
```  
  
 다음 예제는 값 형식과 원시 형식을 사용한 unboxing을 보여줍니다.  
  
```  
// safe_cast_unboxing_2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct I {};  
  
value struct VI : public I {};  
  
void test1() {  
   Object^ o = 5;  
   int x = safe_cast<Int32>(o);  
}  
  
value struct V {  
   int x;  
   String^ s;  
};  
  
void test2() {  
   V localv;  
   Object^ o = localv;  
   V unboxv = safe_cast<V>(o);  
}  
  
void test3() {  
   V localv;  
   V^ o2 = localv;  
   V unboxv2 = safe_cast<V>(o2);  
}  
  
void test4() {  
   I^ refi = VI();  
   VI vi  = safe_cast<VI>(refi);  
}  
  
int main() {  
   test1();  
   test2();  
   test3();  
   test4();  
}  
```  
  
## safe\_cast 및 제네릭 형식  
 다음 예제는 제네릭 형식을 사용하여 다운캐스트를 수행하는 `safe_cast`를 사용할 수 있는 방법을 보여줍니다.  
  
```  
// safe_cast_generic_types.cpp  
// compile with: /clr  
interface struct I {};  
  
generic<class T> where T:I  
ref struct Base {  
   T t;  
   void test1() {}  
};  
  
generic<class T> where T:I  
ref struct Derived:public Base <T> {};  
  
ref struct R:public I {};  
  
typedef Base<R^> GBase_R;  
typedef Derived<R^> GDerived_R;  
  
int main() {  
   GBase_R^ br = gcnew GDerived_R();  
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);  
}  
```  
  
## 참고 항목  
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)