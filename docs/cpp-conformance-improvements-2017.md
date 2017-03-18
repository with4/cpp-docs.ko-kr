---
title: "C++ 컴파일러 규칙 향상 | Microsoft 문서"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
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
translationtype: Human Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: b26df320266a1465e214c70c29c7077d04ffb4b9
ms.lasthandoff: 03/06/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]의 C++ 규칙 향상

## <a name="new-language-features"></a>새 언어 기능  
컴파일러는 일반화된 constexpr을 지원하고 집계에 NSDMI를 사용할 수 있기 때문에 이제 C++14 표준에 추가된 기능을 완벽히 갖췄습니다. 하지만 아직까지 C++11 표준 기능과 C++98 표준 기능이 몇 가지 부족합니다.

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
struct MyList {
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
Visual Studio 2017에서는 조건부 계산 연산의 왼쪽 피연산자가 constexpr 컨텍스트에서 유효하지 않을 경우 정확히 오류를 발생시킵니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 컴파일되지 않습니다.

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // error starting in Visual Studio 2017
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
CStringW를 사용하여 빌드 및 관리되는 문자열의 경우 제공된 ‘operator LPCWSTR()’를 사용하여 CStringW 개체를 서식 문자열에 필요한 C 포인터에 캐스트해야 합니다.

```cpp  
CStringW str1;
CStringW str2;
str1.Format(… , static_cast<LPCWSTR>(str2));
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

### <a name="default-initializers-for-value-class-members-ccli"></a>값 클래스 멤버에 대한 기본 이니셜라이저(C++/CLI)
Visual Studio 2015 이하에서는 컴파일러가 값 클래스 멤버에 대한 기본 멤버 이니셜라이저를 허용하지만 무시했습니다.  값 클래스의 기본 초기화는 항상 멤버를&0;으로 초기화하고 기본 생성자는 허용되지 않습니다.  Visual Studio 2017에서는 기본 멤버 이니셜라이저가 이 예제에 표시된 대로 컴파일러 오류를 발생시킵니다.

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

## <a name="see-also"></a>참고 항목  
[Visual C++ 언어 규칙](visual-cpp-language-conformance.md)  

