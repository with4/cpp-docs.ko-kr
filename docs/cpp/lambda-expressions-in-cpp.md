---
title: "C++의 람다 식 | Microsoft Docs"
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
  - "람다 식[C++]"
  - "람다 식[C++], 개요"
  - "람다 식[C++], 함수 개체와 비교"
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
caps.latest.revision: 36
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++의 람다 식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+11에서 람다 식\(종종 *람다*라고 함\)은 호출되었거나 인수로서 함수에 전달된 위치에서 바로 익명 함수 개체를 정의하는 편리한 방법입니다.  일반적으로 람다는 알고리즘이나 비동기 메서드에 전달되는 몇 줄의 코드를 캡슐화하는 데 사용됩니다.  이 문서에서는 람다가 무엇인지 정의하고 다른 프로그래밍 기법과 비교하고 그 장점을 설명하며 기본 예제를 제공합니다.  
  
## 람다 식의 부분  
 ISO C\+\+ 표준에서는 `std::sort()` 함수에 세 번째 인수로 전달되는 간단한 람다를 보여 줍니다.  
  
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
  
1.  *캡처 절*\(C\+\+ 사양에서는 *lambda\-introducer*라고도 함\)  
  
2.  *매개 변수 목록* 선택 사항입니다.  \(*lambda declarator*라고도 함\)  
  
3.  *mutable specification* 선택 사항입니다.  
  
4.  *exception\-specification* 선택 사항입니다.  
  
5.  *trailing\-return\-type* 선택 사항입니다.  
  
6.  *lambda body*\)  
  
### 캡처 절  
 람다는 새로운 변수를 본문에 도입할 수 있으며\(**C\+\+14**\) 바깥쪽 범위의 변수에 액세스하거나 *캡처*할 수도 있습니다.  람다는 캡처 절\(표준 구문에서는 *lambda\-introducer*\)로 시작됩니다. 캡처 절은 캡처되는 변수 및 캡처가 값이나 참조 중 어느 것을 기준으로 하는지를 지정합니다.  앰퍼샌드\(`&`\) 접두사가 있는 변수는 참조로 액세스되며 이 접두사가 없는 변수는 값으로 액세스됩니다.  
  
 빈 캡처 절인 `[ ]`는 람다 식의 본문이 바깥쪽 범위의 변수에 액세스하지 않음을 나타냅니다.  
  
 기본 캡처 모드\(표준 구문에서는 `capture-default`\)를 사용하여 람다에서 참조되는 외부 변수를 캡처하는 방법을 나타낼 수 있습니다. \[&\]는 참조하는 모든 변수가 참조를 기준으로 캡처된다는 것을 의미하고 \[\=\]는 값을 기준으로 캡처된다는 것을 의미합니다.  기본 캡처 모드를 사용하고 특정 변수에 대해서는 반대 모드를 지정할 수 있습니다.  예를 들어, 람다 본문이 외부 변수 `total`에 참조별로 액세스하고 외부 변수 `factor`에 값별로 액세스하는 경우 다음 캡처 절이 동일합니다.  
  
```cpp  
  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 `capture-default`를 사용할 때는 람다에 언급된 변수만 캡처됩니다.  
  
 캡처 절에 `capture-default` `&`가 포함된 경우 해당 캡처 절의 `identifier`에서 `capture`는 `& identifier` 형태가 될 수 없습니다.  마찬가지로, 캡처 절에 `capture-default` `=`가 포함된 경우 해당 캡처 절의 `capture`는 `= identifier` 형태가 될 수 없습니다.  식별자 또는 `this`는 캡처 절에 두 번 이상 나타날 수 없습니다.  다음 코드 조각은 몇 가지 사례를 보여 줍니다.  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};    // OK  
    [&, &i]{};   // ERROR: i preceded by & when & is the default  
    [=, this]{}; // ERROR: this when = is the default  
    [i, i]{};    // ERROR: i repeated  
}  
```  
  
 다음의 `capture`variadic 템플릿 예제에서와 같이, 줄임표 앞에 오는 [는 팩 확장입니다.](../cpp/ellipses-and-variadic-templates.md)  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 본문이나 클래스 메서드에 람다 식을 사용하려면 캡처 절에 `this` 포인터를 전달하여 바깥쪽 클래스의 메서드 및 데이터 멤버에 대한 액세스 권한을 제공합니다.  클래스 메서드와 함께 람다 식을 사용하는 방법을 보여 주는 예제는 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)의 "예제: 메서드에 람다 식 사용"을 참조하세요.  
  
 캡처 절을 사용하는 경우 특히 람다를 다중 스레딩과 함께 사용할 때는 다음과 같은 사항에 유의해야 합니다.  
  
-   참조 캡처는 외부 변수를 수정하는 데 사용할 수 있지만 값 캡처는 사용할 수 없습니다  \(`mutable`을 통해 복사본은 수정되지만 원본은 수정되지 않습니다.\)  
  
-   참조 캡처는 외부 변수에 대한 업데이트를 반영하지만 값 캡처는 반영하지 않습니다.  
  
-   참조 캡처는 수명 종속성을 발생시키지만 값 캡처에는 수명 종속성이 없습니다.  이는 람다가 비동기적으로 실행되는 경우에 특히 중요합니다.  비동기 람다에서 참조를 기준으로 로컬을 캡처하는 경우 이 로컬은 람다가 실행될 때는 사라졌을 가능성이 매우 높으며, 결과적으로 런타임에 액세스 위반이 발생할 수 있습니다.  
  
 **일반화된 캡처\(C\+\+ 14\)**  
  
 C\+\+14에서는 해당 변수가 반드시 람다 함수의 바깥쪽 범위에 존재하지 않아도 캡처 절에 새 변수를 도입하고 초기화할 수 있습니다.  이러한 초기화는 임의의 식으로 표현할 수 있습니다. 새 변수의 형식은 식에서 생성되는 형식에서 추론됩니다.  이 기능의 이점 중 하나는, C\+\+14에서 주변 범위에서 이동 전용 변수\(예: std::unique\_ptr\)를 캡처하여 이를 람다에서 사용할 수 있다는 점입니다.  
  
```  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### 매개 변수 목록  
 변수를 캡처하는 것 외에도, 람다는 입력 매개 변수를 사용할 수 있습니다.  매개 변수 목록\(표준 구문의 *lambda declarator*\)은 선택 사항이며 대부분의 측면에서 함수의 매개 변수 목록과 유사합니다.  
  
```  
int y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 **C\+\+ 14**에서 매개 변수 형식이 제네릭인 경우 형식 지정자로 auto 키워드를 사용할 수 있습니다.  이렇게 하면 함수 호출 연산자를 템플릿으로 만들도록 컴파일러에 지시합니다.  매개 변수 목록에 있는 각 auto 인스턴스는 고유한 형식 매개 변수와 같습니다.  
  
```  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 람다 식은 다른 람다 식을 인수로 사용할 수 있습니다.  자세한 내용은 [람다 식의 예](../cpp/examples-of-lambda-expressions.md) 항목의 "고차 람다 식"을 참조하세요.  
  
 매개 변수 목록은 선택 사항이므로 람다 식에 인수를 전달하지 않고 `lambda-declarator:`에 *exception\-specification*, *trailing\-return\-type* 또는 `mutable`이 포함되지 않는 경우 빈 괄호를 생략할 수 있습니다.  
  
### 변경 가능한 사양  
 일반적으로 람다 함수 호출 연산자는 값 단위 상수이지만 `mutable` 키워드를 사용할 경우 이를 취소합니다.  변경 가능 데이터 멤버가 생성되지 않습니다.  변경 가능한 사양을 사용하면 람다 식의 본문이 값별로 캡처되는 변수를 수정할 수 있습니다.  이 문서의 뒷부분에 나오는 몇 가지 예제는 `mutable` 키워드 사용 방법에 대해 설명합니다.  
  
### 예외 사양  
 람다 식이 어떠한 예외도 throw하지 않음을 나타내기 위해 `throw()` 예외 사양을 사용할 수 있습니다.  여기에서 볼 수 있는 것과 같이, 일반 함수와 마찬가지로 람다 식이 [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) 예외 사양을 선언하고 람다 본문이 예외를 throw하는 경우 Visual C\+\+ 컴파일러는 `throw()` 경고를 생성합니다.  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() throw() { throw 5; }();  
}  
```  
  
 자세한 내용은 [예외 사양\(throw\)](../cpp/exception-specifications-throw-cpp.md)을 참조하세요.  
  
### 반환 형식  
 람다 식의 반환 형식은 자동으로 추론됩니다.  *trailing\-return\-type*을 지정하지 않는 한 [auto](../cpp/auto-cpp.md) 키워드를 사용할 필요가 없습니다.  *trailing\-return\-type*은 일반 메서드 또는 함수의 반환 형식 부분과 유사합니다.  그러나 반환 형식은 매개 변수 목록 뒤에 와야 하며 반환 형식 앞에 trailing\-return\-type 키워드 `->`를 포함해야 합니다.  
  
 람다 본문에 return 문이 하나만 포함되거나 식이 값을 반환하지 않으면 람다 식의 반환 형식 부분을 생략할 수 있습니다.  람다 본문에 단일 return 문이 포함되어 있으면 컴파일러는 반환 식의 형식에서 반환 형식을 추론합니다.  그렇지 않으면 컴파일러는 반환 형식이 `void`인 것으로 추론합니다.  이 원칙을 설명하는 다음 예제 코드 조각을 참조하세요.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
  
```  
  
 람다 식은 다른 람다 식을 반환 값으로 생성할 수 있습니다.  자세한 내용은 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)의 "고차 람다 식"을 참조하세요.  
  
### 람다 본문  
 람다 식의 람다 본문\(표준 구문의 *compound\-statement*\)에는 일반 메서드 또는 함수 본문에 포함할 수 있는 모든 항목을 포함할 수 있습니다.  일반 함수와 람다 식 모두의 본문은 다음과 같은 종류의 변수에 액세스할 수 있습니다.  
  
-   앞의 설명대로 바깥쪽 범위에서 캡처된 변수  
  
-   매개 변수  
  
-   로컬로 선언된 변수  
  
-   클래스 데이터 멤버\(클래스 내부에서 선언되고 `this`가 캡처된 경우\)  
  
-   정적 저장 기간이 있는 모든 변수\(예: 전역 변수\)  
  
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
  
 **출력:**  
  
  **5**  
**0** `n` 변수는 값별로 캡처되므로 람다 식을 호출한 후 해당 값이 `0`으로 유지됩니다.  `mutable` 사양을 사용하면 람다 내부에서 `n`을 수정할 수 있습니다.  
  
 람다 식은 자동 저장 기간이 있는 변수만 캡처할 수 있지만 람다 식의 본문에서는 정적 저장 기간이 있는 변수를 사용할 수 있습니다.  다음 예제는 `generate` 함수 및 람다 식을 사용하여 `vector` 개체의 각 요소에 값을 할당합니다.  람다 식은 정적 변수를 수정하여 다음 요소의 값을 생성합니다.  
  
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
  
 자세한 내용은 [생성](../Topic/generate.md)를 참조하세요.  
  
 다음 코드 예제는 이전 예제의 함수를 사용하고 STL 알고리즘 `generate_n`을 사용하는 람다 식의 예제를 추가합니다.  이 람다 식은 `vector` 개체의 요소를 이전의 두 요소의 합에 할당합니다.  람다 식의 본문이 외부 변수 `mutable` 및 `x`\(람다 식이 값별로 캡처함\)의 복사본을 수정할 수 있도록 `y` 키워드가 사용됩니다.  람다 식이 원래 변수 `x` 및 `y`를 값별로 캡처하기 때문에 람다가 실행된 후에도 값이 `1`로 유지됩니다.  
  
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
  
 **출력:**  
  
  **vector v after call to generate\_n\(\) with lambda: 1 1 2 3 5 8 13 21 34**  
**x: 1 y: 1**  
**vector v after 1st call to fillVector\(\): 1 2 3 4 5 6 7 8 9**  
**vector v after 2nd call to fillVector\(\): 10 11 12 13 14 15 16 17 18** 자세한 내용은 [generate\_n](../Topic/generate_n.md)을 참조하세요.  
  
## Microsoft 전용  
 람다는 `ref class`, `ref struct`, `value class` 또는 `value struct` 등의 공용 언어 런타임\(CLR\)의 관리되는 엔터티에서 지원되지 않습니다.  
  
 [\_\_declspec](../cpp/declspec.md) 등의 Microsoft 전용 한정자를 사용할 경우 다음 예와 같이 람다 식에서 `parameter-declaration-clause` 직후에 삽입할 수 있습니다.  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
  
```  
  
 람다에서의 한정자 지원 여부를 확인하려면 설명서의 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md) 섹션에서 해당 문서를 참조하세요.  
  
 Visual Studio에서는 C\+\+11 표준 람다 식 구문 및 기능이 지원되지만 다음과 같은 예외 사항이 있습니다.  
  
-   람다는 다른 모든 클래스와 마찬가지로 이동 생성자 및 이동 할당 연산자를 자동으로 생성하지 않습니다.  rvalue 참조 동작 지원에 대한 자세한 내용은 [C\+\+11\/14\/17 기능에 대한 지원](../cpp/support-for-cpp11-14-17-features-modern-cpp.md)의 "Rvalue 참조" 섹션을 참조하세요.  
  
-   선택 항목인 *attribute\-specifier\-seq*가 이 버전에서 지원되지 않습니다.  
  
 Visual Studio에는 C\+\+11 표준 람다 기능 이외에 다음과 같은 기능이 있습니다.  
  
-   상태 비저장 람다를 통해 임의의 호출 규칙을 사용하는 함수 포인터로의 모든 변환이 가능합니다.  
  
-   모든 return 문의 형식이 같은 한 `{ return expression; }`보다 복잡한 람다 본문에 대해 반환 형식이 자동으로 추론됩니다.  이 기능은 제안된 C\+\+14 표준에 포함되어 있습니다.  
  
## 참고 항목  
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [STL의 함수 개체](../standard-library/function-objects-in-the-stl.md)   
 [함수 호출](../cpp/function-call-cpp.md)   
 [for\_each](../Topic/for_each.md)