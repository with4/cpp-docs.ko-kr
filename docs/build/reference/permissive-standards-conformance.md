---
title: "이상의 사용 권한을 허용-(표준 준수) | Microsoft Docs"
ms.date: 11/11/2016
ms.technology: cpp-tools
ms.topic: article
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
dev_langs: C++
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90ff6d2be6174f32d7d93252ebd8b693b422076d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="permissive--standards-conformance"></a>관대 한 /-(표준 규칙)

컴파일러에 표준 규격 모드를 지정 합니다. 이 옵션을 사용 하 여 확인 하 고 코드에서 더 정확 하 고 이식성을 규칙과 관련 된 문제를 해결할 수 있도록 합니다.

## <a name="syntax"></a>구문

> **관대 한 /-**

## <a name="remarks"></a>설명

사용할 수는 **관대 한 /-** 컴파일러 옵션을 컴파일러 표준 준수 동작을 지정 합니다. 이 옵션 관대 한 동작을 사용 하지 않도록 설정 하 고 설정 하는 [/Zc](../../build/reference/zc-conformance.md) 엄격한 규칙에 대 한 컴파일러 옵션입니다. IDE에서이 옵션을 IntelliSense 엔진 밑줄 맞지 않는 코드 사용 하면 됩니다. 

기본적으로는 **관대 한 /-** 옵션은 Visual Studio 2017 버전 15.5 이상 버전에서 만든 새 프로젝트에서 설정 합니다. 이전 버전에서는 기본적으로 설정 되지 않았습니다. 옵션이 설정 된, 컴파일러 진단 오류를 생성 또는 사용자 코드에서 발견 되 면 사용할 수 없는 언어 구문이 도입 되면서 때 경고를 하는 경우 몇 가지 일반적인 버그를 포함 하 여 이전에-C + + 11 코드입니다.

**관대 한 /-** 옵션은 소프트웨어 개발 키트 (SDK) 또는 키트 WDK (Windows 드라이버)를 시작 하는 Windows가 작성자 sdk (10.0.16299.0)와 같은 최신 Windows 키트에서 헤더 파일의 거의 모든 호환 됩니다. 이전 버전의 SDK에서 컴파일하는 데 실패할 수 있습니다 **관대 한 /-** 다양 한 원본 표준을 따르도록 코드에 대 한 합니다. 컴파일러와 다른 릴리스 타임 라인의 Sdk 배송 따라서 남은 몇 가지 문제가 있습니다. 특정 헤더 파일 문제에 대 한 참조 [Windows 헤더 문제](#windows-header-issues) 아래 합니다.

**관대 한 /-** 설정 옵션의 [/zc: strictstrings](../../build/reference/zc-conformance.md) 및 [/zc: rvaluecast](../../build/reference/zc-conformance.md) 옵션 표준에 맞는 동작을 합니다. 기본적으로 맞지 않는 동작 합니다. 특정 전달할 수 있습니다 **/Zc** 후 옵션 **관대 한 /-** 이 동작을 재정의 하려면 명령줄에 있습니다.

버전의 Visual Studio 2017 15.3, 버전에서에서 시작 하는 컴파일러는 **관대 한 /-** 집합 옵션는 **/Zc:ternary** 옵션입니다. 컴파일러는 2 단계 이름 조회에 대 한 요구 사항 중에 구현합니다. 경우는 **관대 한 /-** 옵션이 설정 되어, 컴파일러 서식 파일에 사용 되는 종속 및 종속 되지 않은 이름 식별 함수 및 클래스 템플릿 정의 구문 분석 합니다. 이 릴리스에서 이름 종속성 분석만 수행 됩니다.

환경 관련 확장 및 구현에 따라 표준을 해제 하는 언어 영역 영향을 받지 않는 **관대 한 /-**합니다. 예를 들어 Microsoft 전용 `__declspec`, 호출 규칙 및 구조적된 예외 처리 키워드 및 관련 컴파일러 pragma 지시문 또는 특성에 컴파일러에서 플래그가 지정 되지 않은 **관대 한 /-** 모드입니다.

**관대 한 /-** 옵션 사용 하 여 규칙에 따라 지원 현재 컴파일러 버전에서 어떤 언어 구문을 맞지 않는 확인 합니다. 옵션 코드는 c + + 표준의 특정 버전에 맞는 경우를 확인 하지 않습니다. 를 최신 초안 표준에 대 한 모든 구현 된 컴파일러 지원 하도록 설정 하려면 사용 된 [/std:latest](../../build/reference/std-specify-language-standard-version.md) 옵션입니다. 현재 구현 된 C + + 17 표준에 컴파일러 지원 제한 하려면는 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md) 옵션입니다. C + + 14 표준와 비슷하도록 컴파일러 지원 제한 하려면는 [/std:c + + 14](../../build/reference/std-specify-language-standard-version.md) 옵션을 기본값으로 설정 되어 만들어져야 합니다.

모든 C + + 11, C + + 14, 또는 C + + 17 표준 준수 하지 Visual Studio 2017에 Visual c + + 컴파일러에서 지원 되는 코드입니다. **관대 한 /-** 옵션 2 단계 이름 조회의 일부 측면을 관련 항목, 임시에 대 한 비 const 참조를 바인딩, 직접 초기화로 복사 초기화를 처리 하는 방법에 여러 사용자 정의 변환은 허용 문제를 검색할 수 없습니다 초기화 또는 논리 연산자 및 기타 지원 되지 않는 규칙에 따라 영역에 대 한 대체 토큰입니다. Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="how-to-fix-your-code"></a>코드를 수정 하는 방법

다음은 맞지 않는 사용 하는 경우로 검색 되는 코드의 몇 가지 예제 **관대 한 /-**, 문제를 해결 하는 제안 된 방법을 함께 합니다.

#### <a name="use-default-as-an-identifier-in-native-code"></a>기본값을 사용 하 여 네이티브 코드에서 식별자로

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>종속 자료의 조회 멤버

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>멤버 선언에 정규화 된 이름 사용

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>멤버 이니셜라이저에 여러 공용 구조체 멤버를 초기화 합니다.

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>숨겨진된 friend 이름 조회 규칙

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(S); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>배열 범위 내에 범위가 지정 된 열거형을 사용 하 여

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>네이티브 코드에서 각각에 대해 사용

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>ATL 특성 사용

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be 
// used to automatically obtain a *.idl file for the interfaces with 
// annotation. Second, add a midl step to your build system to make 
// sure that the C++ interface definitions are outputted. 
// Last, adjust your existing code to use ATL directly as shown in 
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>모호한 조건부 연산자 인수

컴파일러 버전의 Visual Studio 2017 버전 15.3 하기 전에 컴파일러에서는 조건 연산자 (또는 삼항 연산자)에 대 한 인수를 수락 `?:` 하는 것으로 간주 모호한 표준에 따라 합니다. **관대 한 /-** 모드에서는 이제 컴파일러가 이전 버전에서 진단 없이 컴파일 하는 경우 하나 이상의 진단 합니다.

이러한 변경으로 인해 발생할 수 있는 공용 오류입니다.

- 오류 C2593: 'operator'? 모호합니다.

- C2679 오류: 이진 '?': 형식의 오른쪽 피연산자로 'B'를 사용 하는 연산자가 없습니다 발견 (또는 허용 가능한 변환이 없습니다)

- c 2678 오류: 이진 '?': 'A' 형식의 왼쪽 피연산자를 사용 하는 연산자 발견 (또는 허용 가능한 변환이 없는)

- 오류 C2446: ':': 'B'에서 'A'로 변환 없음

이 문제를 일으킬 수 있는 일반적인 코드 패턴은 일부 클래스 C 화 형식에 다른 형식 T에서에서 비 명시적 생성자와 비 명시적 변환 연산자를 모두 제공 하는 경우 이 경우 세 번째 서비스로의 형식으로 변환 하는 두 번째 인수의 두 번째의 형식으로 변환 하는 세 번째 인수는 유효한 변환을 표준에 따라 모호한 있습니다.

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

예외가 중요이 공통 패턴을 T null로 끝나는 문자열 형식 중 하나를 나타내는 경우 (예를 들어 `const char *`, `const char16_t *`등) 및 실제 인수를 `?:` 문자열인 해당 유형의 리터럴. C + + 17에는 C + + 14에서 의미 체계가 변경 되었습니다. 예제 2의에서 코드에서 수락 되는 결과적으로, **/std:c + + 14** 와에서 거부 된 **/std:c + + 17** 때 **/Zc:ternary** 또는 **/permissive-**사용 됩니다.

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s; 
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

조건부 연산자와 형식의 인수 하나에 오류가 표시 될 수 있는 경우에도 `void`합니다. 이 경우 ASSERT 모양의 매크로에서 일반적으로 수 있습니다.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

조건부 연산자 결과 형식에서 변경 될 수 있습니다는 여기서 템플릿 메타 프로그래밍에 오류가 나타날 **/Zc:ternary** 및 **관대 한 /-**합니다. 사용 하는 것이 문제를 해결 하는 한 가지 방법은 [std::remove_reference](../../standard-library/remove-reference-class.md) 결과 형식에 있습니다.

```cpp
// Example 4: different result types 
extern bool cond;
extern int count;
char  a = 'A'; 
const char  b = 'B'; 
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary 
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary 
```

#### <a name="two-phase-name-look-up-partial"></a>2 단계 이름 조회 (부분)

경우는 **관대 한 /-** Visual Studio 2017 15.3 버전에서에서 옵션을 설정, 컴파일러 식별 이름 2 단계에 대 한 필요에 따라 서식 파일에서 사용 되는 종속 및 종속 되지 않은 이름의 함수 및 클래스 템플릿 정의 구문 분석 조회 합니다. 이 릴리스에서 이름 종속성 분석만 수행 됩니다. 특히 템플릿 정의의 컨텍스트에서 선언 되지 않은 종속 되지 않은 이름을 ISO c + + 표준에 의해 필요에 따라 진단 메시지를 발생 합니다. 그러나 정의 컨텍스트에서 인수 종속 조회 작업이 수행 되지 않습니다 요구 하는 종속 되지 않은 이름의 바인딩입니다.

```cpp
// dependent base
struct B {
    void g();
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

### <a name="windows-header-issues"></a>Windows 헤더 문제

**관대 한 /-** 옵션은 Windows가 작성자 업데이트 SDK (10.0.16299.0) 하기 전에 Windows 키트의 버전 또는 1709 키트 WDK (Windows 드라이버) 버전에 대 한 굉장히 엄격 합니다. 사용 하도록 최신 버전의 Windows 키트를 업데이트 하는 것이 좋습니다 **관대 한 /-** Windows 또는 장치 드라이버 코드에서.

Windows가 작성자 업데이트 SDK (10.0.16299.0) 또는 Windows 드라이버 키트 (WDK) 1709에서 일부 헤더 파일의 사용과 호환 되지 않을 수 있는 문제에 아직 **관대 한 /-**합니다. 이러한 문제를 해결 하려면 파일에 대해서만 소스 코드를 요구 하 고 제거 하는 이러한 헤더의 사용을 제한 권장는 **관대 한 /-** 해당 특정 소스 코드 파일을 컴파일할 때 옵션입니다. 다음과 같은 문제는 Windows가 작성자 업데이트 SDK (10.0.16299.0)에 달라 집니다.

#### <a name="issue-in-umqueryh"></a>Um\Query.h에서 못한 문제 발생

사용 하는 경우는 **관대 한 /-** 컴파일러 스위치는 `tagRESTRICTION` 구조 case(RTOr) 멤버가 되어 컴파일되지 않습니다. '또는'.

```cpp
struct tagRESTRICTION
    {
    ULONG rt;
    ULONG weight;
    /* [switch_is][switch_type] */ union _URes
        {
        /* [case()] */ NODERESTRICTION ar;
        /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
        /* [case()] */ NODERESTRICTION pxr;
        /* [case()] */ VECTORRESTRICTION vr;
        /* [case()] */ NOTRESTRICTION nr;
        /* [case()] */ CONTENTRESTRICTION cr;
        /* [case()] */ NATLANGUAGERESTRICTION nlr;
        /* [case()] */ PROPERTYRESTRICTION pr;
        /* [default] */  /* Empty union arm */
        } res;
    };
```

이 문제를 해결 하기 위해 없이 Query.h를 포함 하는 파일을 컴파일하는 **관대 한 /-** 옵션입니다.

#### <a name="issue-in-umcellularapioemh"></a>Um\cellularapi_oem.h에서 못한 문제 발생

사용 하는 경우는 **관대 한 /-** 컴파일러 스위치의 정방향 선언은 `enum UICCDATASTOREACCESSMODE` 는 경고를 발생 합니다.

```cpp
typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
```

범위가 지정 되지 않은 열거형의 정방향 선언은 Microsoft 확장입니다. 이 문제를 해결 하기 위해 없이 cellularapi_oem.h를 포함 하는 파일을 컴파일하는 **관대 한 /-** 옵션을 사용 하 여 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 경고 C4471 소리가 나 지 않도록 하려면 옵션입니다.

#### <a name="issue-in-umomscripth"></a>Um\omscript.h에서 못한 문제 발생

C + + 03에서는 문자열 리터럴을에서 BSTR로 변환 (typedef를 ' wchar_t *') 더 이상 사용 되지 않으며 사용할 수 있습니다. C + + 11에서는 변환이 더 이상 허용 됩니다.

```cpp
virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
    /* [in] */ __RPC__in BSTR propname,
    /* [in] */ __RPC__in BSTR expression,
    /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
```

이 문제를 해결 하기 위해 없이 omscript.h를 포함 하는 파일을 컴파일하는 **관대 한 /-** 옵션을 사용 하 여 또는 **/Zc:strictStrings-** 대신 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

Visual Studio 2017 버전 15.5 이상 버전에서이 절차를 사용 합니다.

1. 프로젝트의를 열고 **속성 페이지** 대화 상자.

1. **구성 속성**, 확장 하 고는 **C/c + +** 폴더를 선택 하 고는 **언어** 속성 페이지.

1. 변경 된 **준수 모드** 속성 값을 **예 (허용 /-)**합니다. 선택 **확인** 또는 **적용** 변경 내용을 저장 합니다.

Visual Studio 2017 15.5 버전 보다 이전 버전을이 절차를 사용 합니다.

1. 프로젝트의를 열고 **속성 페이지** 대화 상자.

1. **구성 속성**, 확장 하 고는 **C/c + +** 폴더를 선택 하 고는 **명령줄** 속성 페이지.

1. 입력의 **관대 한 /-** 컴파일러 옵션에는 **추가 옵션** 상자 합니다. 선택 **확인** 또는 **적용** 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](../../build/reference/compiler-options.md)   
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)
