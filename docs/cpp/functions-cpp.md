---
title: 함수 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 01/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a78f3bf043c08586916a1776806b0a759beb827
ms.sourcegitcommit: d9ee6f777974d031570f4260c9581ea2c81ad875
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2018
---
# <a name="functions-c"></a>함수(C++)

함수는 일부 작업을 수행하는 코드 블록입니다. 함수는 호출자가 함수에 인수를 전달할 수 있도록 하는 입력 매개 변수를 필요에 따라 정의할 수 있습니다. 함수는 필요에 따라 출력으로 값을 반환할 수 있습니다. 함수는 이상적으로 함수의 기능을 명확하게 설명하는 이름을 사용하여 재사용 가능한 단일 블록에서 일반 작업을 캡슐화하는 데 유용합니다. 다음 함수는 호출자의 두 정수 및; 합계를 반환 합니다. `a` 및 `b` 는 *매개 변수* 형식의 **int**합니다.

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

함수를 호출할 수 있습니다, 또는 *호출*의 다양 한 프로그램에 대 한 위치에서에서 합니다. 함수에 전달 되는 값은 고 *인수*, 그 형식은 함수 정의의 매개 변수 형식과 호환 되어야 합니다.

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

함수 길이에 실제적인 제한은 없지만 좋은 디자인은 잘 정의된 단일 작업을 수행하는 함수를 목표로 합니다. 복잡한 알고리즘은 가능하면 이해하기 쉬운 더 간단한 함수로 세분화해야 합니다.

클래스 범위에서 정의되는 함수는 멤버 함수라고 합니다. 다른 언어와 달리 C++에서는 네임스페이스 범위(암시적 전역 네임스페이스 포함)에서 함수를 정의할 수도 있습니다. 이러한 함수는 호출 *가능한 함수* 또는 *비멤버 함수*; 표준 라이브러리에서 널리 사용 됩니다.

함수가 될 수 있습니다 *오버 로드 된*, 서로 다른 버전의 함수를 의미 하는 공유할 수 있습니다 이름이 같은 경우 번호 및/또는 정식 매개 변수 형식에 따라 달라 집니다. 자세한 내용은 참조 [함수 오버 로드](../cpp/function-overloading.md)합니다.

## <a name="parts-of-a-function-declaration"></a>함수 선언의 요소

최소 함수 *선언* 반환 형식, 함수 이름 및 매개 변수 목록 (비어 있을 수 있습니다), 컴파일러에 추가 지침을 제공 하는 선택적 키워드와 함께 구성 됩니다. 다음 예제는 함수 선언 합니다.

```cpp
int sum(int a, int b);
```

함수 정의 선언 이루어져과 *본문*, 하는 중괄호 사이의 모든 코드:

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

함수 선언과 뒤에 오는 세미콜론은 프로그램의 여러 위치에 나타날 수 있으며, 각 변환 단위에서 해당 함수를 호출하기 전에 나타나야 합니다. 함수 정의는 ODR(단일 정의 규칙)에 따라 프로그램에 한 번만 나타나야 합니다.

함수 선언의 필수 요소는 다음과 같습니다.

1. 함수가 반환 하는 값의 형식을 지정 하는 반환 형식 또는 **void** 없는 값을 반환 합니다. C + + 11에서는 **자동** 는 return 문에서 형식을 유추 하도록 컴파일러에 지시 하는 유효한 반환 형식입니다. C++14에서는 decltype(auto)도 허용됩니다. 자세한 내용은 아래의 반환 형식에서 형식 추론을 참조하세요.

1. 함수 이름 - 문자 또는 밑줄로 시작하고 공백을 포함할 수 없습니다. 일반적으로 표준 라이브러리 함수 이름의 선행 밑줄은 private 멤버 함수 또는 코드에 사용할 수 없는 비멤버 함수를 나타냅니다.

1. 매개 변수 목록 - 중괄호로 구분되거나 쉼표로 구분된 0개 이상의 매개 변수 집합으로, 함수 본문 내에서 값에 액세스할 수 있는 형식 및 로컬 이름(선택 사항)을 지정합니다.

함수 선언의 선택적 요소는 다음과 같습니다.

1. **constexpr**, 컴파일 타임에 계산할 수 있는 함수의 반환 값을 상수 값 임을 나타냅니다.

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. 해당 링크 사양이 **extern** 또는 **정적**합니다.

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

     자세한 내용은 참조 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)합니다.

1. **인라인**는 함수를 호출할 때마다 함수 코드 자체로 바꿉니다 컴파일러에 지시 합니다. 인라인 처리는 성능이 중요한 코드 섹션에서 함수가 신속하게 실행되고 반복적으로 호출되는 시나리오의 성능 향상에 도움이 됩니다.

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

     자세한 내용은 참조 [인라인 함수](../cpp/inline-functions-cpp.md)합니다.

1. A **noexcept** 함수가 예외를 throw 하 고 있는지 여부를 지정 하는 식입니다. 다음 예제에서 함수는 예외를 throw 하지 하는 경우는 `is_pod` 식이 **true**합니다.

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

     자세한 내용은 참조 [noexcept](../cpp/noexcept-cpp.md)합니다.

1. (멤버 함수에만 해당) cv 한정자 함수 인지를 지정 하는 **const** 또는 **휘발성**합니다.

1. (멤버 함수에만 해당) **가상**, **재정의**, 또는 **최종**합니다. **가상** 지정는 함수는 파생된 클래스에서 재정의할 수 있습니다. **재정의** 파생된 클래스에서 함수의 가상 함수 재정의 하는 것을 의미 합니다. **최종** 파생 클래스를 의미에서 추가 함수를 재정의할 수 없습니다. 자세한 내용은 참조 [가상 함수](../cpp/virtual-functions.md)합니다.

1. (멤버 함수에만 해당) **정적** 적용 멤버에 함수는 함수가 클래스의 개체 인스턴스와 연결 하지 않음을 의미 합니다.

1. (비정적 멤버 함수에만 해당) ref 한정자는 시점을 선택 하는 함수 오버 로드를 컴파일러에 지정 하는 암시적 개체 매개 변수 (\*이)가 lvalue 참조 및 rvalue 참조입니다. 자세한 내용은 참조 [함수 오버 로드](function-overloading.md#ref-qualifiers)합니다.

다음 그림에서는 함수 정의의 일부분을 보여 줍니다. 음영 처리된 영역은 함수 본문입니다.

 ![함수 정의 부분](../cpp/media/vc38ru1.gif "vc38RU1") 함수 정의 부분

## <a name="function-definitions"></a>함수 정의

A *함수 정의* 선언과 함수 본문을 중괄호로 묶인 변수 선언, 문 및 식에 포함 된 구성 됩니다. 다음 예제에서는 완전 한 함수 정을 보여 줍니다.

```cpp
    int foo(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       if(strcmp(s, "default") != 0)
       {
            value = mc.do_something(i);
       }
       return value;
    }
```

본문 내에 선언된 변수는 지역 변수 또는 지역이라고 합니다. 이러한 변수는 함수가 종료될 때 범위를 벗어나므로 함수는 지역에 대한 참조를 반환할 수 없습니다.

```cpp
    MyClass& boom(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       mc.Initialize(i,s);
       return mc;
    }
```

## <a name="const-and-constexpr-functions"></a>const 및 constexpr 함수

멤버 함수로 선언할 수 있습니다 **const** 함수는 클래스에서 모든 데이터 멤버의 값을 변경할 수는 지정할 수 있습니다. 멤버 함수로 선언 하 여 **const**, 적용할 컴파일러 도움말 *const 정확성*합니다. 누군가가 실수로로 선언 된 함수를 사용 하 여 개체를 수정 하기 위한 경우 **const**, 컴파일러 오류가 발생 합니다. 자세한 내용은 참조 [const](const-cpp.md)합니다.

함수로 선언 **constexpr** 컴파일 타임에 확인할 수 때 생성 값이 될 수 있습니다. Constexpr 함수는 일반적으로 일반 함수 보다 더 빠르게 실행합니다. 자세한 내용은 참조 [constexpr](constexpr-cpp.md)합니다.

## <a name="function-templates"></a>함수 템플릿

함수 템플릿은 클래스 템플릿과 유사하며 템플릿 인수에 따라 구체적인 함수를 생성합니다. 대부분의 경우 템플릿은 형식 인수를 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

자세한 내용은 참조 [함수 템플릿](../cpp/function-templates.md)

## <a name="function-parameters-and-arguments"></a>함수 매개 변수 및 인수

함수에는 0개 이상 형식의 쉼표로 구분된 매개 변수 목록이 있으며, 각각에는 함수 본문 내에서 액세스할 수 있는 이름이 있습니다. 함수 템플릿은 추가 형식이나 값 매개 변수를 지정할 수 있습니다. 호출자는 형식이 매개 변수 목록과 호환되는 구체적인 값인 인수를 전달합니다.

기본적으로 인수는 값으로 함수에 전달됩니다. 즉, 함수는 전달할 개체의 복사본을 받는다는 의미입니다. 큰 개체의 경우 복사본을 만들려면 비용이 많이 들 수 있으며 항상 만들 필요는 없습니다. 참조 (특히 lvalue 참조)로 전달 될 인수를 매개 변수에 참조 수량자를 추가 합니다.

```cpp
void DoSomething(std::string& input){...}
```

함수에서 참조로 전달된 인수를 수정하면 로컬 복사본이 아니라 원래 개체가 수정됩니다. 함수에서 이러한 인수를 수정할 수 없도록 하려면 매개 변수를 const&로 한정합니다.

```cpp
void DoSomething(const std::string& input){...}
```

 **C + + 11:** 를 rvalue 참조 또는 lvalue 참조로 전달 되는 인수를 명시적으로 처리를 사용 하 여 이중 앰퍼샌드 매개 변수에 범용 참조를 나타냅니다.

```cpp
void DoSomething(const std::string&& input){...}
```

단일 키워드로 선언 된 함수 **void** 매개 변수 선언에서 목록 인수를 사용 하지 키워드는 **void** 처음 이자 유일한 멤버 인수 선언 목록의 합니다. 형식의 인수 **void** 곳 목록에서 오류를 생성 합니다. 예를 들어:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

지정할 수는 없지만 있는지 확인 한 **void** 설명한 인수를 제외 하 고 여기에서 형식에서에서 파생 형식 **void** (에 대 한 포인터와 같은 **void** 및 배열을**void**) 어디에 나 인수 선언 목록 나타날 수 있습니다.

### <a name="default-arguments"></a>기본 인수

함수 서명에서 마지막 매개 변수에 기본 인수를 할당할 수 있습니다. 즉, 일부 다른 값을 지정하려는 경우가 아니면 함수를 호출할 때 호출자가 인수를 제외할 수 있습니다.

```cpp
int DoSomething(int num,
    string str,
    Allocator& alloc = defaultAllocator)
{ ... }

// OK both parameters are at end
int DoSomethingElse(int num,
    string str = string{ "Working" },
    Allocator& alloc = defaultAllocator)
{ ... }

// C2548: 'DoMore': missing default parameter for parameter 2
int DoMore(int num = 5, // Not a trailing parameter!
    string str,
    Allocator& = defaultAllocator)
{...}
```

자세한 내용은 참조 [기본 인수](../cpp/default-arguments.md)합니다.

## <a name="function-return-types"></a>함수 반환 형식

다른 함수 또는 기본 제공 배열을;는 함수를 반환 하지 않을 수 있습니다. 이러한 형식에 대 한 포인터 반환할 수 없지만 또는 *람다*, 함수 개체를 생성 합니다. 제외 하면 이러한 경우에는 함수 범위에 있는 모든 형식의 값을 반환 하거나 값을 반환할 수 있습니다,이 경우 반환 형식이 **void**합니다.

### <a name="trailing-return-types"></a>후행 반환 형식

"일반" 반환 형식은 함수 서명의 왼쪽에 있습니다. A *후행 반환 형식은* 은 서명의 가장 오른쪽에 있고 앞에서-> 연산자입니다. 후행 반환 형식은 반환 값의 형식이 템플릿 매개 변수에 따라 달라지는 경우 함수 템플릿에서 특히 유용합니다.

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

때 **자동** 사용 되는 후행 반환 형식이와 함께, 역할만 자리 표시자는 decltype 식이 생성 하는 형식 및 형식 추론을 수행 되어 있지 않습니다.


## <a name="function-local-variables"></a>함수 지역 변수

함수 본문 내에서 선언 되는 변수 라고는 *지역 변수* 또는 간단히 *로컬*합니다. 비정적 지역은 함수 본문 내에만 표시되며, 스택에서 선언될 경우 함수가 종료되면 범위를 벗어납니다. 지역 변수를 생성하고 값으로 반환하는 경우 컴파일러에서 일반적으로 반환 값 최적화를 수행하여 불필요한 복사 작업을 방지합니다. 지역 변수를 참조로 반환하는 경우 해당 참조를 사용하려는 호출자의 모든 시도가 지역이 제거된 후 수행되므로 컴파일러에서 경고가 발생합니다.

C++에서는 지역 변수를 정적으로 선언할 수 있습니다. 이 변수는 함수 본문 내에만 표시되지만 함수의 모든 인스턴스에 대해 변수의 단일 복사본이 존재합니다. 로 지정 된 종료 중에 로컬 정적 개체 소멸 됩니다 **atexit**합니다. 프로그램의 제어 흐름이 정적 개체의 선언을 건너뛰었기 때문에 정적 개체가 생성되지 않은 경우에는 해당 개체를 제거하려고 하지 않습니다.

##  <a name="type_deduction"></a> 반환 형식 (C + + 14)에서 형식 추론

C + + 14에서는 사용할 수 있습니다 **자동** 후행 반환 형식을 제공 하지 않고도 함수 본문에서 반환 형식을 유추 하도록 컴파일러에 지시 하 합니다. **자동** 항상에 반환 값으로 추론 합니다. 사용 하 여 **자동 & &** 에 대 한 참조를 추론 하도록 컴파일러에 지시 합니다.

이 예제에서는 **자동** lhs 및 rhs 합계의 비 const 값 복사로 추론 됩니다.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

**자동** 추론 하는 형식의 const-ness를 유지 하지 않습니다. 전달 함수의 반환 값 해야 하는 const 특성 또는 ref 특성 인수를 유지 하기를 사용할 수 있습니다는 **decltype (auto)** 키워드를 사용 하 여 **decltype** 형식 유추 규칙 및 모든 형식 정보를 유지 합니다. **decltype (auto)** 후행 반환 값 또는 왼쪽에 있는 일반 반환 값으로 사용할 수 있습니다.

다음 예제에서는 (의 코드 기반 [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)), 표시 **decltype (auto)** 템플릿이 될 때까지 지는 반환 형식에서 함수 인수의 완벽 한 전달을 사용 하도록 설정 하는 데 사용 되 고 인스턴스화됩니다.

```cpp
template<typename F, typename Tuple = tuple<T...>, int... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);
}

template<typename F, typename Tuple = tuple<T...>,
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>
   decltype( auto)
    apply(F&& f, Tuple&& args)
{
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());
}
}
```

## <a name="returning-multiple-values-from-a-function"></a>함수에서 여러 값을 반환합니다.

여러 가지 방법으로 함수에서 둘 이상의 값을 반환 합니다.

1. 명명된 된 클래스 또는 구조체 개체의 값을 캡슐화 합니다. 호출자에 게 표시 되도록 클래스 또는 구조체 정의가 필요 합니다.

    ```cpp
    #include <string>
    #include <iostream>
    
    using namespace std;
    
    struct S
    {
        string name;
        int num;
    };
    
    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }
    
    int main()
    {
        S s = g();
        cout << s.name << " " << s.num << endl;
        return 0;
    }
    ```
    
1. Std:: tuple 또는 std:: pair 개체를 반환 합니다.

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>
    
    using namespace std;
        
    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }
    
    int main()
    {
        auto t = f();
        cout << get<0>(t) << " " << get<1>(t) << " " << get<2>(t) << endl;
     
        // --or--
    
        int myval;
        string myname;
        double mydecimal;
        tie(myval, myname, mydecimal) = f();
        cout << myval << " " << myname << " " << mydecimal << endl;
    
        return 0;
    }
    ```

1. **Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 사용 하 여 바인딩을 구성 합니다. 구조적 바인딩의 장점은입니다 반환 값을 저장 하는 변수는 초기화 있다고 선언, 동시에 일부 경우에는 훨씬 더 효율적일 수 있습니다. 이 문에서-`auto[x, y, z] = f();`-대괄호 소개 하 고 전체 함수 블록에 대 한 범위에 있는 이름을 초기화 합니다.

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>
    
    using namespace std;
    
    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }
    struct S
    {
        string name;
        int num;
    };
    
    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }
    
    int main()
    {
        auto[x, y, z] = f(); // init from tuple
        cout << x << " " << y << " " << z << endl;
    
        auto[a, b] = g(); // init from POD struct
        cout << a << " " << b << endl;
        return 0;
    }
    ```
    
1. 반환 값 자체를 사용 하는 것 외에도 "값을 반환할 있습니다" 개수에 관계 없이 함수를 수정 하거나 호출자에 게 제공 하는 개체의 값을 초기화할 수 있도록 참조로 전달에 사용할 매개 변수를 정의 하 여 합니다. 자세한 내용은 참조 [참조 형식 함수 인수](reference-type-function-arguments.md)합니다.

## <a name="function-pointers"></a>함수 포인터

C++은 C 언어와 동일한 방식으로 함수 포인터를 지원합니다. 그러나 일반적으로 함수 개체를 사용하면 형식이 보다 더 안전합니다.

것이 좋습니다 **typedef** 함수 포인터 형식을 반환 하는 함수를 선언 하는 경우 함수 포인터 형식에 대 한 별칭을 선언 하는 데 사용 됩니다.  예

```cpp
typedef int (*fp)(int);
fp myFunction(char* s); // function returning function pointer
```

다른 방법으로, 식별자(위 예제에서 `fp`)를 함수 이름 및 인수 목록으로 대체하여 함수 선언의 올바른 구문을 함수 포인터의 선언자 구문에서 추론할 수 있습니다. 예제는 다음과 같습니다.

```cpp
int (*myFunction(char* s))(int);
```

앞의 선언은 위에서 typedef를 사용한 선언과 같습니다.

## <a name="see-also"></a>참고 항목

- [함수 오버로드](../cpp/function-overloading.md)
- [가변 인수 목록을 사용하는 함수](../cpp/functions-with-variable-argument-lists-cpp.md)
- [명시적으로 기본 설정 및 삭제된 함수](../cpp/explicitly-defaulted-and-deleted-functions.md)
- [함수에 대한 인수 종속 이름(Koenig) 조회](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)
- [기본 인수](../cpp/default-arguments.md)
- [인라인 함수](../cpp/inline-functions-cpp.md)
