---
title: "C + +의 람다 식 | Microsoft Docs"
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b7af430bd8c509713d5be76ea0f64601a91c35cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="lambda-expressions-in-c"></a>C++의 람다 식
C + + 11 이상 버전에서는 람다 식을-라고도 *람다*-익명 함수 개체를 정의 하는 편리한 방법 (한 *클로저*) 여기서은 호출 되었거나 인수로 서 전달 된 위치에서 바로 에 함수입니다. 일반적으로 람다는 알고리즘이나 비동기 메서드에 전달되는 몇 줄의 코드를 캡슐화하는 데 사용됩니다. 이 문서에서는 람다가 무엇인지 정의하고 다른 프로그래밍 기법과 비교하고 그 장점을 설명하며 기본 예제를 제공합니다.  

## <a name="related-topics"></a>관련 항목
- [함수 개체와 비교 람다 식](lambda-expression-syntax.md)
- [람다 식 작업](examples-of-lambda-expressions.md)
- [constexpr 람다 식](lambda-expressions-constexpr.md)

## <a name="parts-of-a-lambda-expression"></a>람다 식의 부분  
 ISO C++ 표준에서는 `std::sort()` 함수에 세 번째 인수로 전달되는 간단한 람다를 보여 줍니다.  
  
```cpp  
#include <algorithm>  
#include <cmath>  
  
void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
            return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
}  
  
```  
  
 이 그림에서는 람다의 부분을 보여 줍니다.  
  
 ![람다 식의 구조 요소](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *캡처 절* (라고도 *람다 유도* c + + 사양에.)  
  
2.  *매개 변수 목록* 선택 사항입니다. (라고도 *람다 선언 자*)  
  
3.  *변경 가능한 사양을* 선택 사항입니다.  
  
4.  *예외 사양이* 선택 사항입니다.  
  
5.  *후행 반환 형식당* 선택 사항입니다.  
  
6.  *람다 본문*)  
  
### <a name="capture-clause"></a>캡처 절  
 람다 본문에 새 변수를 제공할 수 있습니다 (에서 **C + + 14**), 하며 액세스를 수 있습니다. 또는 *캡처*, 주변 범위에서 변수입니다. 람다 캡처 절과 함께 시작 (*람다 유도* 표준 구문에서는)은 캡처되는 변수 및 캡처가 값 이나 참조로 인지 지정 합니다. 앰퍼샌드(`&`) 접두사가 있는 변수는 참조로 액세스되며 이 접두사가 없는 변수는 값으로 액세스됩니다.  
  
 빈 캡처 절인 `[ ]`는 람다 식의 본문이 바깥쪽 범위의 변수에 액세스하지 않음을 나타냅니다.  
  
 기본 캡처 모드를 사용할 수 있습니다 (*캡처 기본값* 표준 구문에서는)는 외부 람다에서 참조 되는 변수를 캡처하는 방법을 나타내기 위해: `[&]` 에서 캡처된 모든 변수가 참조 하는 방법 참조 및 `[=]` 값별로 캡처되 것을 의미 합니다. 기본 캡처 모드를 사용하고 특정 변수에 대해서는 반대 모드를 지정할 수 있습니다. 예를 들어, 람다 본문이 외부 변수 `total`에 참조별로 액세스하고 외부 변수 `factor`에 값별로 액세스하는 경우 다음 캡처 절이 동일합니다.  
  
```cpp  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 캡처 기본값 사용 되는 경우 람다에 언급 된 변수만 캡처됩니다.  
  
 캡처 절 캡처 기본값을 포함 하는 경우 `&`, 없습니다 `identifier` 에 `capture` 해당 캡처 절의 형태가 될 수 `& identifier`합니다. 마찬가지로, 캡처 절 캡처 기본값을 포함 하는 경우 `=`, 없습니다 `capture` 해당 캡처 절의 형태가 될 수 `= identifier`합니다. 식별자 또는 `this`는 캡처 절에 두 번 이상 나타날 수 없습니다. 다음 코드 조각은 몇 가지 사례를 보여 줍니다.  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};      // OK  
    [&, &i]{};     // ERROR: i preceded by & when & is the default  
    [=, this]{};   // ERROR: this when = is the default  
    [=, *this]{ }; // OK: captures this by value. See below.
    [i, i]{};      // ERROR: i repeated  
}  
```  
  
 뒤에 줄임표가 캡처는 팩 확장은이 표시 된 것과 같이 [variadic 템플릿](../cpp/ellipses-and-variadic-templates.md) 예제:  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 본문이나 클래스 메서드에 람다 식을 사용하려면 캡처 절에 `this` 포인터를 전달하여 바깥쪽 클래스의 메서드 및 데이터 멤버에 대한 액세스 권한을 제공합니다. 
 
**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):는 `this` 지정 하 여 포인터 값으로 캡처할 수 있습니다 `*this` 캡처 절에 합니다. 값별로 캡처 즉 전체 *클로저*, 하는 익명 함수 개체는 encapulates 람다 식, 람다 식 호출 되는 모든 호출 사이트에 복사 됩니다. 캡처 값으로 람다는 특히 NUMA 같은 특정 하드웨어 아키텍처에서 병렬 또는 비동기 작업에서 실행 될 때 유용 합니다. 

클래스 메서드와 함께 람다 식을 사용 하는 방법을 보여 주는 예를 들어에 대 한 "예제:: 람다 식에는 메서드에 사용"의 참조 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)합니다.  
  
 캡처 절을 사용하는 경우 특히 람다를 다중 스레딩과 함께 사용할 때는 다음과 같은 사항에 유의해야 합니다.  
  
-   참조 캡처는 외부 변수를 수정하는 데 사용할 수 있지만 값 캡처는 사용할 수 없습니다 (`mutable`을 통해 복사본은 수정되지만 원본은 수정되지 않습니다.)  
  
-   참조 캡처는 외부 변수에 대한 업데이트를 반영하지만 값 캡처는 반영하지 않습니다.  
  
-   참조 캡처는 수명 종속성을 발생시키지만 값 캡처에는 수명 종속성이 없습니다. 이는 람다가 비동기적으로 실행되는 경우에 특히 중요합니다. 비동기 람다에서 참조를 기준으로 로컬을 캡처하는 경우 이 로컬은 람다가 실행될 때는 사라졌을 가능성이 매우 높으며, 결과적으로 런타임에 액세스 위반이 발생할 수 있습니다.  
  
### <a name="generalized-capture-c-14"></a>일반화된 캡처(C++ 14)  
  
 C++14에서는 해당 변수가 반드시 람다 함수의 바깥쪽 범위에 존재하지 않아도 캡처 절에 새 변수를 도입하고 초기화할 수 있습니다. 이러한 초기화는 임의의 식으로 표현할 수 있습니다. 새 변수의 형식은 식에서 생성되는 형식에서 추론됩니다. 이 기능의 이점 중 하나는, C++14에서 주변 범위에서 이동 전용 변수(예: std::unique_ptr)를 캡처하여 이를 람다에서 사용할 수 있다는 점입니다.  
  
```cpp  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### <a name="parameter-list"></a>매개 변수 목록  
 변수를 캡처하는 것 외에도, 람다는 입력 매개 변수를 사용할 수 있습니다. 매개 변수 목록 (*람다 선언 자* 표준 구문에서는)는 선택 사항이 며 대부분의 측면에서 함수에 대 한 매개 변수 목록와 유사 합니다.  
  
```cpp  
auto y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 **c + + 14**, 매개 변수 형식이 제네릭인 경우 형식 지정자로 auto 키워드를 사용할 수 있습니다. 이렇게 하면 함수 호출 연산자를 템플릿으로 만들도록 컴파일러에 지시합니다. 매개 변수 목록에 있는 각 auto 인스턴스는 고유한 형식 매개 변수와 같습니다.  
  
```cpp  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 람다 식은 다른 람다 식을 인수로 사용할 수 있습니다. 자세한 내용은 항목의 "고차 람다 식" 참조 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)합니다.  
  
 람다 식에 인수를 전달 하지 않으면 람다-선언에 없는 경우 빈 괄호를 생략할 수 매개 변수 목록은 선택 사항 이므로 *예외 사양이*,  *후행 반환 형식당*, 또는 `mutable`합니다.  
  
### <a name="mutable-specification"></a>변경 가능한 사양  
 일반적으로 람다 함수 호출 연산자는 값 단위 상수이지만 `mutable` 키워드를 사용할 경우 이를 취소합니다. 변경 가능 데이터 멤버가 생성되지 않습니다. 변경 가능한 사양을 사용하면 람다 식의 본문이 값별로 캡처되는 변수를 수정할 수 있습니다. 이 문서의 뒷부분에 나오는 몇 가지 예제는 `mutable` 키워드 사용 방법에 대해 설명합니다.  
  
### <a name="exception-specification"></a>예외 사양  
 람다 식이 어떠한 예외도 throw하지 않음을 나타내기 위해 `noexcept` 예외 사양을 사용할 수 있습니다. 일반 함수와 함께 Visual c + + 컴파일러는 경고를 생성 [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) 람다 식을 선언 하는 경우는 `noexcept` 예외 사양 및 람다 본문 다음과 같이 예외를 throw 합니다.  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() noexcept { throw 5; }();  
}  
```  
  
 자세한 내용은 참조 [예외 사양 (throw)](../cpp/exception-specifications-throw-cpp.md)합니다.  
  
### <a name="return-type"></a>반환 형식  
 람다 식의 반환 형식은 자동으로 추론됩니다. 사용할 필요가 없습니다는 [자동](../cpp/auto-cpp.md) 키워드를 지정 하지 않으면는 *후행 반환 형식당*합니다. *후행 반환 형식당* 일반 메서드 또는 함수의 반환 형식 부분 유사 합니다. 그러나 반환 형식은 매개 변수 목록 뒤에 와야 하며 반환 형식 앞에 trailing-return-type 키워드 `->`를 포함해야 합니다.  
  
 람다 본문에 return 문이 하나만 포함되거나 식이 값을 반환하지 않으면 람다 식의 반환 형식 부분을 생략할 수 있습니다. 람다 본문에 단일 return 문이 포함되어 있으면 컴파일러는 반환 식의 형식에서 반환 형식을 추론합니다. 그렇지 않으면 컴파일러는 반환 형식이 `void`인 것으로 추론합니다. 이 원칙을 설명하는 다음 예제 코드 조각을 참조하세요.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
```  
  
 람다 식은 다른 람다 식을 반환 값으로 생성할 수 있습니다. 자세한 내용은의 "고차 람다 식" 참조 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)합니다.  
  
### <a name="lambda-body"></a>람다 본문  
 람다 본문 (*복합 문* 표준 구문에서는)의 람다 식 수 있는 모든 포함 될는 일반 메서드 또는 함수 본문에 포함 될 수 있습니다. 일반 함수와 람다 식 모두의 본문은 다음과 같은 종류의 변수에 액세스할 수 있습니다.  
  
-   앞의 설명대로 바깥쪽 범위에서 캡처된 변수  
  
-   매개 변수  
  
-   로컬로 선언된 변수  
  
-   클래스 데이터 멤버(클래스 내부에서 선언되고 `this`가 캡처된 경우)  
  
-   정적 저장 기간이 있는 모든 변수(예: 전역 변수)  
  
 다음 예제에는 `n` 변수를 값별로 명시적으로 캡처하고 `m` 변수를 참조별로 암시적으로 캡처하는 람다 식이 포함되어 있습니다.  
  
```cpp  
// captures_lambda_expression.cpp  
// compile with: /W4 /EHsc   
#include <iostream>  
using namespace std;  
  
int main()  
{  
   int m = 0;  
   int n = 0;  
   [&, n] (int a) mutable { m = ++n + a; }(4);  
   cout << m << endl << n << endl;  
}  
```  
  
```Output  
5  
0  
```  
  
 `n` 변수는 값별로 캡처되므로 람다 식을 호출한 후 해당 값이 `0`으로 유지됩니다. `mutable` 사양을 사용하면 람다 내부에서 `n`을 수정할 수 있습니다.  
  
 람다 식은 자동 저장 기간이 있는 변수만 캡처할 수 있지만 람다 식의 본문에서는 정적 저장 기간이 있는 변수를 사용할 수 있습니다. 다음 예제는 `generate` 함수 및 람다 식을 사용하여 `vector` 개체의 각 요소에 값을 할당합니다. 람다 식은 정적 변수를 수정하여 다음 요소의 값을 생성합니다.  
  
```cpp  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });   
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
```  
  
 자세한 내용은 참조 [생성](../standard-library/algorithm-functions.md#generate)합니다.  
  
 다음 코드 예제에서는 이전 예제의 함수를 사용 하 고 c + + 표준 라이브러리 알고리즘을 사용 하는 람다 식의 예를 추가 `generate_n`합니다. 이 람다 식은 `vector` 개체의 요소를 이전의 두 요소의 합에 할당합니다. 람다 식의 본문이 외부 변수 `mutable` 및 `x`(람다 식이 값별로 캡처함)의 복사본을 수정할 수 있도록 `y` 키워드가 사용됩니다. 람다 식이 원래 변수 `x` 및 `y`를 값별로 캡처하기 때문에 람다가 실행된 후에도 값이 `1`로 유지됩니다.  
  
```cpp  
// compile with: /W4 /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });  
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
  
int main()  
{  
    // The number of elements in the vector.  
    const int elementCount = 9;  
  
    // Create a vector object with each element set to 1.  
    vector<int> v(elementCount, 1);  
  
    // These variables hold the previous two elements of the vector.  
    int x = 1;  
    int y = 1;  
  
    // Sets each element in the vector to the sum of the   
    // previous two elements.  
    generate_n(v.begin() + 2,  
        elementCount - 2,  
        [=]() mutable throw() -> int { // lambda is the 3rd parameter  
        // Generate current value.  
        int n = x + y;  
        // Update previous two values.  
        x = y;  
        y = n;  
        return n;  
    });  
    print("vector v after call to generate_n() with lambda: ", v);  
  
    // Print the local variables x and y.  
    // The values of x and y hold their initial values because   
    // they are captured by value.  
    cout << "x: " << x << " y: " << y << endl;  
  
    // Fill the vector with a sequence of numbers  
    fillVector(v);  
    print("vector v after 1st call to fillVector(): ", v);  
    // Fill the vector with the next sequence of numbers  
    fillVector(v);  
    print("vector v after 2nd call to fillVector(): ", v);  
}  
```  
  
```Output  
vector v after call to generate_n() with lambda: 1 1 2 3 5 8 13 21 34  
x: 1 y: 1  
vector v after 1st call to fillVector(): 1 2 3 4 5 6 7 8 9  
vector v after 2nd call to fillVector(): 10 11 12 13 14 15 16 17 18  
```  
  
 자세한 내용은 참조 [generate_n](../standard-library/algorithm-functions.md#generate_n)합니다.  

## <a name="constexpr-lambda-expressions"></a>constexpr 람다 식
**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 람다 식으로 선언할 수 있습니다 `constexpr` 상수 식에서 사용할 때 각 데이터 멤버의 초기화 한다는 캡처하거나 소개 상수 식 내에 허용 됩니다.  

```cpp
    int y = 32;
    auto answer = [y]() constexpr 
    {
        int x = 10;
        return y + x; 
    };

    constexpr int Increment(int n) 
    {
        return [n] { return n + 1; }();
    }

``` 
람다는 암시적으로 `constexpr` 결과의 요구 사항을 만족 하는 경우는 `constexpr` 함수:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
람다가 암시적 또는 명시적으로 경우 `constexpr`, 함수 포인터 간의 변환 생성 한 `constexpr` 함수:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 람다는 `ref class`, `ref struct`, `value class` 또는 `value struct` 등의 공용 언어 런타임(CLR)의 관리되는 엔터티에서 지원되지 않습니다.  
  
 와 같은 Microsoft 전용 한정자를 사용 하는 경우 [__declspec](../cpp/declspec.md), 람다 식에 삽입할 수 바로 뒤의 `parameter-declaration-clause`-예:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 람다에서의 한정자 지원 여부를 확인 하려면 참조에 대 한 문서는 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md) 설명서의 섹션입니다.  
  
 Visual Studio C + + 11 표준 람다 기능, 아니라 임의의 호출 규칙을 사용 하는 함수 포인터를 통해 변환 가능한 상태 비저장 람다를 지원 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C + + 표준 라이브러리에 함수 개체](../standard-library/function-objects-in-the-stl.md)   
 [함수 호출](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
