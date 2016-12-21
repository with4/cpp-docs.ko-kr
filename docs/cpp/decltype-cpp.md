---
title: "decltype (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "decltype"
  - "decltype_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decltype 연산자"
  - "연산자[C++], decltype"
  - "연산자[C++], deduce 식 형식"
  - "연산자[C++], 식 형식"
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# decltype (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`decltype` 형식 지정자는 지정된 식의 형식을 생성합니다.  `decltype` 형식 지정자는 [auto 키워드](../cpp/auto-cpp.md)와 함께 템플릿 라이브러리를 작성하는 개발자에게 주로 유용합니다.  반환 형식이 해당 템플릿 인수의 형식에 종속되는 템플릿 함수를 선언하려면 `auto` 및 `decltype`을 사용하세요.  또는 다른 함수에 대한 호출을 래핑한 다음 래핑된 함수의 반환 형식을 반환하는 템플릿 함수를 선언하려면 `auto` 및 `decltype`을 사용하세요.  
  
## 구문  
  
```  
decltype( expression )  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`expression`|식입니다.  자세한 내용은 [식](../cpp/expressions-cpp.md)을 참조하세요.|  
  
## 반환 값  
 `expression` 매개 변수의 형식입니다.  
  
## 설명  
 `decltype` 형식 지정자는 Visual C\+\+ 2010 이상 버전에서 지원되고 네이티브 코드 또는 관리 코드에 사용할 수 있습니다.  `decltype(auto)`\(C\+\+14\)는 Visual Studio 2015 이상에서 지원됩니다.  
  
 컴파일러는 다음 규칙을 사용하여 `expression` 매개 변수의 형식을 결정합니다.  
  
-   `expression` 매개 변수가 식별자 또는 [클래스 멤버 액세스](../cpp/member-access-operators-dot-and.md)인 경우 `decltype(``expression``)`은 `expression`에 의해 이름이 지정된 엔터티의 형식입니다.  그러한 엔터티가 없거나 `expression` 매개 변수가 오버로드된 함수 집합에 이름을 지정하는 경우에는 컴파일러가 오류 메시지를 생성합니다.  
  
-   `expression` 매개 변수가 함수 또는 오버로드된 연산자 함수에 대한 호출인 경우 `decltype(``expression``)`은 함수의 반환 형식입니다.  오버로드된 연산자를 묶는 괄호는 무시됩니다.  
  
-   `expression` 매개 변수가 [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)인 경우 `decltype(``expression``)`은 `expression`의 형식입니다.  `expression` 매개 변수가 [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)인 경우에는 `decltype(``expression``)`이 [lvalue 참조](../cpp/lvalue-reference-declarator-amp.md) 형식에 대한 `expression` 입니다.  
  
 다음 코드 예제에서는 `decltype` 형식 지정자의 용례를 보여 줍니다.  먼저 다음 문을 코딩한 것으로 가정합니다.  
  
```  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 다음으로 아래 표에서 4개의 `decltype` 문에 의해 반환되는 형식을 검토합니다.  
  
|문|형식|메모|  
|-------|--------|--------|  
|`decltype(fx());`|`const int&&`|[rvalue 참조](../cpp/rvalue-reference-declarator-amp-amp.md) 에 대한 `const int` 입니다.|  
|`decltype(var);`|`int`|`var` 변수의 형식입니다.|  
|`decltype(a->x);`|`double`|멤버 액세스의 형식입니다.|  
|`decltype((a->x));`|`const double&`|내부 괄호를 사용하면 문이 멤버 액세스가 아니라 식으로 평가됩니다.  `a`가 `const` 포인터로 선언되므로 형식은 `const double`에 대한 참조입니다.|  
  
## Decltype 및 Auto  
 C\+\+14에서는 후행 반환 형식 없는 `decltype(auto)`를 사용하여 반환 형식이 해당 템플릿 인수의 형식에 종속되는 템플릿 함수를 선언할 수 있습니다.  
  
 C\+\+11에서는 `auto` 키워드와 함께 후행 반환 형식에 대한 `decltype` 형식 지정자를 사용하여 반환 형식이 해당 템플릿 인수의 형식에 종속되는 템플릿 함수를 선언할 수 있습니다.  예를 들어, 템플릿 함수의 반환 형식이 템플릿 인수의 형식에 종속되는 것을 보여 주는 다음 코드 예제를 살펴보세요.  코드 예제에서 *UNKNOWN* 자리 표시자는 반환 형식을 지정할 수 없음을 나타냅니다.  
  
```  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 개발자는 `decltype` 형식 지정자를 통해 템플릿 함수가 반환하는 식의 형식을 가져올 수 있습니다.  *컴파일하면 지정되는* 반환 형식을 선언하려면 나중에 살펴볼 `auto`대체 함수 선언 구문, `decltype` 키워드 및  *형식 지정자를 사용하세요.* 컴파일하면 지정되는 반환 형식은 코딩 시가 아니라 선언이 컴파일될 때 결정됩니다.  
  
 다음 프로토타입에서는 대체 함수 선언의 구문을 보여 줍니다.  `const` 및 `volatile` 한정자와 `throw` [예외 사양](../cpp/exception-specifications-throw-cpp.md)은 선택 사항입니다.  *function\_body* 자리 표시자는 함수가 수행하는 작업을 지정하는 복합 문을 나타냅니다.  모범 코딩 사례는 `decltype` 문의 *expression* 자리 표시자를 *function\_body*의 `return` 문\(있는 경우\)에 의해 지정된 식과 일치시키는 것입니다.  
  
 `auto` *function\_name*`(`*parameters*opt`)` `const`opt `volatile`opt `−>` `decltype(`*expression*`)` `throw`opt `{`*function\_body*`};`  
  
 다음 코드 예제에서는 `myFunc` 템플릿 함수의 컴파일하면 지정되는 반환 형식이 `t` 및 `u` 템플릿 인수의 형식에 따라 결정됩니다.  모범 코딩 사례에 따라 코드 예제는 rvalue 참조 및 `forward` 함수 템플릿\(*완전 전달* 지원\)도 사용합니다.  자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  
```  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## Decltype 및 전달 함수\(C\+\+11\)  
 전달 함수는 다른 함수에 대한 호출을 래핑합니다.  해당 인수 또는 이러한 인수를 포함하는 식의 결과를 다른 함수로 전달하는 함수 템플릿을 고려해 보세요.  또한 전달 함수는 다른 함수를 호출한 결과를 반환합니다.  이 시나리오에서 전달 함수의 반환 형식은 래핑된 함수의 반환 형식과 동일해야 합니다.  
  
 이 시나리오에서는 `decltype` 형식 지정자 없이 적절한 형식 식을 쓸 수 없습니다.  `decltype` 형식 지정자는 함수가 참조 형식을 반환하는지 여부에 대한 필수 정보를 잃지 않기 때문에 제네릭 전달 함수를 사용할 수 있게 만듭니다.  전달 함수의 코드 예제는 이전 `myFunc` 템플릿 함수 예제를 참조하세요.  
  
## 예제  
 다음 코드 예제는 템플릿 함수 `Plus()`의 컴파일하면 지정되는 반환 형식을 선언합니다.  `Plus` 함수는 해당 두 피연산자를 `operator+` 오버로드로 처리합니다.  따라서 `Plus` 함수의 반환 형식 및 더하기 연산자\(\+\)에 대한 해석은 함수 인수의 형식에 따라 달라집니다.  
  
```  
// decltype_1.cpp  
// compile with: /EHsc  
//  
#include "stdafx.h"  
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
  
 **출력**  
  
 이 코드 예제는 다음 결과를 생성합니다.  
  
 13  
  
 13.5  
  
 Hello, world\!  
  
 42  
  
## 요구 사항  
 Visual C\+\+ 2010 이상 버전  
  
 decltype\(auto\)에는 Visual Studio 2015 이상이 필요함  
  
## 참고 항목  
 [\(NOTINBUILD\)Simple Type Names](http://msdn.microsoft.com/ko-kr/333f45cb-2c72-4d81-8e59-e346b05f55e3)