---
title: "dynamic_cast 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dynamic_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29add795c7adeca67fc85c7cf3b1b90d17f804fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dynamiccast-operator"></a>dynamic_cast 연산자
피연산자를 변환 `expression` 유형의 개체로 `type-id`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dynamic_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>설명  
 `type-id` 포인터 또는 이전에 정의 된 클래스 형식에 대 한 참조 또는 "void 포인터" 이어야 합니다. `type-id`이 포인터인 경우 `expression`의 형식은 포인터여야 하며 `type-id`이 참조인 경우에는 l 값이어야 합니다.  
  
 참조 [static_cast](../cpp/static-cast-operator.md) 에 대 한 설명은 각 사용 하기에 적합 한 경우 및 정적 및 동적 캐스팅 변환 간의 차이입니다.  
  
 동작의 두 가지 주요 변경 내용이 `dynamic_cast` 관리 코드에서:  
  
-   `dynamic_cast`boxed 열거형의 내부 형식에 대 한 포인터로 변환 된 포인터 대신 0을 반환 하는 런타임 시 실패 합니다.  
  
-   `dynamic_cast`더 이상 예외를 throw 할 때 `type-id` 는 런타임 시 실패 한 캐스트를 통해 값 형식으로 내부 포인터입니다.  캐스팅 throw 하는 대신 0 포인터 값을 반환 합니다.  
  
 경우 `type-id` 는 명확한 액세스할 수 있는 직접 또는 간접 기본 클래스의에 대 한 포인터 `expression`, 형식의 고유한 하위 개체에 대 한 포인터 `type-id` 은 결과입니다. 예:  
  
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
  
 파생 클래스에서 파생 된 클래스에는 클래스 계층 구조 위로 포인터를 이동 하기 때문에 이러한 유형의 변환 "업캐스팅" 라고 합니다. 업 캐스트는 암시적으로 변환 합니다.  
  
 경우 `type-id` 은 void * 런타임 검사가 수행 되는 실제 유형의 확인 `expression`합니다. 결과 완전 한 가리키는 개체에 대 한 포인터는 `expression`합니다. 예:  
  
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
  
 경우 `type-id` void * 않습니다 런타임 검사가 수행 되는 경우는 가리키는 개체를 보려면 `expression` 가리키는 형식으로 변환 될 수 `type-id`합니다.  
  
 경우 유형의 `expression` 는 기본 클래스의 형식 `type-id`, 런타임 검사가 수행 되는 있는지 `expression` 실제로 형식의 완전 한 개체를 가리키는 `type-id`합니다. True 이면 결과 완전 한 개체의 형식에 대 한 포인터 `type-id`합니다. 예:  
  
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
  
 이러한 유형의 변환 라고는 여기에서 파생 클래스에 지정된 된 클래스에서 클래스 계층 구조 아래로 대 한 포인터를 이동 하기 때문에 "캐스트"입니다.  
  
 다중 상속의 경우 모호성에 대 한 가능성에 도입 되었습니다. 다음 그림에 표시 된 클래스 계층 구조를 고려해 야 합니다.  
  
 CLR 형식에 대 한 `dynamic_cast` 변환이 암시적으로 수행할 수 있으면 no-op 또는 MSIL `isinst` 동적 검사를 수행 하 고 반환 하는 명령 `nullptr` 경우 변환이 실패 합니다.  
  
 다음 샘플에서는 `dynamic_cast` 특정 형식의 인스턴스 클래스 인지 확인 하려면:  
  
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
  
 ![다중 상속을 보여 주는 계층 구조를 클래스](../cpp/media/vc39011.gif "vc39011")  
다중 상속을 보여 주는 클래스 계층 구조  
  
 형식의 개체에 대 한 포인터 `D` 으로 안전 하 게 캐스팅 될 수 `B` 또는 `C`합니다. 그러나 경우 `D` 를 가리키도록 캐스팅는 `A` 개체, 인스턴스 `A` 초래? 따라서 모호한 캐스팅 오류가 있습니다. 이 문제를 해결 하려면 두 개의 모호 하지 않은 캐스트를 수행할 수 있습니다. 예:  
  
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
  
 가상 기본 클래스를 사용 하는 경우 추가 모호성을 유발 될 수 있습니다. 다음 그림에 표시 된 클래스 계층 구조를 고려해 야 합니다.  
  
 ![가상 기본 클래스를 보여 주는 계층 구조를 클래스](../cpp/media/vc39012.gif "vc39012")  
가상 기본 클래스를 보여 주는 클래스 계층 구조  
  
 이 계층에서 `A` 는 가상 기본 클래스입니다. 클래스의 인스턴스가 `E` 및에 대 한 포인터는 `A` 하위 개체는 `dynamic_cast` 에 대 한 포인터로 `B` 모호성으로 인해 실패 합니다. 먼저 전체으로 다시 캐스팅 해야 `E` 개체를 차례 대로 계층을 반복에 올바른 연결 모호 하지 않은 방식 `B` 개체입니다.  
  
 다음 그림에 표시 된 클래스 계층 구조를 고려해 야 합니다.  
  
 ![중복 된 기본 클래스를 보여 주는 계층 구조를 클래스](../cpp/media/vc39013.gif "vc39013")  
중복 기본 클래스를 보여 주는 클래스 계층 구조  
  
 지정 된 형식의 개체 `E` 및에 대 한 포인터는 `D` 하위 개체에서 탐색 하는 `D` 맨 왼쪽에 하위 개체 `A` 하위 개체, 세 가지 변환이 수행 될 수 있습니다. 수행할 수 있습니다는 `dynamic_cast` 에서 변환은 `D` 에 대 한 포인터는 `E` 포인터를 다음으로 변환 (중 하나 `dynamic_cast` 또는 암시적으로 변환)에서 `E` 를 `B`, 및에서 암시적 변환이 마지막으로 `B` 를 `A`합니다. 예:  
  
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
  
 `dynamic_cast` 연산자 캐스트를 수행 하는 "교차 합니다."도 사용할 수 있습니다 같은 클래스 계층 구조를 사용 하 여에서 예를 들어 대 한 포인터를 캐스팅할 수는 `B` 하위 개체에는 `D` 으로 완전 한 개체 형식의 하위 개체 `E`합니다.  
  
 캐스트 크로스 고려, 실제로에 대 한 포인터에서 변환을 수행할 수는 `D` 맨 왼쪽에 대 한 포인터로 `A` 두 단계에서 하위 개체입니다. 크로스에서 캐스팅을 수행할 수 있습니다 `D` 를 `B`에서 암시적 변환이 다음 `B` 를 `A`합니다. 예:  
  
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
  
 Null 포인터 값으로 대상 형식의 null 포인터 값으로 변환 됩니다 `dynamic_cast`합니다.  
  
 사용 하는 경우 `dynamic_cast < type-id > ( expression )`경우 `expression` 형식으로 안전 하 게 변환할 수 없습니다 `type-id`, 런타임 검사 하면 실패로 캐스팅 합니다. 예:  
  
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
  
 포인터 형식으로 실패 한 캐스팅의 값이 null 포인터입니다. 실패 한 캐스팅 참조 형식을 throw 하는 [bad_cast 예외](../cpp/bad-cast-exception.md)합니다.   경우 `expression` 가리킨 하거나 유효한 개체를 참조 하지 않는 한 `__non_rtti_object` 예외가 throw 됩니다.  
  
 참조 [typeid](../cpp/typeid-operator.md) 에 대 한 설명은 `__non_rtti_object` 예외입니다.  
  
## <a name="example"></a>예  
 다음 샘플 기본 클래스 (구조체 A) 포인터 (C 구조체) 개체를 만듭니다.  이 더한 없는 팩트는 가상 함수, 런타임 다형성을 사용 하도록 설정 합니다.  
  
 또한 샘플 계층 구조에서 비가상 함수를 호출합니다.  
  
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
  
```Output  
in C  
test2 in B  
in GlobalTest  
Can't cast to C  
```  
  
## <a name="see-also"></a>참고 항목  
 [캐스팅 연산자](../cpp/casting-operators.md)   
 [키워드](../cpp/keywords-cpp.md)