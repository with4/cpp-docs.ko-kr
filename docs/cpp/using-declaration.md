---
title: "선언 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "선언 사용"
  - "네임스페이스 선언, 네임스페이스에서 정규화되지 않은 이름"
  - "선언[C++], using-declaration"
  - "네임스페이스[C++], 정규화되지 않은 이름"
  - "using 키워드[C++]"
  - "선언[C++], 네임스페이스"
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 선언 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`using` 선언이 `using` 선언이 나타나는 선언 영역에 이름을 도입합니다.  
  
## 구문  
  
```  
  
      using [typename][::] nested-name-specifier unqualified-id  
using :: unqualified-id  
```  
  
## 설명  
 이름은 다른 곳에서 선언된 엔터티에 대한 동의어가 됩니다.  [명시적 정규화](../misc/explicit-qualification.md) 없이 특정 네임스페이스에서 *개별* 이름을 사용할 수 있습니다.  이것은 `using` 명령어와 대조되는데, 네임 스페이스에 있는 *all* 이름이 자격없이 사용될 수 있도록 합니다.  자세한 내용은 [using 지시문](../misc/using-directive-cpp.md)을 참조하십시오.  이 키워드는 [형식 별칭](../cpp/aliases-and-typedefs-cpp.md)으로 사용됩니다.  
  
## 예제  
 선언 사용은 클래스 정의에서 사용할 수 있습니다.  
  
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
   using B::f;  
   using B::g;  
   void f(int) {  
      printf_s("In D::f()\n");  
      f('c');  
   }  
  
   void g(int) {  
      printf_s("In D::g()\n");  
      g('c');  
   }  
};  
  
int main() {  
   D myD;  
   myD.f(1);  
   myD.g('a');  
}  
```  
  
  **D::f\(\)에서**  
**B::f\(\)에서**  
**B::g\(\)에서**   
## 예제  
 멤버를 선언하는데 사용하는 경우 선언을 사용하여 기본 클래스 멤버를 참조해야 합니다.  
  
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
  
  **B::f\(\)에서**   
## 예제  
 선언을 통해 선언된 멤버는 명시적 한정자를 사용하여 참조할 수 있습니다.  `::` 접두사는 글로벌 네임스페이스를 나타냅니다.  
  
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
   using ::f;   // global f  
   using A::g;   // A's g  
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
  
  **h에서**  
**f에서**  
**A::g에서**   
## 예제  
 사용선언을 한 경우, 선언에 의해 만들어진 동의어는 사용선언 시점에 유효한지에 대한 정의만을 나타냅니다.  using 선언 뒤의 네임스페이스에 추가된 정의가 올바른 동의어가 아닙니다.  
  
 선언을 사용하여 정의된 이름은 원래 이름의 별칭입니다.  원래 선언의 다른 특성이나 형식, 링크에는 영향을 주지 않습니다.  
  
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
  
## 예제  
 네임 스페이스의 함수로, 로컬 선언 집합과 단일 이름에 대한 선언의 사용이 선언 영역에 주어질 경우, 모두 동일한 엔티티를 참조하거나, 또는 모든 함수를 참조해야 합니다.  
  
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
  
 위 예제에서는 `using B::i` 문으로 인해 두 번째 `int i`가 `g()` 함수에서 선언됩니다.  `B::f`에 의하여 도입된 기능 명칭은 다른 파라미터 유형을 가지므로, `using B::f` 문장은 `f(char)` 기능과 경쟁하지 않습니다.  
  
## 예제  
 지역 함수 선언은 선언을 사용하여 도입된 함수와 같은 이름과 형식을 가질 수 없습니다.  예를 들면 다음과 같습니다.  
  
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
  
## 예제  
 상속에 대하여, 기본 클래스의 이름을 파생 클래스 범위에 소개하는 선언문의 사용 시, 파생 클래스의 멤버 함수는 기본 클래스의 동일 이름과 인수 형식의 가상 멤버 함수를 무시합니다.  
  
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
   pd->f(1);   // calls D::f(int)  
   pd->f('a');   // calls B::f(char)  
   pd->g(1);   // calls B::g(int)  
   pd->g('a');   // calls D::g(char)  
}  
  
int main() {  
   D * myd = new D();  
   f(myd);  
}  
```  
  
  **D::f\(int\)에서**  
**B::f\(char\)에서**  
**B::g에서**  
**D::g\(char\)에서**   
## 예제  
 using 선언에서 언급된 이름의 모든 인스턴스에 액세스할 수 있어야 합니다.  특히 파생된 클래스가 using 선언을 사용하여 기본 클래스의 멤버에 액세스하는 경우 멤버 이름을 액세스할 수 있어야 합니다.  오버로드된 멤버 함수의 이름인 경우 명명된 모든 함수에 액세스할 수 있어야 합니다.  
  
 멤버의 액세스 가능성에 대한 자세한 내용은 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)를 참조하십시오.  
  
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
  
## 참고 항목  
 [네임스페이스](../cpp/namespaces-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)