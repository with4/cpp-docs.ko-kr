---
title: "C++ 컴파일러 규칙 향상 | Microsoft 문서"
ms.custom: 
ms.date: 06/05/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: d00951204a358ec064f69035b7dd6ac5adc08ed9
ms.contentlocale: ko-kr
ms.lasthandoff: 06/08/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]의 C++ 규칙 향상
업데이트 버전 15.3의 향상된 기능을 확인하려면 [Visual Studio 업데이트 버전 15.3의 버그 수정](#update_153)을 참조하세요.
## <a name="new-language-features"></a>새 언어 기능  
컴파일러는 일반화된 constexpr을 지원하고 집계에 NSDMI를 사용할 수 있기 때문에 이제 C++14 표준에 추가된 기능을 완벽히 갖췄습니다. 하지만 아직까지 C++11 표준 기능과 C++98 표준 기능이 몇 가지 부족합니다. 컴파일러의 현재 상태를 보여 주는 테이블은 [Visual C++ Language Conformance](visual-cpp-language-conformance.md)(Visual C++ 언어 규칙)를 참조하세요.

### <a name="c11"></a>C++11:
**더 많은 라이브러리의 SFINAE 식 지원** Visual C++ 컴파일러는 decltype 및 constexpr 식이 템플릿 매개 변수로 나타날 수 있는 템플릿 인수 감소 및 대체에 필요한 SFINAE 식에 대한 지원을 계속 개선하고 있습니다. 자세한 내용은 [Expression SFINAE improvements in Visual Studio 2017 RC](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3)(Visual Studio 2017 RC의 SFINAE 식 향상)를 참조하세요. 


### <a name="c-14"></a>C++ 14:
**집계용 NSDMI** 집계는 사용자 제공 생성자가 없고, 개인 또는 보호된 비정적 데이터 멤버가 없고, 기본 클래스가 없고, 가상 함수가 없는 배열 또는 클래스입니다. C++14부터 집계에 멤버 이니셜라이저가 포함될 수 있습니다. 자세한 내용은 [Member initializers and aggregates](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html)(멤버 이니셜라이저 및 집계)를 참조하세요.

**확장된 constexpr** constexpr로 선언된 식은 이제 특정 종류의 선언, if 및 switch 문, loop 문 및 수명이 constexpr 식 계산 내에서 시작된 개체의 변형을 포함할 수 있습니다. 또한 더 이상 constexpr 비정적 멤버 함수가 암시적으로 생성될 필요가 없습니다. 자세한 내용은 [Relaxing constraints on constexpr functions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)(constexpr 함수에 대한 제약 조건 완화)를 참조하세요. 

### <a name="c17"></a>C++17:
**간결한 static_assert**(/std:c++latest와 함께 사용 가능) C++17에서 static_assert에 대한 메시지 매개 변수는 선택 사항입니다. 자세한 내용은 [Extending static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)(static_assert 확장, v2)를 참조하세요. 

**[[fallthrough]] 특성**(/std:c++latest와 함께 사용 가능) [[fallthrough]] 특성은 switch 문의 컨텍스트에서 제어 이동 동작이 의도된 컴파일러에 대한 힌트로 사용될 수 있습니다. 이 특성을 사용하면 컴파일러가 해당하는 경우에 경고를 실행하지 않습니다. 자세한 내용은 [Wording for [[fallthrough]] attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf)([[fallthrough]] 특성에 대한 표현)를 참조하세요. 

**일반화된 range-based for 루프**(컴파일러 스위치가 필요하지 않음) Range-based for 루프에는 더 이상 같은 형식의 begin() 및 end() 반환 개체가 필요하지 않습니다. 이 기능을 사용하면 end()가 Ranges-V3 제안에 정의된 대로 범위에서 사용되는 sentinel 개체를 반환할 수 있습니다. 자세한 내용은 [Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)(Range-Based For 루프 일반화) 및 [range-v3 library on GitHub](https://github.com/ericniebler/range-v3)(GitHub의 range-v3 라이브러리)를 참조하세요. 


Visual Studio 2015, 업데이트 3까지 규칙 향상의 전체 목록은 [Visual C++ What's New 2003 through 2015](https://msdn.microsoft.com/en-us/library/mt723604.aspx)(2003부터 2015까지 Visual C++의 새로운 기능)를 참조하세요.

## <a name="bug-fixes"></a>버그 수정
### <a name="copy-list-initialization"></a>Copy-list-initialization
Visual Studio 2017에서는 Visual Studio 2015에서 파악되지 않았고 크래시나 정의되지 않은 런타임 동작을 일으킬 수 있는 이니셜라이저 목록을 사용한 개체 만들기에 관련된 컴파일러 오류를 정확히 발생시킵니다.  N4594 13.3.1.7p1에 따라 copy-list-initialization에서 컴파일러는 오버로드 확인을 위해 명시적 생성자를 고려해야 하지만 실제로 오버로드가 선택되면 오류를 발생시켜야 합니다. 

다음 두 가지 예제는 Visual Studio 2015에서 컴파일되지만 Visual Studio 2017에서 컴파일되지 않습니다.
```cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```
오류를 수정하려면 직접 초기화를 사용합니다.
```cpp  
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015에서 컴파일러는 일반 copy-initialization과 같은 방식으로 copy-list-initialization을 잘못 처리했고 오버로드 확인을 위해 생성자 변환만 고려했습니다. 다음 예제에서 Visual Studio 2015에서는 MyInt(23)를 선택하지만 Visual Studio 2017에서는 정확히 오류를 발생시킵니다. 

```cpp  
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

이 예제는 이전 예제와 비슷하지만 다른 오류를 발생시킵니다. 이 예제는 Visual Studio 2015에서는 성공하지만 Visual Studio 2017(C2668 포함)에서는 실패합니다. 

```cpp  
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>사용되지 않는 형식 정의
Visual Studio 2017에서는 이제 클래스 또는 구조체에서 선언된 사용되지 않는 형식 정의에 대한 올바른 경고를 실행합니다. 다음 예제는 Visual Studio 2015에서는 경고 없이 컴파일되지만 Visual Studio 2017에서는 C4996를 생성합니다.

```cpp  
struct A 
{
    // also for __declspec(deprecated) 
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr
Visual Studio 2017에서는 조건부 계산 연산의 왼쪽 피연산자가 constexpr 컨텍스트에서 유효하지 않을 경우 정확히 오류를 발생시킵니다. 다음 코드는 Visual Studio 2017이 아닌 Visual Studio 2015에서 컴파일합니다(C3615 constexpr 함수 ‘f’는 상수 식이 될 수 없음).

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // C3615    
}
```
오류를 수정하려면 array::size() 함수를 constexpr로 선언하거나 f에서 constexpr 한정자를 제거합니다. 

### <a name="class-types-passed-to-variadic-functions"></a>variadic 함수에 전달된 클래스 형식
Visual Studio 2017에서 printf와 같이 variadic 함수에 전달된 클래스 또는 구조체는 일반적으로 복사 가능합니다. 해당 개체를 전달할 때 컴파일러는 비트 복사본을 만들기만 하고 생성자 또는 소멸자를 호출하지 않습니다. 

```cpp  
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```
오류를 수정하려면 일반적으로 복사 가능한 형식을 반환하는 멤버 함수를 호출하거나 

```cpp  
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```
정적 캐스트를 수행하여 개체를 변환한 후 전달합니다.
```cpp  
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```
CStringW를 사용하여 빌드 및 관리되는 문자열의 경우 제공된 `operator LPCWSTR()`를 사용하여 CStringW 개체를 서식 문자열에 필요한 C 포인터에 캐스트해야 합니다.

```cpp  
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>클래스 생성의 cv 한정자
Visual Studio 2015에서는 컴파일러가 생성자 호출을 통해 클래스 개체를 생성할 때 cv 한정자를 잘못 무시하는 경우가 있습니다. 이로 인해 잠재적으로 크래시 또는 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 컴파일러 오류를 발생시킵니다.

```cpp  
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```
오류를 수정하려면 operator int()를 생성자로 선언합니다. 

### <a name="access-checking-on-qualified-names-in-templates"></a>템플릿의 정규화된 이름에 대한 액세스 검사
이전 버전의 컴파일러는 일부 템플릿 컨텍스트에서 정규화된 이름에 대한 액세스 검사를 수행하지 않았습니다. 이는 이름에 액세스할 수 없기 때문에 대체에 실패할 것으로 예상되는 경우 예상되는 SFINAE 동작을 방해할 수 있습니다. 따라서 컴파일러가 연산자의 잘못된 오버로드를 잘못 호출하기 때문에 잠재적으로 런타임에 크래시나 예기치 않은 동작이 발생했을 수 있습니다. Visual Studio 2017에서는 컴파일러 오류가 발생합니다. 구체적인 오류는 달라질 수 있지만 일반적으로 오류는 “C2672 일치하는 오버로드된 함수가 없습니다.”입니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 발생시킵니다.

```cpp  
#include <type_traits>

template <class T> class S {
       typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
       f(10); // C2672: No matching overloaded function found. 
}
```

### <a name="missing-template-argument-lists"></a>누락된 템플릿 인수 목록
Visual Studio 2015 이하에서는 템플릿이 템플릿 매개 변수 목록에 나타날 때(예: 기본 템플릿 인수 또는 형식 없는 템플릿 매개 변수의 일부로) 컴파일러가 누락된 템플릿 인수 목록을 진단하지 않았습니다. 이로 인해 컴파일러 크래시나 예기치 않은 런타임 동작을 포함하여 예기치 않은 동작이 발생할 수 있습니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 생성합니다.

```cpp  
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;  
```

### <a name="expression-sfinae"></a>SFINAE 식
SFINAE 식을 지원하기 위해 이제 컴파일러는 템플릿이 인스턴스화가 아니라 선언될 때 decltype 인수를 구문 분석합니다. 따라서 decltype 인수에 독립적 특수화가 있는 경우 이 특수화는 인스턴스화 시점으로 연기되지 않고 즉시 처리되며 결과 오류가 이 시점에 진단됩니다.  

다음 예제에서는 선언 시점에 발생한 컴파일러 오류를 보여 줍니다.

```cpp  
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
       struct BadType {};
       template <class U>
       static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
       template <class U>
       static BadType Test(...);
       static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```
### <a name="classes-declared-in-anonymous-namespaces"></a>익명 네임스페이스에 선언된 클래스
C++ 표준에 따라 익명 네임스페이스 내에 선언된 클래스는 내부 링크가 있으므로 내보낼 수 없습니다. Visual Studio 2015 이전 버전에서는 이 규칙이 적용되지 않았습니다. Visual Studio 2017에서는 이 규칙이 부분적으로 적용됩니다. 다음 예제에서는 Visual Studio 2017에서 "오류 C2201: ' const `anonymous namespace'::S1::`vftable'': 가져오거나 내보내려면 외부 링크가 있어야 합니다." 오류를 발생시킵니다.

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>값 클래스 멤버에 대한 기본 이니셜라이저(C++/CLI)
Visual Studio 2015 이하에서는 컴파일러가 값 클래스 멤버에 대한 기본 멤버 이니셜라이저를 허용하지만 무시했습니다.  값 클래스의 기본 초기화는 항상 멤버를 0으로 초기화하고 기본 생성자는 허용되지 않습니다.  Visual Studio 2017에서는 기본 멤버 이니셜라이저가 이 예제에 표시된 대로 컴파일러 오류를 발생시킵니다.

```cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>기본 인덱서(C++/CLI)
Visual Studio 2015 이하에서는 컴파일러가 기본 속성을 기본 인덱서로 잘못 식별하는 경우가 있었습니다. 속성에 액세스하는 데 식별자 "default"를 사용하여 문제를 해결할 수 있었습니다. default가 C++11에서 키워드로 도입된 이후 해결 방법 자체가 문제가 되었습니다. 따라서 Visual Studio 2017에서는 해결 방법이 필요했던 버그가 수정되었고 이제 컴파일러는 "default"가 클래스에 대한 기본 속성에 액세스하는 데 사용될 경우 오류를 발생시킵니다.

```cpp  
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

 
// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Visual Studio 2017에서는 이름을 사용하여 값 속성에 둘 다 액세스할 수 있습니다.

```cpp  
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> Visual Studio 2017 업데이트 버전 15.3
### <a name="calls-to-deleted-member-templates"></a>삭제된 멤버 템플릿에 대한 호출
Visual Studio의 이전 버전에서는 경우에 따라 컴파일러가 런타임에 충돌을 일으킬 수 있는 삭제된 멤버 템플릿에 대한 잘못된 형식의 호출에 관련된 오류를 내보내지 못합니다. 다음 코드는 C2280 “‘int S<int>::f<int>(void)’: 삭제된 함수를 참조하려고 합니다.”를 생성합니다.
```cpp
template<typename T> 
struct S { 
   template<typename U> static int f() = delete; 
}; 
 
void g() 
{ 
   decltype(S<int>::f<int>()) i; // this should fail 
}
```
오류를 해결하려면 i를 `int`로 선언합니다.

### <a name="pre-condition-checks-for-type-traits"></a>형식 특성에 대한 전제 조건 검사
Visual Studio 2017 업데이트 버전 15.3에서는 표준을 더 엄격하게 따르도록 형식 특성에 대한 전제 조건 검사가 향상됩니다. 해당 검사는 할당 가능합니다. 다음 코드는 업데이트 버전 15.3에서 C2139를 생성합니다.

```cpp
struct S; 
enum E; 
 
static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>네이티브에서 관리로의 마샬링에 대한 새로운 컴파일러 경고 및 런타임 검사
관리되는 함수에서 네이티브 함수로 호출하려면 마샬링이 필요합니다. CLR는 마샬링을 수행하지만 C++ 의미 체계를 이해하지 못합니다. 네이티브 개체를 값으로 전달하면 CLR는 개체의 복사 생성자를 호출하거나 런타임에 정의되지 않은 동작을 생성할 수 있는 BitBlt를 사용합니다. 
 
이제 컴파일러는 컴파일 시간에 삭제된 복사 ctor를 포함하는 네이티브 개체가 네이티브 경계와 관리되는 경계 사이에 값으로 전달됨을 알 수 있는 경우 경고를 내보냅니다. 컴파일러가 컴파일 시간에 알 수 없는 경우 컴파일러는 잘못된 형식의 마샬링이 수행될 때 프로그램이 즉시 std::terminate를 호출하도록 런타임 검사를 삽입합니다. 업데이트 버전 15.3에서 다음 코드는 C4606을 생성합니다. “ ‘A’: 네이티브 및 관리 경계에서 인수를 값별로 전달하려면 유효한 복사 생성자가 필요합니다. 이 생성자가 없으면 런타임 동작이 정의되지 않습니다.”
```cpp
class A 
{ 
public: 
   A() : p_(new int) {} 
   ~A() { delete p_; } 
 
   A(A const &) = delete; 
   A(A &&rhs) { 
   p_ = rhs.p_; 
} 
 
private: 
   int *p_; 
}; 
 
#pragma unmanaged 
 
void f(A a) 
{ 
} 
 
#pragma managed 
 
int main() 
{ 
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which will result in a double-free later. 
}
```
오류를 해결하려면 `#pragma managed` 지시문을 제거하여 호출자를 네이티브로 표시하고 마샬링을 피합니다. 

### <a name="experimental-api-warning-for-winrt"></a>WinRT에 대한 실험적 API 경고
실험 및 피드백용으로 릴리스된 WinRT API는 `Windows.Foundation.Metadata.ExperimentalAttribute`로 데코레이트됩니다. 업데이트 버전 15.3에서 컴파일러는 특성을 발견할 경우 경고 C4698을 생성합니다. 이전 Windows SDK 버전의 몇몇 API는 이미 특성으로 데코레이트되었고 이러한 API를 호출하면 이 컴파일러 경고의 트리거가 시작됩니다. 최신 Windows SDK에서는 모든 제공된 형식에서 특성이 제거되지만 이전 SDK를 사용 중인 경우에는 모든 제공된 형식 호출에 대해 이러한 경고를 표시하지 않아야 합니다.
다음 코드는 경고 C4698을 생성합니다. “‘Windows::Storage::IApplicationDataStatics2::GetForUserAsync’는 평가 목적으로만 제공되며 향후 업데이트에서 변경되거나 제거될 수 있습니다.”
```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() //C4698
```

이 경고를 사용하지 않도록 설정하려면 #pragma를 추가합니다.

```cpp
#pragma warning(push) 
#pragma warning(disable:4698) 
 
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() 
 
#pragma warning(pop)
```
### <a name="out-of-line-definition-of-a-template-member-function"></a>템플릿 멤버 함수의 확장 정의 
업데이트 버전 15.3에서는 클래스에서 선언되지 않은 템플릿 멤버 함수의 확장 정의를 발견할 경우 오류를 생성합니다. 다음 코드는 오류 C2039를 생성합니다. ‘f’:이 ‘S’의 멤버가 아닙니다.

```cpp
struct S {}; 
 
template <typename T> 
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

오류를 해결하려면 클래스에 선언을 추가합니다.

```cpp
struct S { 
    template <typename T> 
    void f(T t); 
}; 
template <typename T> 
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>“this” 포인터의 주소를 가져오려고 합니다.
C++에서 ‘this’는 X에 대한 형식 포인터의 prvalue입니다. ‘this’의 주소를 가져오거나 lvalue 참조에 바인딩할 수 없습니다. 이전 버전의 Visual Studio에서는 컴파일러를 통해 캐스트를 수행하여 이 제한 사항을 회피할 수 있습니다. 업데이트 버전 15.3에서 컴파일러는 오류 C2664를 생성합니다.

### <a name="conversion-to-an-inaccessible-base-class"></a>액세스할 수 없는 기본 클래스로의 변환
업데이트 버전 15.3에서는 형식을 액세스할 수 없는 기본 클래스로 변환하려고 할 때 오류를 생성합니다. 이제 컴파일러는  
“오류 C2243: ‘type cast’: ‘D *’에서 ‘B *’로의 변환이 있지만 액세스할 수 없습니다.”를 발생시킵니다. 다음 코드는 형식이 잘못되었고 런타임에 충돌을 일으킬 수 있습니다. 이제 컴파일러는 다음과 같은 코드를 발견할 때 C2243을 생성합니다.

```cpp
#include <memory> 
 
class B { }; 
class D : B { }; // C2243. should be public B { }; 
 
void f() 
{ 
   std::unique_ptr<B>(new D()); 
}
```
### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>기본 인수는 멤버 함수의 확장 정의에서 허용되지 않음
기본 인수는 템플릿 클래스에 있는 멤버 함수의 확장 정의에서 허용되지 않습니다.  컴파일러는 /permissive에서는 경고를 생성하고 /permissive-에서는 하드 오류를 생성합니다. 이전 버전의 Visual Studio에서는 다음 잘못된 형식의 코드가 런타임 충돌을 일으킬 수 있습니다. 업데이트 버전 15.3에서는 경고 C5034를 생성합니다. ‘A<T>::f’: 클래스 템플릿 멤버의 확장 정의에는 기본 인수가 포함될 수 없습니다.
```cpp
 
template <typename T> 
struct A { 
    T f(T t, bool b = false); 
}; 
 
template <typename T> 
T A<T>::f(T t, bool b = false) // C5034
{ 
... 
}
```
오류를 해결하려면 “= false” 기본 인수를 제거합니다. 

### <a name="use-of-offsetof-with-compound-member-designator"></a>복합 멤버 지정자와 함께 offsetof 사용
업데이트 버전 15.3에서 m이 “복합 멤버 지정자”인 offsetof(T, m)를 사용하면 /Wall 옵션으로 컴파일할 때 경고가 발생합니다. 다음 코드는 형식이 잘못되었고 런타임에 충돌을 일으킬 수 있습니다. 업데이트 버전 15.3에서는 “경고 C4841: 비표준 확장이 사용됨: offseto의 복합 멤버 지정자”를 생성합니다.

```cpp
  
struct A { 
int arr[10]; 
}; 
 
// warning C4841: non-standard extension used: compound member designator in offsetof 
constexpr auto off = offsetof(A, arr[2]);
```
코드를 수정하려면 pragma를 사용하여 경고를 사용하지 않도록 설정하거나 offsetof를 사용하지 않도록 코드를 변경합니다. 

```cpp
#pragma warning(push) 
#pragma warning(disable: 4841) 
constexpr auto off = offsetof(A, arr[2]); 
#pragma warning(pop) 
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>정적 데이터 멤버 또는 멤버 함수와 함께 offsetof 사용
업데이트 버전 15.3에서 m이 정적 데이터 멤버 또는 멤버 함수를 참조하는 offsetof(T, m)를 사용하면 오류가 발생합니다. 다음 코드는 “오류 C4597: 정의되지 않은 동작: offsetof가 멤버 함수 ‘foo’에 적용되었습니다.” 및 “오류 C4597: 정의되지 않은 동작: offsetof가 정적 데이터 멤버 ‘bar’에 적용되었습니다.”를 생성합니다.
```cpp
 
#include <cstddef> 
 
struct A { 
int foo() { return 10; } 
static constexpr int bar = 0; 
}; 
 
constexpr auto off = offsetof(A, foo); 
Constexpr auto off2 = offsetof(A, bar);
```
 
이 코드는 형식이 잘못되었고 런타임에 충돌을 일으킬 수 있습니다. 오류를 해결하려면 정의되지 않은 동작을 더 이상 호출하지 않도록 코드를 변경합니다. 이는 C++ 표준에서 허용되지 않는 이식할 수 없는 코드입니다.

### <a name="new-warning-on-declspec-attributes"></a>declspec 특성에 대한 새로운 경고
업데이트 버전 15.3에서 컴파일러는 __declspec(…)가 extern “C” 링크 사양 앞에 적용될 경우 더 이상 특성을 무시하지 않습니다. 이전 버전에서는 컴파일러가 런타임 의미를 가질 수 있는 특성을 무시합니다. `/Wall /WX` 옵션이 설정되면 다음 코드는 “경고 C4768: 링크 사양 앞의 __declspec 특성은 무시됩니다.”를 생성합니다.

```cpp
 
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

경고를 해결하려면 extern “C”를 먼저 삽입합니다.

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```
이 경고는 기본적으로 꺼져 있으며 `/Wall /WX`로 컴파일된 코드에만 영향을 줍니다.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype 및 삭제된 소멸자 호출
이전 버전의 Visual Studio에서 컴파일러는 삭제된 소멸자 호출이 ‘decltype’과 연결된 식의 컨텍스트에서 발생한 시점을 검색하지 않았습니다. 업데이트 버전 15.3에서 다음 코드는 “오류 C2280: ‘A<T>::~A(void)’: 삭제된 함수를 참조하려고 합니다.”를 생성합니다.

```cpp
template<typename T> 
struct A 
{ 
   ~A() = delete; 
}; 
 
template<typename T> 
auto f() -> A<T>; 
 
template<typename T> 
auto g(T) -> decltype((f<T>())); 
 
void h() 
{ 
   g(42); 
}
```
### <a name="uninitialized-const-variables"></a>초기화되지 않은 const 변수
Visual Studio 2017 RTW 릴리스에는 ‘const’ 변수가 초기화되지 않으면 C++ 컴파일러가 진단을 실행하지 않는 재발 문제가 있었습니다. 이 재발 문제는 Visual Studio 2017 업데이트 1에서 해결되었습니다. 다음 코드는 “경고 C4132: ‘Value’: const 개체를 초기화해야 합니다.”를 생성합니다.

```cpp
const int Value; //C4132
```
오류를 해결하려면 `Value`에 값을 할당합니다.

### <a name="empty-declarations"></a>빈 선언
이제 Visual Studio 2017 업데이트 버전 15.3에서는 기본 제공 형식만이 아닌 모든 형식의 빈 선언에 대해 경고를 생성합니다. 다음 코드는 모든 네 가지 선언에 대한 수준 2 C4091 경고를 생성합니다.

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };
 
int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

경고를 제거하려면 빈 선언을 주석으로 처리하거나 제거합니다.  명명되지 않은 개체에 부작용(예: RAII)을 포함하려면 개체에 이름을 지정해야 합니다.
 
경고는 /Wv:18에서는 제외되고 기본적으로 경고 수준 W2에서 켜집니다.


### <a name="stdisconvertible-for-array-types"></a>배열 형식에 대한 std::is_convertible
이전 버전의 컴파일러는 배열 형식에 대한 [std::is_convertible](standard-library/is-convertible-class.md)에 대해 잘못된 결과를 제공했습니다. 따라서 라이브러리 작성자는 `std::is_convertable<…>` 형식 특성을 사용할 때 특별히 Visual C++ 컴파일러를 사용해야 했습니다. 다음 예제에서는 정적 어설션이 이전 버전의 Visual Studio는 통과하나 Visual Studio 2017 업데이트 버전 15.3은 통과하지 못합니다.

```cpp
#include <type_traits>
 
using Array = char[1];
 
static_assert(std::is_convertible<Array, Array>::value);
static_assert((std::is_convertible<const Array, const Array>::value), "");
static_assert((std::is_convertible<Array&, Array>::value), "");
static_assert((std::is_convertible<Array, Array&>::value), "");
```

가상의 함수 정의가 올바른 형식으로 되어 있는지 확인하는 방법으로 **std::is_convertible<From, To>**가 계산됩니다.
```cpp 
   To test() { return std::declval<From>(); }
``` 

### <a name="private-destructors-and-stdisconstructible"></a>비공개 소멸자 및 std::is_constructible
이전 버전의 컴파일러는 [std::is_constructible](standard-library/is-constructible-class.md)의 결과를 결정할 때 소멸자가 비공개인지 여부를 무시합니다. 그러나 지금은 비공개 여부를 고려합니다. 다음 예제에서는 정적 어설션이 이전 버전의 Visual Studio는 통과하나 Visual Studio 2017 업데이트 버전 15.3은 통과하지 못합니다.

```cpp
#include <type_traits>
 
class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};
 
// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```  

비공개 소멸자는 형식을 non-constructible로 만듭니다. 다음 선언이 작성된 것처럼 **std::is_constructible<T, Args…>**가 계산됩니다.
```cpp 
   T obj(std::declval<Args>()…)
``` 
이 호출은 소멸자 호출을 의미합니다.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: 모호한 오버로드 확인
이전 버전의 컴파일러는 선언 및 인수 종속적인 조회를 모두 사용하여 검색할 때 모호성을 감지하지 못하는 경우가 종종 있었습니다. 그러면 잘못된 오버로드를 선택하고 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제에서는 Visual Studio 2017 업데이트 버전 15.3이 오버로드된 함수에 C2668 ‘f’: 모호한 호출을 정확히 수행합니다.

```cpp
namespace N {
   template<class T>
   void f(T&, T&);
 
   template<class T>
   void f();
}
 
template<class T>
void f(T&, T&);
 
struct S {};
void f()
{
   using N::f; 
 
   S s1, s2;
   f(s1, s2); // C2668
}
```
::f()를 호출하려는 경우 코드를 수정하려면 사용 중인 N::f 문을 제거합니다.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: 로컬 함수 선언 및 인수 종속 조회
로컬 함수 선언은 바깥쪽 범위에 있는 함수 선언을 숨기고 인수 종속 조회를 사용하지 않도록 설정합니다.
그러나 이 경우에는 이전 버전의 Visual C++ 컴파일러가 인수 종속 조회를 수행했으므로 잘못된 오버로드를 선택하고 예기치 않은 런타임 동작이 발생할 가능성이 있습니다. 일반적으로 오류는 로컬 함수 선언의 잘못된 시그니처 때문입니다. 다음 예제에서는 Visual Studio 2017 업데이트 버전 15.3이 C2660 ‘f’: 함수가 2개의 인수를 사용하지 않음을 정확히 수행합니다.

```cpp
struct S {}; 
void f(S, int);
 
void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

이 문제를 해결하려면 **f(S)** 시그니처를 변경하거나 제거합니다.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: 이니셜라이저 목록에서 초기화 순서
클래스 구성원은 이니셜라이저 목록에 나타나는 순서가 아니라 선언된 순서대로 초기화됩니다. 이전 버전의 컴파일러는 이니셜라이저 목록의 순서가 선언 순서와 다른 경우 경고를 표시하지 않았습니다. 이로 인해 한 구성원의 초기화가 이미 초기화되고 있는 목록의 다른 구성원에 종속되는 경우에는 정의되지 않은 런타임 동작이 발생할 수 있었습니다. 다음 예제에서는 Visual Studio 2017 업데이트 버전 15.3(/Wall 또는 /WX 포함)에서 C5038: 데이터 구성원 ‘A::y’가 데이터 구성원 ‘A::x’ 이후에 초기화됨 경고가 발생합니다.

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};

```
문제를 해결하려면 선언과 같은 순서가 되도록 이니셜라이저 목록을 정렬합니다. 하나 또는 두 이니셜라이저가 기본 클래스 구성원을 참조하는 경우 유사한 경고가 발생합니다.

이 경고는 기본적으로 꺼져 있으며 /Wall 또는 /WX를 사용하여 컴파일한 코드에만 영향을 줍니다.

## <a name="see-also"></a>참고 항목  
[Visual C++ 언어 규칙](visual-cpp-language-conformance.md)  

