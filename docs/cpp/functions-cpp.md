---
title: "함수 (c + +) | Microsoft Docs"
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 4196abd9d33595c59ae291ea4eba9e8806cce984
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="functions-c"></a>함수(C++)
함수는 일부 작업을 수행하는 코드 블록입니다. 함수는 호출자가 함수에 인수를 전달할 수 있도록 하는 입력 매개 변수를 필요에 따라 정의할 수 있습니다. 함수는 필요에 따라 출력으로 값을 반환할 수 있습니다. 함수는 이상적으로 함수의 기능을 명확하게 설명하는 이름을 사용하여 재사용 가능한 단일 블록에서 일반 작업을 캡슐화하는 데 유용합니다. 다음 함수는 호출자의 두 정수 및; 합계를 반환 합니다. `a` 및 `b` 는 *매개 변수* 형식의 `int`합니다.  
  
```  
int sum(int a, int b)  
{  
    return a + b;  
}  
```  
  
 함수 일 수 ' 호출 또는 *호출*의 다양 한 프로그램에 대 한 위치에서에서 합니다. 함수에 전달 되는 값은 고 *인수*, 그 형식은 함수 정의의 매개 변수 형식과 호환 되어야 합니다.  
  
```  
int main()  
{  
    int i = sum(10, 32);  
    int j = sum(i, 66);  
    cout << "The value of j is" << j << endl; // 108  
}  
```  
  
 함수 길이에 실제적인 제한은 없지만 좋은 디자인은 잘 정의된 단일 작업을 수행하는 함수를 목표로 합니다. 복잡한 알고리즘은 가능하면 이해하기 쉬운 더 간단한 함수로 세분화해야 합니다.  
  
 클래스 범위에서 정의되는 함수는 멤버 함수라고 합니다. 다른 언어와 달리 C++에서는 네임스페이스 범위(암시적 전역 네임스페이스 포함)에서 함수를 정의할 수도 있습니다. 이러한 함수는 호출 *가능한 함수* 또는 *비멤버 함수*; 표준 라이브러리에서 널리 사용 됩니다.  
  
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
  
1.  반환 형식 - 함수가 반환하는 값의 형식을 지정하거나 값이 반환되지 않을 경우 `void`입니다. C + + 11에서는 `auto` 는 return 문에서 형식을 유추 하도록 컴파일러에 지시 하는 유효한 반환 형식입니다. C++14에서는 decltype(auto)도 허용됩니다. 자세한 내용은 아래의 반환 형식에서 형식 추론을 참조하세요.  
  
2.  함수 이름 - 문자 또는 밑줄로 시작하고 공백을 포함할 수 없습니다. 일반적으로 표준 라이브러리 함수 이름의 선행 밑줄은 private 멤버 함수 또는 코드에 사용할 수 없는 비멤버 함수를 나타냅니다. 
  
3.  매개 변수 목록 - 중괄호로 구분되거나 쉼표로 구분된 0개 이상의 매개 변수 집합으로, 함수 본문 내에서 값에 액세스할 수 있는 형식 및 로컬 이름(선택 사항)을 지정합니다. 
  
 함수 선언의 선택적 요소는 다음과 같습니다.  
  
1.  `constexpr` - 함수의 반환 값이 컴파일 시간에 계산할 수 있는 상수 값임을 나타냅니다.  
  
    ```  
    constexpr float exp(float x, int n)  
    {  
        return n == 0 ? 1 :  
            n % 2 == 0 ? exp(x * x, n / 2) :  
            exp(x * x, (n - 1) / 2) * x;  
    };  
    ```  
  
2.  해당 `linkage` 사양, `extern` 또는 `static`입니다.  
  
    ```  
    Declare printf with C linkage.  
    extern "C" int printf( const char *fmt, ... );  
  
    ```  
  
     자세한 내용은 참조 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)합니다.  
  
3.  `inline` - 함수에 대한 모든 호출을 함수 코드 자체로 바꾸도록 컴파일러에 지시합니다. 인라인 처리는 성능이 중요한 코드 섹션에서 함수가 신속하게 실행되고 반복적으로 호출되는 시나리오의 성능 향상에 도움이 됩니다.  
  
    ```  
    inline double Account::GetBalance()  
    {  
        return balance;  
    }  
    ```  
  
     자세한 내용은 참조 [인라인 함수](../cpp/inline-functions-cpp.md)합니다.  
  
4.  A `noexcept` 함수가 예외를 throw 하 고 있는지 여부를 지정 하는 식입니다. 다음 예제에서 함수는 `is_pod` 식이 `true`로 계산되는 경우 예외를 throw하지 않습니다.  
  
    ```  
    #include <type_traits>  
  
    template <typename T>  
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}  
    ```  
  
     자세한 내용은 참조 [noexcept](../cpp/noexcept-cpp.md)합니다.  
  
5.  (멤버 함수만 해당) cv 한정자 - 함수가 `const`인지 `volatile`인지를 지정합니다.  
  
6.  (멤버 함수만 해당) `virtual`, `override` 또는 `final`입니다. `virtual`은 파생 클래스에서 함수를 재정의할 수 있도록 지정합니다. `override`는 파생 클래스의 함수가 가상 함수를 재정의하고 있음을 의미합니다. `final`은 이후 파생 클래스에서 함수를 재정의할 수 없음을 의미합니다. 자세한 내용은 참조 [가상 함수](../cpp/virtual-functions.md)합니다.  
  
7.  (멤버 함수만 해당) 멤버 함수에 적용된 `static`은 함수가 클래스의 개체 인스턴스와 연결되어 있지 않음을 의미합니다.  
  
8.  (비정적 멤버 함수에만 해당) ref 한정자는 시점을 선택 하는 함수 오버 로드를 컴파일러에 지정 하는 암시적 개체 매개 변수 (*이)가 lvalue 참조 및 rvalue 참조입니다.  
  
 다음 그림에서는 함수 정의의 일부분을 보여 줍니다. 음영 처리된 영역은 함수 본문입니다.  
  
 ![함수 정의 부분](../cpp/media/vc38ru1.gif "vc38RU1")  
함수 정의 부분  
  
## <a name="function-definitions"></a>함수 정의  
 본문 내에 선언된 변수는 지역 변수 또는 지역이라고 합니다. 이러한 변수는 함수가 종료될 때 범위를 벗어나므로 함수는 지역에 대한 참조를 반환할 수 없습니다.  
  
## <a name="function-templates"></a>함수 템플릿  
 함수 템플릿은 클래스 템플릿과 유사하며 템플릿 인수에 따라 구체적인 함수를 생성합니다. 대부분의 경우 템플릿은 형식 인수를 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다.  
  
```  
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
  
 기본적으로 인수는 값으로 함수에 전달됩니다. 즉, 함수는 전달할 개체의 복사본을 받는다는 의미입니다. 큰 개체의 경우 복사본을 만들려면 비용이 많이 들 수 있으며 항상 만들 필요는 없습니다. 참조(특히 lvalue 참조)로 인수를 전달하려면 매개 변수에 참조 quaitifer를 추가합니다.  
  
```  
void DoSomething(std::string& input){...}  
```  
  
 함수에서 참조로 전달된 인수를 수정하면 로컬 복사본이 아니라 원래 개체가 수정됩니다. 함수에서 이러한 인수를 수정할 수 없도록 하려면 매개 변수를 const&로 한정합니다.  
  
```  
void DoSomething(const std::string& input){...}  
```  
  
 **C + + 11:** lvalue 참조 또는 rvalue 참조로 전달 되는 인수를 명시적으로 처리 하려면 이중 앰퍼샌드 매개 변수에 범용 참조를 나타내는 데 사용 합니다.  
  
```  
void DoSomething(const std::string&& input){...}  
```  
  
 `void` 키워드가 인수 선언 목록의 처음이자 유일한 멤버이면 매개 변수 선언 목록에서 단일 키워드 `void`로 선언된 함수가 인수를 사용하지 않습니다. `void` 형식의 인수가 목록의 다른 곳에 있으면 오류가 생성됩니다. 예:  
  
```  
  
// OK same as GetTickCount()  
long GetTickCount( void );   
```  
  
 여기에 설명한 경우를 제외하고 `void` 인수를 지정하면 안 되지만 `void` 형식에서 파생된 형식(예: `void`의 포인터 및 `void`의 배열)이 인수 선언 목록 어디에나 나타날 수 있습니다.  
  
### <a name="default-arguments"></a>기본 인수  
 함수 서명에서 마지막 매개 변수에 기본 인수를 할당할 수 있습니다. 즉, 일부 다른 값을 지정하려는 경우가 아니면 함수를 호출할 때 호출자가 인수를 제외할 수 있습니다.  
  
```  
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
 다른 함수 또는 기본 제공 배열을;는 함수를 반환 하지 않을 수 있습니다. 이러한 형식에 대 한 포인터 반환할 수 없지만 또는 *람다*, 함수 개체를 생성 합니다. 이러한 경우를 제외하면 함수는 범위에 있는 모든 형식의 값을 반환하거나 값을 반환하지 않을 수 있으며 이 경우 반환 형식은 `void`입니다.  
  
### <a name="trailing-return-types"></a>후행 반환 형식  
 "일반" 반환 형식은 함수 서명의 왼쪽에 있습니다. A *후행 반환 형식은* 은 서명의 가장 오른쪽에 있고 앞에서-> 연산자입니다. 후행 반환 형식은 반환 값의 형식이 템플릿 매개 변수에 따라 달라지는 경우 함수 템플릿에서 특히 유용합니다.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)  
{  
    return lhs + rhs;   
}  
```  
  
 `auto`가 후행 반환 형식과 함께 사용되는 경우 decltype 식이 생성하는 모든 항목의 자리 표시자 역할만 하며 직접 형식 추론을 수행하지는 않습니다.  

   
## <a name="function-local-variables"></a>함수 지역 변수  
 함수 본문 내에서 선언 되는 변수 라고는 *지역 변수* 또는 간단히 *로컬*합니다. 비정적 지역은 함수 본문 내에만 표시되며, 스택에서 선언될 경우 함수가 종료되면 범위를 벗어납니다. 지역 변수를 생성하고 값으로 반환하는 경우 컴파일러에서 일반적으로 반환 값 최적화를 수행하여 불필요한 복사 작업을 방지합니다. 지역 변수를 참조로 반환하는 경우 해당 참조를 사용하려는 호출자의 모든 시도가 지역이 삭제된 후 수행되므로 컴파일러에서 경고가 발생합니다.  
  
 로컬 정적 개체는 `atexit`로 지정된 종료 중에 소멸됩니다. 프로그램의 제어 흐름이 정적 개체의 선언을 건너뛰었기 때문에 정적 개체가 생성되지 않은 경우에는 해당 개체를 소멸하려고 하지 않습니다.  
  
### <a name="static-local-variables"></a>정적 지역 변수  
 C++에서는 지역 변수를 정적으로 선언할 수 있습니다. 이 변수는 함수 본문 내에만 표시되지만 함수의 모든 인스턴스에 대해 변수의 단일 복사본이 존재합니다.  
  
###  <a name="type_deduction"></a>반환 형식 (C + + 14)에서 형식 추론  
 C++14에서는 `auto`를 사용하여 후행 반환 형식을 제공하지 않고도 함수 본문에서 반환 형식을 유추하도록 컴파일러에 지시할 수 있습니다. 이때 `auto`는 항상 return-by-value로 추론됩니다. `auto&&`를 사용하여 참조를 추론하도록 컴파일러에 지시합니다.  
  
 이 예제에서 `auto`는 lhs 및 rhs 합계의 비const 값 복사로 추론됩니다.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs; //returns a non-const object by value  
}  
```  
  
 `auto` 추론 하는 형식의 const-ness를 유지 하지 않습니다. 반환 값에서 해당 인수의 const-ness나 ref-ness를 유지해야 하는 전달 함수의 경우 `decltype(auto)` 키워드를 사용할 수 있는데, 이 키워드는 `decltype` 형식 유추 규칙을 사용하고 모든 형식 정보를 유지합니다. `decltype(auto)`은 왼쪽에 있는 일반 반환 값이나 후행 반환 값으로 사용할 수 있습니다.  
  
 다음 예제에서는 (의 코드 기반 [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)), 표시 `decltype(auto)` 템플릿이 인스턴스화될 때까지 지는 반환 형식에서 함수 인수의 완벽 한 전달을 사용 하도록 설정 하는 데 사용 되 고 있습니다.  
  
```  
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

2. Std:: tuple 또는 std:: pair 개체를 반환 합니다.

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

3. **Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 사용 하 여 바인딩을 구성 합니다. 구조적 바인딩의 장점은입니다 반환 값을 저장 하는 변수는 초기화 있다고 선언, 동시에 일부 경우에는 훨씬 더 효율적일 수 있습니다. 이 문에서-`auto[x, y, z] = f();`-대괄호 소개 하 고 전체 함수 블록에 대 한 범위에 있는 이름을 초기화 합니다.  

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

4. 반환 값 자체를 사용 하는 것 외에도 "값을 반환할 있습니다" 개수에 관계 없이 함수를 수정 하거나 호출자에 게 제공 하는 개체의 값을 초기화할 수 있도록 참조로 전달에 사용할 매개 변수를 정의 하 여 합니다. 자세한 내용은 참조 [참조 형식 함수 인수](reference-type-function-arguments.md)합니다.
  
## <a name="function-pointers"></a>함수 포인터  
 C++은 C 언어와 동일한 방식으로 함수 포인터를 지원합니다. 그러나 일반적으로 함수 개체를 사용하면 형식이 보다 더 안전합니다.  
  
 함수 포인터 형식을 반환하는 함수를 선언할 경우 `typedef`를 사용하여 함수 포인터 형식에 대한 별칭을 선언하는 것이 좋습니다.  예  
  
```  
typedef int (*fp)(int);  
fp myFunction(char* s); // function returning function pointer  
```  
  
 다른 방법으로, 식별자(위 예제에서 `fp`)를 함수 이름 및 인수 목록으로 대체하여 함수 선언의 올바른 구문을 함수 포인터의 선언자 구문에서 추론할 수 있습니다. 예제는 다음과 같습니다.  
  
```  
int (*myFunction(char* s))(int);  
```  
  
 앞의 선언은 위에서 typedef를 사용한 선언과 같습니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수 오버 로드](../cpp/function-overloading.md)   
 [가변 인수 목록 가진 함수](../cpp/functions-with-variable-argument-lists-cpp.md)   
 [명시적으로 기본 설정 및 삭제 된 함수](../cpp/explicitly-defaulted-and-deleted-functions.md)   
 [함수에 대 한 인수 종속 이름 (Koenig) 조회](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)   
 [기본 인수](../cpp/default-arguments.md)   
 [인라인 함수](../cpp/inline-functions-cpp.md)
