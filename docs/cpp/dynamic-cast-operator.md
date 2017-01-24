---
title: "dynamic_cast 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "dynamic_cast"
  - "dynamic_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dynamic_cast 키워드[C++]"
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dynamic_cast 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

피연산자 `expression`을 `type-id` 형식의 개체로 변환합니다.  
  
## 구문  
  
```  
  
dynamic_cast < type-id > ( expression )  
```  
  
## 설명  
 `type-id`는 포인터나 앞서 정의한 클래스 유형이나 "빈 공간에 대한 포인터"에 대한 참조가 되어야 합니다.  만약 `type-id`이 포인터이거나 l\-값이라면, 만약 `type-id`이 참조라면, `expression`의 유형은 포인터가 되어야 합니다.  
  
 정적 및 동적 캐스팅 변환과 각각 사용하기에 적합한 시기에 대한 자세한 내용은 [static\_cast](../cpp/static-cast-operator.md)를 참조하십시오.  
  
 관리 코드의 `dynamic_cast` 동작에 다음과 같은 두 개의 주요 변경 내용이 있습니다.  
  
-   boxed enum의 기본 형식에 대한 포인터의 `dynamic_cast`는 변환된 포인터 대신 0을 반환하며 런타임에 실패합니다.  
  
-   `type-id`가 런타임에 캐스팅에 실패하는 값 형식에 대한 내부 포인터일 때 `dynamic_cast`는 더 이상 예외를 throw하지 않습니다.  이제 캐스팅은 throwing 대신 0 포인터 값을 반환합니다.  
  
 `type-id`가 `expression`의 액세스 가능하며 명확한 직접 또는 간접적 기본 클래스에 대한 포인터인 경우 `type-id` 형식의 고유한 하위 개체에 대한 포인터가 결과입니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_1.cpp  
// compile with: /c  
class B { };  
class C : public B { };  
class D : public C { };  
  
void f(D* pd) {  
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class  
                                   // pc points to C subobject of pd   
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class  
                                   // pb points to B subobject of pd  
}  
```  
  
 이 변환 형식은 유래된 클래스에서 이것은 유래한 클래스까지 포인터를 클래스 계층구조 위로 이동시키기 때문에 "업캐스트"라고 부릅니다.  업캐스팅은 암시적 변환입니다.  
  
 `type-id`가 void\*인 경우 `expression`의 실제 형식을 확인하도록 런타임 검사가 수행됩니다.  결과는 `expression`이 가리키는 전체 개체에 대한 포인터입니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_2.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
  
void f() {  
   A* pa = new A;  
   B* pb = new B;  
   void* pv = dynamic_cast<void*>(pa);  
   // pv now points to an object of type A  
  
   pv = dynamic_cast<void*>(pb);  
   // pv now points to an object of type B  
}  
```  
  
 `type-id`가 유효하지 않은 경우\* `expression`에서 가리킨 개체를 `type-id`에서 가리킨 형식으로 변환할 수 있는지를 확인하기 위한 런타임 검사가 수행됩니다.  
  
 `expression` 형식이 `type-id` 형식의 기본 클래스인 경우 `expression`이 실제로 `type-id` 형식의 완전한 개체를 가리키는지 확인하기 위한 런타임 검사가 수행됩니다.  이 값이 true이면 결과는 `type-id` 형식의 완전한 개체에 대한 포인터입니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_3.cpp  
// compile with: /c /GR  
class B {virtual void f();};  
class D : public B {virtual void f();};  
  
void f() {  
   B* pb = new D;   // unclear but ok  
   B* pb2 = new B;  
  
   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D  
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D  
}  
```  
  
 이 변환 형식은 주어진 클래스에서 여기에서 유래된 클래스까지 포인터를 클래스 계층구조 아래로 이동시키기 때문에 "다운캐스트"라고 부릅니다.  
  
 다중 상속의 경우에는 모호성의 가능성이 있습니다.  다음 그림에 표시된 클래스 계층 구조를 살펴보십시오.  
  
 CLR 형식의 경우 `dynamic_cast`에서는 변환이 암시적으로 수행되거나 MSIL `isinst` 명령인 경우 no\-op이 되며, 여기서 명령은 동적 검사를 수행하거나 변환에 실패한 경우 `nullptr`을 반환합니다.  
  
 다음 샘플은 클래스가 특정 형식의 인스턴스인지 여부를 결정하기 위해 `dynamic_cast`를 사용합니다.  
  
```  
// dynamic_cast_clr.cpp  
// compile with: /clr  
using namespace System;  
  
void PrintObjectType( Object^o ) {  
   if( dynamic_cast<String^>(o) )  
      Console::WriteLine("Object is a String");  
   else if( dynamic_cast<int^>(o) )  
      Console::WriteLine("Object is an int");  
}  
  
int main() {  
   Object^o1 = "hello";  
   Object^o2 = 10;  
  
   PrintObjectType(o1);  
   PrintObjectType(o2);  
}  
```  
  
 ![여러 상속을 보여 주는 클래스 계층 구조](../cpp/media/vc39011.png "vc39011")  
다중 상속을 보여 주는 클래스 계층 구조  
  
 `D` 형식의 개체에 대한 포인터는 `B` 또는 `C`로 안전하게 캐스팅될 수 있습니다.  하지만 `D`가 `A` 개체를 가리키도록 캐스팅될 경우 `A`의 어떤 인스턴스가 결과로 나타날까요?  이는 모호한 캐스팅 오류를 일으킬 수 있습니다.  이 문제를 해결하려면 두 개의 모호하지 않은 캐스트를 수행할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_4.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
class D : public B {virtual void f();};  
  
void f() {  
   D* pd = new D;  
   B* pb = dynamic_cast<B*>(pd);   // first cast to B  
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous  
}  
```  
  
 가상 기본 클래스를 사용할 때 추가 모호성이 제공될 수 있습니다.  다음 그림에 표시된 클래스 계층 구조를 살펴보십시오.  
  
 ![가상 기본 클래스를 보여 주는 클래스 계층 구조](../cpp/media/vc39012.png "vc39012")  
가상 기본 클래스를 보여 주는 클래스 계층 구조  
  
 이 계층 구조에서 `A`는 가상 기본 클래스입니다.  가상 기본 클래스에 대한 정의는 [가상 기본 클래스](../misc/virtual-base-classes.md)를 참조하십시오.  `E` 클래스 인스턴스와 `A` 하위 개체를 가리키는 포인터에는 `dynamic_cast` 에 대한 포인터 `B`는 모호성 때문에 실패합니다.  먼저 완전한  `E`  개체로 돌아간 후, 모호하지 않은 방식으로 계층 구조를 백업하는 방식을 진행하여 정확한  `B`  개체에 도달해야 합니다.  
  
 다음 그림에 표시된 클래스 계층 구조를 살펴보십시오.  
  
 ![중복된 기본 클래스를 보여 주는 클래스 계층 구조](../cpp/media/vc39013.png "vc39013")  
중복 기본 클래스를 보여 주는 클래스 계층 구조  
  
 `E` 형식의 개체와 `D`를 가리키는 포인터의 경우 `D` 하위 개체에서 `A` 하위 개체의 맨 왼쪽으로 탐색하려면 세 가지 변환이 이루어질 수 있습니다.  `D` 포인터에서 `E` 포인터로의 `dynamic_cast` 변환, `E`에서 `B`로의 변환 \(`dynamic_cast` 또는 암시적 변환 모두\), 마지막으로 `B`에서 `A`로의 암시적 변환을 수행할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_5.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B : public A {virtual void f();};  
class C : public A { };  
class D {virtual void f();};  
class E : public B, public C, public D {virtual void f();};  
  
void f(D* pd) {  
   E* pe = dynamic_cast<E*>(pd);  
   B* pb = pe;   // upcast, implicit conversion  
   A* pa = pb;   // upcast, implicit conversion  
}  
```  
  
 `dynamic_cast` 연산자도 "크로스 캐스팅" 수행하는 데 사용할 수 있습니다. 같은 클래스 계층 구조를 사용하여 완전 개체가 `E` 형식인 경우에 한해 한 예로, `B` 하부개체에서  `D` 하부 개체로 포인터를 캐스팅할 수 있습니다.  
  
 크로스 캐스팅을 고려할 때 실제로 단 두 단계만에 `D`에 대한 포인터에서 가장 왼쪽 `A` 하위 개체에 대한 포인터로 변환을 수행할 수 있습니다.  `D`에서 `B`로, 그리고 `B`에서 `A`로의 암시적 변환으로 크로스 캐스팅을 수행할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_6.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B : public A {virtual void f();};  
class C : public A { };  
class D {virtual void f();};  
class E : public B, public C, public D {virtual void f();};  
  
void f(D* pd) {  
   B* pb = dynamic_cast<B*>(pd);   // cross cast  
   A* pa = pb;   // upcast, implicit conversion  
}  
```  
  
 null 포인터 값은 `dynamic_cast`에 의해 대상 형식의 null 포인터 값으로 변환됩니다.  
  
 `dynamic_cast < type-id > ( expression )`를 사용하는 경우, `expression`이 `type-id` 형식으로 안전하게 변환될 수 없으면 런타임 검사로 인해 캐스팅이 실패하게 됩니다.  예를 들면 다음과 같습니다.  
  
```  
// dynamic_cast_7.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
  
void f() {  
   A* pa = new A;  
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;  
   // B not derived from A  
}  
```  
  
 포인터 형식의 실패한 캐스트 값이 null 포인터입니다.  형식을 참조하는 데 실패한 캐스팅은 [bad\_cast Exception](../cpp/bad-cast-exception.md)을 throw합니다. `expression`이 유효한 개체를 가리키거나 참조하지 못하는 경우 `__non_rtti_object` 예외가 throw됩니다.  
  
 `__non_rtti_object` 예외에 대한 설명은 [typeid](../cpp/typeid-operator.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 개체\(C 구조체\)에 기본 클래스\(구조체 A\) 포인터를 만듭니다.  여기에 가상 함수가 있다는 사실은 런타임 다형성을 가능하게 합니다.  
  
 또한 샘플에서 계층 구조의 비가상 함수를 호출합니다.  
  
```  
// dynamic_cast_8.cpp  
// compile with: /GR /EHsc  
#include <stdio.h>  
#include <iostream>  
  
struct A {  
    virtual void test() {  
        printf_s("in A\n");  
   }  
};  
  
struct B : A {  
    virtual void test() {  
        printf_s("in B\n");  
    }  
  
    void test2() {  
        printf_s("test2 in B\n");  
    }  
};  
  
struct C : B {  
    virtual void test() {  
        printf_s("in C\n");  
    }  
  
    void test2() {  
        printf_s("test2 in C\n");  
    }  
};  
  
void Globaltest(A& a) {  
    try {  
        C &c = dynamic_cast<C&>(a);  
        printf_s("in GlobalTest\n");  
    }  
    catch(std::bad_cast) {  
        printf_s("Can't cast to C\n");  
    }  
}  
  
int main() {  
    A *pa = new C;  
    A *pa2 = new B;  
  
    pa->test();  
  
    B * pb = dynamic_cast<B *>(pa);  
    if (pb)  
        pb->test2();  
  
    C * pc = dynamic_cast<C *>(pa2);  
    if (pc)  
        pc->test2();  
  
    C ConStack;  
    Globaltest(ConStack);  
  
   // will fail because B knows nothing about C  
    B BonStack;  
    Globaltest(BonStack);  
}  
```  
  
  **C에서는**  
**GlobalTest,**   
**B의 test2를**  
**C로 캐스팅할 수 없습니다.**   
## 참고 항목  
 [캐스팅 연산자](../cpp/casting-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)