---
title: "컴파일러 오류 C2440 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0789875fee672856dbc0eff429d2363a43963940
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2440"></a>컴파일러 오류 C2440
'conversion': 'type1'에서 'type2'로 변환할 수 없습니다  
  
컴파일러에서 캐스팅할 수 없습니다 `type1` 를 `type2`합니다.  
  
## <a name="example"></a>예제  
C2440 비 const를 초기화 하려고 하면 발생할 수 있습니다 `char*` (또는 `wchar_t*`) c + + 코드에 있는 문자열 리터럴이 사용 하 여 때 컴파일러 규칙 옵션 [/zc: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) 설정 됩니다. C에서는 문자열 리터럴 형식이 배열 `char`, 표시 되지만 c + +, 배열을 `const char`합니다. 이 샘플에서는 C2440 오류가 생성 됩니다.  
  
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
  
## <a name="example"></a>예제  
 C2440은 void * 멤버 포인터 변환 하려는 경우에 발생할 수 있습니다. 다음 샘플에서는 C2440 오류가 생성 됩니다.  
  
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
  
## <a name="example"></a>예제  
 C2440 앞 으로만 선언 되었지만 정의 되어 있지 하는 형식에서 캐스팅 하 려 하는 경우에 발생할 수 있습니다. 이 샘플에서는 C2440 오류가 생성 됩니다.  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## <a name="example"></a>예제  
 15, 16 다음 샘플의 줄에 있는 C2440 오류도 한정 되는 `Incompatible calling conventions for UDT return value` 메시지입니다. A *UDT* 클래스, 구조체 또는 공용 구조체와 같은 사용자 정의 형식입니다. 이러한 종류의 비 호환성 오류는 UDT의 호출 규칙은 반환 형식의 실제 udt 및 함수 포인터와 연관 된 호출 규칙으로 충돌 하는 정방향 선언에 지정 된 경우에 발생 합니다.  
  
 예제에서는 먼저 없는 구조체 및 구조체; 반환 하는 함수에 대 한 정방향 선언 컴파일러는 구조체는 c + + 호출 규칙을 사용 하는 가정 합니다. 다음은 기본적으로 C를 사용 하는 구조체 정의 호출 규칙. 모르기 때문에 컴파일러는 구조체의 호출 규칙 전체 구조체 구조체의 반환 형식에 대 한 호출 규칙을 읽는 완료 될 때까지 `get_c2` 또한 c + +로 간주 됩니다.  
  
 구조체는 구조체를 반환 하는 다른 함수 선언 뒤 하지만 시점에서 컴파일러 것을 알고 구조체의 호출 규칙은 c + +입니다. 마찬가지로, 컴파일러는 구조체는 c + + 호출 규칙을 사용 하는지 알 수 있도록 구조체를 반환 하는 함수 포인터를 구조체 정의 뒤 정의 됩니다.  
  
 C2440 호환 되지 않는 호출 규칙으로 인해 발생 하는 오류를 해결 하려면 UDT 정의 다음에 UDT를 반환 하는 함수를 선언 합니다.  
  
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
  
## <a name="example"></a>예제  
 C2440 내부 포인터에 0을 할당 하는 경우에 발생할 수 있습니다.  
  
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
  
## <a name="example"></a>예제  
 사용자 정의 변환 사용이 잘못 C2440도 발생할 수 있습니다. 예를 들어 때 변환 연산자 정의 된 `explicit`, 컴파일러는 암시적 변환에 사용할 수 없습니다. 사용자 정의 변환에 대 한 자세한 내용은 참조 [사용자 정의 변환 (C + + /cli CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). 이 샘플에서는 C2440 오류가 생성 됩니다.  
  
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
  
## <a name="example"></a>예제  
 C2440는 <xref:System.Array>.</xref:System.Array> 형식이 Visual c + + 배열의 인스턴스를 만들려고 할 경우에 발생할 수 있습니다.  자세한 내용은 참조 [배열](../../windows/arrays-cpp-component-extensions.md)합니다.  다음 샘플에서는 C2440 오류가 생성 됩니다.  
  
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
  
## <a name="example"></a>예제  
 C2440 특성 기능의 변경으로 인해 발생할 수도 있습니다.  다음 샘플에서는 C2440 합니다.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## <a name="example"></a>예제  
 Visual c + + 컴파일러는 더 이상 허용는 [const_cast 연산자](../../cpp/const-cast-operator.md) 아래로 캐스팅할 때 소스 코드를 사용 하 **/clr** 프로그래밍 컴파일됩니다.  
  
 이 c2440 오류를 해결 하려면 올바른 캐스트 연산자를 사용 합니다. 자세한 내용은 참조 [캐스팅 연산자](../../cpp/casting-operators.md)합니다.  
  
 이 샘플에서는 C2440 오류가 생성 됩니다.  
  
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
  
## <a name="example"></a>예제  
C2440 Visual Studio 2015 업데이트 3에서 컴파일러 규칙 변경으로 인해 발생할 수 있습니다. 이전에 컴파일러 잘못 처리 특정 개별 식 같은 형식으로 일치 하는 서식 파일을 식별할 때는 `static_cast` 작업 합니다. 이전에 의존 하는 이제 컴파일러는 형식이 올바르게 구분 하 고 코드 `static_cast` 동작은 중단 합니다. 이 문제를 해결 하려면 변경 템플릿 매개 변수 형식과 일치 하거나 사용 하려면 템플릿 인수는 `reinterpret_cast` 또는 C 스타일 캐스트 합니다.
  
이 샘플에서는 C2440 오류가 생성 됩니다.  
  
```cpp  
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3 
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.

```

## <a name="example"></a>예제  
### <a name="copy-list-initialization"></a>Copy-list-initialization

2017 및 이후 버전의 visual Studio에는 올바르게 Visual Studio 2015에서 하지 되었으나 및 충돌 될 수는 이니셜라이저 목록을 사용 하 여 개체 만들기와 관련 된 컴파일러 오류가 발생 하거나 런타임 동작을 정의 되지 않았습니다. C + + 17 복사 목록-초기화, 컴파일러는 오버 로드 확인에 대 한 명시적 생성자를 고려해 야 하는 데 필요 하지만 오버 로드 하는 실제로 선택 하는 경우 오류가 발생 합니다.

다음 예제에서는 Visual Studio 2017 있지만 Visual Studio 2015에 컴파일합니다.

```cpp  
// C2440j.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot 
                         // convert from 'int' to 'const A &'
}
```  
  
오류를 수정하려면 직접 초기화를 사용합니다.  
  
```cpp  
// C2440k.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    const A& a2{ 1 };
}  
```  

## <a name="example"></a>예제
### <a name="cv-qualifiers-in-class-construction"></a>클래스 생성의 cv 한정자

Visual Studio 2015에서는 컴파일러가 생성자 호출을 통해 클래스 개체를 생성할 때 cv 한정자를 잘못 무시하는 경우가 있습니다. 이로 인해 잠재적으로 크래시 또는 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제에서는 Visual Studio 2015에서 컴파일하지만 이상 Visual Studio 2017에서 컴파일러 오류를 발생 시킵니다.

```cpp
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

오류를 수정하려면 operator int()를 생성자로 선언합니다.

