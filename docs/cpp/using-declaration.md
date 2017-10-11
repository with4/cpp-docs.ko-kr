---
title: "선언을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- using declaration
- declaring namespaces, unqualified names in namespaces
- declarations [C++], using-declaration
- namespaces [C++], unqualified names in
- using keyword [C++]
- declarations [C++], namespaces
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c55abac758c636bce596b0613e0ad5671fc9c430
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="using-declaration"></a>선언 사용
선언을 사용 하는 이름을는 선언적 영역에 새로 추가 선언을 사용 하 여 나타납니다.  
  
## <a name="syntax"></a>구문  
  
```  
using [typename] nested-name-specifier unqualified-id ;  
using declarator-list ;  
```  
  
### <a name="parameters"></a>매개 변수
  
*중첩 된 이름-지정자*  
    네임 스페이스, 클래스 또는 열거형 이름 및 범위 확인 연산자 (:)의 범위 확인 연산자에 의해 종료 시퀀스입니다. 이름을 전역 네임 스페이스에서 제공 하는 단일 범위 결정 연산자를 사용할 수 있습니다. 키워드 `typename` 는 선택 사항이 며 기본 클래스에서 클래스 템플릿을 도입할 때 종속 이름을 확인 하기 위해 사용할 수 있습니다.  
  
*정규화 되지 않은 id*  
    정규화 되지 않은 id-있는 식을 식별자, 오버 로드 된 운영자 이름, 사용자 정의 리터럴 연산자 또는 변환 함수 이름, 클래스 소멸자 이름 또는 템플릿 이름 및 인수 목록을 수 있습니다.  
  
*선언 자 목록*  
    쉼표로 구분 된 목록 [`typename`] *중첩-이름-지정자* *정규화 되지 않은 id* 다음 선택적 줄임표로 선언 자입니다.
    
## <a name="remarks"></a>설명  
엔터티에 대 한 동의어로 정규화 되지 않은 이름을 소개 선언을 사용 하 여 다른 곳에서 선언 합니다. 나타나는 선언 영역에서 명시적 자격 증명 없이 사용할 특정 네임 스페이스에서 단일 이름 수 있습니다. 이 달리는 [지시문을 사용 하 여](../cpp/namespaces-cpp.md#using_directives)을 허용 하는 *모든* 자격 증명 없이 사용 하는 네임 스페이스의 이름입니다. `using` 키워드에도 사용 됩니다 [형식의 별칭](../cpp/aliases-and-typedefs-cpp.md)합니다.  
  
## <a name="example"></a>예제  
 선언을 사용 하 여 클래스 정의에 사용할 수 있습니다.  
  
```cpp  
// using_declaration1.cpp  
#include <stdio.h>  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class D : B {  
public:  
   using B::f;    // B::f(char) is now visible as D::f(char)  
   using B::g;    // B::g(char) is now visible as D::g(char)  
   void f(int) {  
      printf_s("In D::f()\n");  
      f('c');     // Invokes B::f(char) instead of recursing  
   }  
  
   void g(int) {  
      printf_s("In D::g()\n");  
      g('c');     // Invokes B::g(char) instead of recursing  
   }  
};  
  
int main() {  
   D myD;  
   myD.f(1);  
   myD.g('a');  
}  
```  
  
```Output  
In D::f()  
In B::f()  
In B::g()  
```  
  
## <a name="example"></a>예제  
사용 하는 멤버를 선언 하는 데 사용 하는 경우 선언은 기본 클래스의 멤버를 참조 해야 합니다.  
  
```cpp  
// using_declaration2.cpp  
#include <stdio.h>  
  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class C {  
public:  
   int g();  
};  
  
class D2 : public B {  
public:  
   using B::f;   // ok: B is a base of D2  
   // using C::g;   // error: C isn't a base of D2  
};  
  
int main() {  
   D2 MyD2;  
   MyD2.f('a');  
}  
```  
  
```Output  
In B::f()  
```  
  
## <a name="example"></a>예제  
사용 하 여 선언 된 멤버 선언 명시적 정규화를 사용 하 여 참조할 수 있습니다. `::` 전역 네임 스페이스 접두사를 참조 합니다.  
  
```cpp  
// using_declaration3.cpp  
#include <stdio.h>  
  
void f() {  
   printf_s("In f\n");  
}  
  
namespace A {  
   void g() {  
      printf_s("In A::g\n");  
   }  
}  
  
namespace X {  
   using ::f;   // global f is also visible as X::f  
   using A::g;   // A's g is now visible as X::g 
}  
  
void h() {  
   printf_s("In h\n");  
   X::f();   // calls ::f  
   X::g();   // calls A::g  
}  
  
int main() {  
   h();  
}  
```  
  
```Output  
In h  
In f  
In A::g  
```  
  
## <a name="example"></a>예제  
사용 하는 경우 선언한, 사용 하는 지점에서 사용할 수 있는 정의에 선언 하 여 만든 동의어에서 참조 선언 합니다. 에서는 사용 된 네임 스페이스에 추가 된 정의 선언 값은 유효한 동의어가 아닙니다.  
  
에 정의 된 이름을 `using` 선언은 원래 이름에 대 한 별칭입니다. 형식, 링크 또는 다른 특성이 원래 선언에는 영향을 주지 않습니다.  
  
```cpp  
// post_declaration_namespace_additions.cpp  
// compile with: /c  
namespace A {  
   void f(int) {}  
}  
  
using A::f;   // f is a synonym for A::f(int) only  
  
namespace A {  
   void f(char) {}  
}  
  
void f() {  
   f('a');   // refers to A::f(int), even though A::f(char) exists  
}  
  
void b() {  
   using A::f;   // refers to A::f(int) AND A::f(char)  
   f('a');   // calls A::f(char);  
}  
```  
  
## <a name="example"></a>예제  
지역 선언에는 네임 스페이스의 함수에 대해 선언 대 한 사용 하는 선언적 영역에서 단일 이름 제공, 해야 모두 동일한 엔터티를 참조 또는 해야 모든 함수를 참조 합니다.  
  
```cpp  
// functions_in_namespaces1.cpp  
// C2874 expected  
namespace B {  
    int i;  
    void f(int);  
    void f(double);  
}  
  
void g() {  
    int i;  
    using B::i;   // error: i declared twice  
    void f(char);  
    using B::f;   // ok: each f is a function  
}  
```  
  
 위의 예에는 `using B::i` 문을 사용 하면 두 번째 `int i` 에서 선언할 수는 `g()` 함수입니다. `using B::f` 문을와 충돌 하지 않는 `f(char)` 에 의해 정의 된 함수 이름 때문에 작동 `B::f` 매개 변수 형식이 다릅니다.  
  
## <a name="example"></a>예제  
 로컬 함수 선언 선언을 사용 하 여에서 도입 된 함수와 같은 이름과 형식을 가질 수 없습니다. 예:  
  
```cpp  
// functions_in_namespaces2.cpp  
// C2668 expected  
namespace B {  
    void f(int);  
    void f(double);  
}  
  
namespace C {  
    void f(int);  
    void f(double);  
    void f(char);  
}  
  
void h() {  
    using B::f;          // introduces B::f(int) and B::f(double)  
    using C::f;          // C::f(int), C::f(double), and C::f(char)  
    f('h');              // calls C::f(char)  
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?  
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)  
}  
```  
  
## <a name="example"></a>예제  
 상속을 기준으로 제공 하는 경우 using 선언 이름을 기본 클래스에서 파생된 클래스 범위, 기본 클래스에 동일한 이름 및 인수 형식 가진 파생된 클래스 재정의 가상 멤버 함수에서 멤버 함수에 있습니다.  
  
```cpp  
// using_declaration_inheritance1.cpp  
#include <stdio.h>  
struct B {  
   virtual void f(int) {  
      printf_s("In B::f(int)\n");  
   }  
  
   virtual void f(char) {  
      printf_s("In B::f(char)\n");  
   }  
  
   void g(int) {  
      printf_s("In B::g\n");  
   }  
  
   void h(int);  
};  
  
struct D : B {  
   using B::f;  
   void f(int) {   // ok: D::f(int) overrides B::f(int)  
      printf_s("In D::f(int)\n");  
   }  
  
   using B::g;  
   void g(char) {   // ok: there is no B::g(char)  
      printf_s("In D::g(char)\n");  
   }  
  
   using B::h;  
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)  
};  
  
void f(D* pd) {  
   pd->f(1);     // calls D::f(int)  
   pd->f('a');   // calls B::f(char)  
   pd->g(1);     // calls B::g(int)  
   pd->g('a');   // calls D::g(char)  
}  
  
int main() {  
   D * myd = new D();  
   f(myd);  
}  
```  
  
```Output  
In D::f(int)  
In B::f(char)  
In B::g  
In D::g(char)  
```  
  
## <a name="example"></a>예제  
이름 사용 하 여 언급 된 함수의 모든 인스턴스의 선언 액세스할 수 있어야 합니다. 특히, 파생된 클래스를 사용 하 여 사용 하는 경우에 기본 클래스 멤버 이름은 멤버 액세스 하는 선언에 액세스할 수 있어야 합니다. 이름이 경우 오버 로드 된 멤버 함수의 명명 하는 모든 함수에 액세스할 수 있어야 합니다.  
  
멤버의 액세스 가능성에 자세한 내용은 참조 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)합니다.  
  
```cpp  
// using_declaration_inheritance2.cpp  
// C2876 expected  
class A {  
private:  
   void f(char);  
public:  
   void f(int);  
protected:  
   void g();  
};  
  
class B : public A {  
   using A::f;   // C2876: A::f(char) is inaccessible  
public:  
   using A::g;   // B::g is a public synonym for A::g  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [네임스페이스](../cpp/namespaces-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)
