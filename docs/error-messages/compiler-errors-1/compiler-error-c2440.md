---
title: "컴파일러 오류 C2440 | Microsoft Docs"
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
  - "C2440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2440"
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion' : 'type1'에서 'type2'\(으\)로 변환할 수 없습니다.  
  
 컴파일러가 '`type1`'에서 '`type2`'로 캐스팅할 수 없습니다.  
  
## 예제  
 C2440은 컴파일러 성능 옵션 [\/Zc:strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md)가 설정되었을 때 C\+\+ 코드의 문자열 리터럴을 사용하여 비상수 `char*`\(또는 `wchar_t*`\)를 초기화하려고 시도하는 경우 발생할 수 있습니다.  C에서 문자열 리터럴의 형식은 `char`의 배열이지만 C\+\+에서는 `const` `char`의 배열입니다.  이 샘플은 C2440을 생성합니다.  
  
```cpp  
// C2440s.cpp  
// Build: cl /Zc:strictStrings /W3 C2440s.cpp  
// When built, the compiler emits:  
// error C2440: 'initializing' : cannot convert from 'const char [5]'   
// to 'char *'  
//        Conversion from string literal loses const qualifier (see  
// /Zc:strictStrings)  
  
int main() {  
   char* s1 = "test"; // C2440  
   const char* s2 = "tests"; // OK  
}  
```  
  
## 예제  
 C2440은 멤버에 대한 포인터를 void\*로 변환하려고 할 때도 발생할 수 있습니다.  다음 샘플에서는 C2440이 발생하는 경우를 보여줍니다.  
  
```cpp  
// C2440.cpp  
class B {  
public:  
   void  f(){;}  
  
   typedef void (B::*pf)();  
  
   void f2(pf pf) {  
       (this->*pf)();  
       void* pp = (void*)pf;   // C2440  
   }  
  
   void f3() {  
      f2(f);  
   }  
};  
```  
  
## 예제  
 C2440은 전방 선언되기만 하고 정의되지는 않은 형식에서 캐스팅을 시도하는 경우에도 발생할 수 있습니다.  이 샘플은 C2440을 생성합니다.  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## 예제  
 다음 샘플의 15줄과 16줄에 있는 C2440 오류는 `Incompatible calling conventions for UDT return value` 메시지로 한정됩니다. UDT는 클래스, 구조체 또는 공용 구조체와 같은 사용자 정의 형식입니다. 이러한 종류의 비호환 오류는 전방 선언의 반환 형식에 지정한 UDT의 호출 규칙이 UDT의 실제 호출 규칙과 충돌하는 경우 및 함수 포인터와 연관된 경우에 발생합니다.  
  
 예제에서는 struct를 반환하는 함수에 대해 그리고 struct에 대해 전방 선언이 사용되며, 컴파일러는 struct가 C\+\+ 호출 규칙을 사용한다고 가정합니다.  다음은 기본적으로 C 호출 규칙을 사용하는 struct 정의입니다.  컴파일러는 전체 구조체를 읽을 때까지 구조체의 호출 규칙을 알지 못하므로 `get_c2`의 반환 형식에서 구조체에 대한 호출 규칙은 C\+\+로 간주됩니다.  
  
 struct 다음에는 struct를 반환하는 다른 함수 선언이 옵니다. 이때 컴파일러는 struct의 호출 규칙이 C\+\+임을 알고 있습니다.  마찬가지로 구조체를 반환하는 함수 포인터는 컴파일러가 구조체에서 C\+\+ 호출 규칙이 사용되는지 알 수 있도록 구조체 정의 다음에 정의됩니다.  
  
 호환되지 않는 호출 규칙으로 인해 발생하는 C2440을 해결하려면 UDT 정의 다음에 UDT를 반환하는 함수를 선언합니다.  
  
```cpp  
// C2440b.cpp  
struct MyStruct;  
  
MyStruct get_c1();  
  
struct MyStruct {  
   int i;  
   static MyStruct get_C2();  
};  
  
MyStruct get_C3();  
  
typedef MyStruct (*FC)();  
  
FC fc1 = &get_c1;   // C2440, line 15  
FC fc2 = &MyStruct::get_C2;   // C2440, line 16  
FC fc3 = &get_C3;  
  
class CMyClass {  
public:  
   explicit CMyClass( int iBar)  
      throw()   {  
   }  
  
   static CMyClass get_c2();  
};  
  
int main() {  
   CMyClass myclass = 2;   // C2440  
   // try one of the following  
   // CMyClass myclass{2};  
   // CMyClass myclass(2);  
  
   int *i;  
   float j;  
   j = (float)i;   // C2440, cannot cast from pointer to int to float  
}  
```  
  
## 예제  
 C2440은 내부 포인터에 0을 할당하는 경우에도 발생할 수 있습니다.  
  
```cpp  
// C2440c.cpp  
// compile with: /clr  
int main() {  
   array<int>^ arr = gcnew array<int>(100);  
   interior_ptr<int> ipi = &arr[0];  
   ipi = 0;   // C2440  
   ipi = nullptr;   // OK  
}  
```  
  
## 예제  
 C2440은 사용자 정의 변환을 잘못 사용할 때도 발생할 수 있습니다.  사용자 정의 변환에 대한 자세한 내용은 [사용자 정의 변환](../../dotnet/user-defined-conversions-cpp-cli.md)을 참조하십시오.  이 샘플은 C2440을 생성합니다.  
  
```cpp  
// C2440d.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   int i;  
   i = d;   // C2440  
   // Uncomment the following line to resolve.  
   // i = static_cast<int>(d);  
}  
```  
  
## 예제  
 C2440은 해당 형식이 <xref:System.Array>인 Visual C\+\+ 배열의 인스턴스를 만들려는 경우에도 발생할 수 있습니다.  자세한 내용은 [Arrays](../../windows/arrays-cpp-component-extensions.md)을 참조하십시오.  다음 샘플에서는 C2440이 발생하는 경우를 보여줍니다.  
  
```cpp  
// C2440e.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440  
   // try the following line instead  
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));  
}  
```  
  
## 예제  
 C2440은 특성 기능이 변경된 경우에도 발생할 수 있습니다.  다음 샘플에서는 C2440 오류가 발생하는 경우를 보여 줍니다.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## 예제  
 Visual C\+\+ 컴파일러에서는 **\/clr** 프로그래밍을 사용하는 소스 코드를 컴파일할 때 더 이상 [const\_cast 연산자](../../cpp/const-cast-operator.md)의 다운 캐스트가 허용되지 않습니다.  
  
 이 C2440을 해결하려면 올바른 캐스트 연산자를 사용합니다.  자세한 내용은 [캐스팅 연산자](../../cpp/casting-operators.md)을 참조하십시오.  
  
 이 샘플은 C2440을 생성합니다.  
  
```cpp  
// c2440g.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
int main() {  
   Derived ^d = gcnew Derived;  
   Base ^b = d;  
   d = const_cast<Derived^>(b);   // C2440  
   d = dynamic_cast<Derived^>(b);   // OK  
}  
```  
  
## 예제  
 C2440은 **\/clr:oldSyntax**를 사용할 때도 발생할 수 있습니다.  
  
```cpp  
// c2440h.cpp  
// compile with: /clr:oldSyntax  
__gc class Base {};  
__gc class Derived : public Base {};  
int main() {  
   Derived *d = new Derived;  
   Base *b = d;  
   d = const_cast<Derived*>(b);   // C2440  
   d = dynamic_cast<Derived*>(b);   // OK  
}  
```