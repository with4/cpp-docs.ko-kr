---
title: decltype (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: decltype_cpp
dev_langs: C++
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 472b09b268fe9f493a4df025950a3565fd6c944c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="decltype--c"></a>decltype (c + +)
`decltype` 형식 지정자는 지정된 식의 형식을 생성합니다. `decltype` 형식 지정자와 함께 [auto 키워드](../cpp/auto-cpp.md), 템플릿 라이브러리를 작성 하는 개발자에 게 주로 유용 합니다. 반환 형식이 해당 템플릿 인수의 형식에 종속되는 템플릿 함수를 선언하려면 `auto` 및 `decltype`을 사용하세요. 또는 다른 함수에 대한 호출을 래핑한 다음 래핑된 함수의 반환 형식을 반환하는 템플릿 함수를 선언하려면 `auto` 및 `decltype`을 사용하세요.  
  
## <a name="syntax"></a>구문  
  
```  
decltype( expression )  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`expression`|식입니다. 자세한 내용은 참조 [식](../cpp/expressions-cpp.md)합니다.|  
  
## <a name="return-value"></a>반환 값  
 `expression` 매개 변수의 형식입니다.  
  
## <a name="remarks"></a>설명  
 `decltype` 형식 지정자는 Visual C++ 2010 이상 버전에서 지원되고 네이티브 코드 또는 관리 코드에 사용할 수 있습니다. `decltype(auto)`(C++14)는 Visual Studio 2015 이상에서 지원됩니다.  
  
 컴파일러는 다음 규칙을 사용하여 `expression` 매개 변수의 형식을 결정합니다.  
  
-   경우는 `expression` 매개 변수는 식별자 또는 [클래스 멤버 액세스](../cpp/member-access-operators-dot-and.md), `decltype(expression)` 로 명명 된 엔터티 형식이 `expression`합니다. 그러한 엔터티가 없거나 `expression` 매개 변수가 오버로드된 함수 집합에 이름을 지정하는 경우에는 컴파일러가 오류 메시지를 생성합니다.  
  
-   경우는 `expression` 매개 변수는 함수 또는 오버 로드 된 연산자 함수에 대 한 호출 `decltype(expression)` 함수의 반환 형식입니다. 오버로드된 연산자를 묶는 괄호는 무시됩니다.  
  
-   경우는 `expression` 매개 변수는 한 [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` 유형의 `expression`합니다. 경우는 `expression` 매개 변수는는 [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` 는 [lvalue 참조](../cpp/lvalue-reference-declarator-amp.md) 유형과 `expression`합니다.  
  
 다음 코드 예제에서는 `decltype` 형식 지정자의 용례를 보여 줍니다. 먼저 다음 문을 코딩한 것으로 가정합니다.  
  
```cpp  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 다음으로 아래 표에서 4개의 `decltype` 문에 의해 반환되는 형식을 검토합니다.  
  
|문|형식|참고|  
|---------------|----------|-----------|  
|`decltype(fx());`|`const int&&`|[rvalue 참조](../cpp/rvalue-reference-declarator-amp-amp.md) 에 `const int`합니다.|  
|`decltype(var);`|`int`|`var` 변수의 형식입니다.|  
|`decltype(a->x);`|`double`|멤버 액세스의 형식입니다.|  
|`decltype((a->x));`|`const double&`|내부 괄호를 사용하면 문이 멤버 액세스가 아니라 식으로 평가됩니다. `a`가 `const` 포인터로 선언되므로 형식은 `const double`에 대한 참조입니다.|  
  
## <a name="decltype-and-auto"></a>Decltype 및 Auto  
 C + + 14에서는 사용할 수 있습니다 `decltype(auto)` 해당 반환 형식이 템플릿 함수를 선언 하려면 후행 반환 형식이 없는 해당 템플릿 인수의 형식에 따라 다릅니다.  
  
 C++11에서는 `auto` 키워드와 함께 후행 반환 형식에 대한 `decltype` 형식 지정자를 사용하여 반환 형식이 해당 템플릿 인수의 형식에 종속되는 템플릿 함수를 선언할 수 있습니다. 예를 들어, 템플릿 함수의 반환 형식이 템플릿 인수의 형식에 종속되는 것을 보여 주는 다음 코드 예제를 살펴보세요. 코드 예제에서는 *알 수 없는* 자리 표시자는 반환 형식을 지정할 수 없음을 나타냅니다.  
  
```cpp  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 개발자는 `decltype` 형식 지정자를 통해 템플릿 함수가 반환하는 식의 형식을 가져올 수 있습니다. 사용 하 여는 *대체 함수 선언 구문* 나중 표시 된는 `auto` 키워드를 및 `decltype` 형식 지정자를 선언 하는 *런타임에 지정 된* 형식을 반환 합니다. 컴파일하면 지정되는 반환 형식은 코딩 시가 아니라 선언이 컴파일될 때 결정됩니다.  
  
 다음 프로토타입에서는 대체 함수 선언의 구문을 보여 줍니다. `const` 및 `volatile` 한정자 및 `throw` [예외 사양이](../cpp/exception-specifications-throw-cpp.md) 는 선택 사항입니다. *function_body* 자리 표시자 함수에서 수행 하는 작업을 지정 하는 복합 문을 나타냅니다. 모범 코딩 사례는 *식* 에서 자리 표시자는 `decltype` 문의 하 여 지정 된 식이 일치 해야는 `return` 문, 있는 경우에 *function_body*합니다.  
  
 **자동** *function_name* **(** *매개 변수*<sub>opt</sub> **)**  **const**<sub>opt</sub> **휘발성**<sub>opt</sub>  **->**  **decltype (** *식* **)** **throw**<sub>opt</sub> **{** *function_body* **};**  
  
 다음 코드 예제에서는 `myFunc` 템플릿 함수의 컴파일하면 지정되는 반환 형식이 `t` 및 `u` 템플릿 인수의 형식에 따라 결정됩니다. 모범 코딩 사례, 코드 예제에서는 또한 사용 하 여 rvalue 참조 및 `forward` 지원 함수 템플릿을 *완벽 전달*합니다. 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  
```cpp  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## <a name="decltype-and-forwarding-functions-c11"></a>Decltype 및 전달 함수(C++11)  
 전달 함수는 다른 함수에 대한 호출을 래핑합니다. 해당 인수 또는 이러한 인수를 포함하는 식의 결과를 다른 함수로 전달하는 함수 템플릿을 고려해 보세요. 또한 전달 함수는 다른 함수를 호출한 결과를 반환합니다. 이 시나리오에서 전달 함수의 반환 형식은 래핑된 함수의 반환 형식과 동일해야 합니다.  
  
 이 시나리오에서는 `decltype` 형식 지정자 없이 적절한 형식 식을 쓸 수 없습니다. `decltype` 형식 지정자는 함수가 참조 형식을 반환하는지 여부에 대한 필수 정보를 잃지 않기 때문에 제네릭 전달 함수를 사용할 수 있게 만듭니다. 전달 함수의 코드 예제는 이전 `myFunc` 템플릿 함수 예제를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 템플릿 함수 `Plus()`의 컴파일하면 지정되는 반환 형식을 선언합니다. `Plus` 함수는 해당 두 피연산자를 `operator+` 오버로드로 처리합니다. 따라서 `Plus` 함수의 반환 형식 및 더하기 연산자(+)에 대한 해석은 함수 인수의 형식에 따라 달라집니다.  
  
```cpp  
// decltype_1.cpp  
// compile with: cl /EHsc decltype_1.cpp  
  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
```Output  
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```
  
## <a name="example"></a>예제
**Visual Studio 2017 이상:** 컴파일러 템플릿을 선언 되지 않고 인스턴스화할 때 decltype 인수를 구문 분석 합니다. 따라서 decltype 인수에 독립적 특수화가 있는 경우 이 특수화는 인스턴스화 시점으로 연기되지 않고 즉시 처리되며 결과 오류가 이 시점에 진단됩니다.

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

## <a name="requirements"></a>요구 사항  
 Visual C++ 2010 이상 버전  
  
 `decltype(auto)`Visual Studio 2015 이상이 필요합니다.  
  
