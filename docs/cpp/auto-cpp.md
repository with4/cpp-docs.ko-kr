---
title: "auto(C++ | Microsoft Docs"
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
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
caps.latest.revision: 18
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto(C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

초기화 식에서 선언된 변수의 형식을 추론합니다.  
  
## 구문  
  
```  
auto declarator initializer;  
```  
  
```  
[](auto param1, auto param2) {};  
```  
  
## 설명  
 `auto` 키워드는 선언된 변수 또는 람다 식 매개 변수의 초기화 식을 사용하여 해당 형식을 추론하도록 컴파일러에 지시합니다.  
  
 `auto` 키워드는 다음과 같은 이점을 제공하므로 꼭 변환이 필요한 경우가 아니라면 대부분의 경우에 사용할 것을 추천합니다.  
  
-   **강력함:** 함수의 반환 형식이 변경할 때 포함되므로 식의 형식이 변경되는 경우에도 작동합니다.  
  
-   **성능:** 변환되지 않도록 보장할 수 있습니다.  
  
-   **유용성:** 형식 이름 맞춤법 문제 및 오타를 걱정할 필요가 없습니다.  
  
-   **효율성:** 코딩의 효율성이 향상됩니다.  
  
 `auto`를 사용하지 않는 변환의 경우:  
  
-   특정 형식을 원하는 경우 다른 항목은 사용할 수 없습니다.  
  
-   식 템플릿 도우미 형식\(예: `(valarray+valarray)` 및 이니셜라이저 목록\)은 드물게 `auto x = { 1 };`를 사용하여 `int`를 얻고자 할 때 거의 선택하지 않습니다.  
  
 `auto` 키워드를 사용하려면 형식 대신 이 키워드를 사용하여 변수를 선언하고 초기화 식을 지정합니다.  또한 지정자 및 선언자\(`auto`, `const`\), 포인터\(`volatile`\), 참조\(`*`\), 및 rvalue 참조\(`&`\)를 사용하여 `(&&` 키워드를 수정할 수 있습니다.  컴파일러는 초기화 식을 계산하고 해당 정보를 사용하여 변수의 형식을 추론합니다.  
  
 초기화 식은 할당\(등호 구문\), 직접 초기화\(함수\-스타일 구문\), [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) 식이 될 수 있거나 초기화 식은 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md) 문의 *for\-range\-declaration* 매개 변수가 될 수 있습니다.  자세한 내용은 [이니셜라이저](../cpp/initializers.md) 및 이 문서의 뒷부분에 있는 코드 예제를 참조하세요.  
  
 `auto` 키워드는 형식 그 자체가 아니라 형식을 위한 자리 표시자입니다.  따라서 `auto` 키워드는 캐스트 또는 [sizeof](../cpp/sizeof-operator.md) 및 [typeid](../windows/typeid-cpp-component-extensions.md)와 같은 연산자에 사용할 수 없습니다.  
  
## 유용성  
 `auto` 키워드는 복잡한 형식의 변수를 선언하는 간단한 방법입니다.  예를 들어 `auto`를 사용하여 초기화 식이 템플릿, 함수에 대한 포인터 또는 멤버에 대한 포인터와 관련된 변수를 선언할 수 있습니다.  
  
 `auto`를 사용하여 변수를 람다 식으로 선언 및 초기화할 수 있습니다.  람다 식의 형식은 컴파일러에만 알려져 있기 때문에 직접 변수 유형을 선언할 수 없습니다.  자세한 내용은 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)를 참조하세요.  
  
## 후행 반환 형식  
 `auto`를 `decltype` 형식 지정자와 함께 사용하여 템플릿 라이브러리를 작성할 수 있습니다.  반환 형식이 해당 템플릿 인수의 형식에 종속되는 템플릿 함수를 선언하려면 `auto` 및 `decltype`을 사용하세요.  또는 다른 함수에 대한 호출을 래핑한 후 다른 함수의 반환 형식을 반환하는 템플릿 함수를 선언하려면 `auto` 및 `decltype`을 사용합니다.  자세한 내용은 [decltype](../cpp/decltype-cpp.md)를 참조하세요.  
  
## 참조 및 cv 한정자  
 `auto`를 사용하면 참조, const 한정자 및 volatile 한정자가 삭제됩니다.  다음 예제를 참조하세요.  
  
```cpp  
// cl.exe /analyze /EHsc /W4  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
    int count = 10;  
    int& countRef = count;  
    auto myAuto = countRef;  
  
    countRef = 11;  
    cout << count << " ";  
  
    myAuto = 12;  
    cout << count << endl;  
}  
  
```  
  
 myAuto가 int 참조인 것 같지만 그렇지 않습니다.  단순한 int이므로 참조가 `11 11` 에 의해 삭제되지 않는 것처럼 `11 12` 가 아니라 `auto`을 출력합니다.  
  
## 제한 사항 및 오류 메시지  
 다음 표에서는 `auto` 키워드 사용에 대한 제한 및 컴파일러에서 내보내는 해당 진단 오류 메시지를 보여 줍니다.  
  
|오류 번호|설명|  
|-----------|--------|  
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|`auto` 키워드는 다른 형식 지정자와 함께 사용할 수 없습니다.|  
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|`auto` 키워드를 사용하여 선언된 기호에는 이니셜라이저가 있어야 합니다.|  
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|`auto` 키워드를 잘못 사용하여 형식을 선언했습니다.  예를 들어 메서드 반환 형식 또는 배열을 선언했습니다.|  
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|매개 변수 또는 템플릿 인수는 `auto` 키워드를 사용하여 선언할 수 없습니다.|  
|[C3534](../Topic/Compiler%20Error%20C3534.md)|`new` 식에서 `auto` 키워드를 사용하여 선언된 기호에는 이니셜라이저가 있어야 합니다.  자세한 내용은 [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)를 참조하세요.|  
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|메서드 또는 템플릿 매개 변수는 `auto` 키워드를 사용하여 선언할 수 없습니다.|  
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|초기화되기 전에 기호를 사용할 수 없습니다.  실제로, 이는 변수를 사용하여 자신을 초기화할 수 없음을 의미합니다.|  
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|`auto` 키워드를 사용하여 선언된 형식으로 캐스팅할 수 없습니다.|  
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|`auto` 키워드를 사용하여 선언된 선언자 목록의 모든 기호는 동일한 형식으로 확인되어야 합니다.  자세한 내용은 [선언](../misc/declarations.md)을 참조하세요.|  
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|`auto` 키워드를 사용하여 선언된 기호에 [sizeof](../cpp/sizeof-operator.md) 및 [typeid](../windows/typeid-cpp-component-extensions.md) 연산자를 적용할 수 없습니다.|  
  
## 예  
 코드 조각은 `auto` 키워드를 사용할 수 있는 몇 가지 방법을 설명합니다.  
  
 다음 선언은 동일합니다.  첫 번째 문에서는 `j` 변수가 `int` 형식으로 선언되었습니다.  두 번째 문에는 초기화 식\(0\)이 정수이므로 `k` 변수가 `int` 형식으로 추론되었습니다.  
  
```cpp  
  
int j = 0;  // Variable j is explicitly type int.  
auto k = 0; // Variable k is implicitly type int because 0 is an integer.  
```  
  
 다음 선언은 동일하지만 두 번째 선언이 첫 번째 선언보다 간단합니다.  `auto` 키워드를 사용하는 가장 중요한 이유 중 하나는 단순성입니다.  
  
```cpp  
  
map<int,list<string>>::iterator i = m.begin();   
auto i = m.begin();   
```  
  
 다음 코드 조각은 `iter` 및 범위 `elem` 루프가 시작될 때 `for` 및 `for` 형식의 변수를 선언합니다.  
  
```cpp  
  
// cl /EHsc /nologo /W4  
#include <deque>  
using namespace std;  
  
int main()  
{  
    deque<double> dqDoubleData(10, 0.1);  
  
    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)  
    { /* ... */ }  
  
    // prefer range-for loops with the following information in mind  
    // (this applies to any range-for with auto, not just deque)  
  
    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples  
    { /* ... */ }  
  
    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE  
    { /* ... */ }  
  
    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE  
    { /* ... */ }  
}  
  
```  
  
 다음 코드 조각에서는 `new` 연산자 및 포인터 선언을 사용하여 포인터를 선언합니다.  
  
```cpp  
  
double x = 12.34;  
auto *y = new auto(x), **z = new auto(&x);  
```  
  
 다음 코드 조각은 각 선언문에서 여러 기호를 선언합니다.  각 명령문의 모든 기호는 동일한 형식으로 확인됩니다.  
  
```cpp  
  
auto x = 1, *y = &x, **z = &y; // Resolves to int.  
auto a(2.01), *b (&a);         // Resolves to double.  
auto c = 'a', *d(&c);          // Resolves to char.  
auto m = 1, &n = m;            // Resolves to int.  
```  
  
 다음 코드 조각은 조건부 연산자\(`?:`\)를 사용하여 변수 `x`를 정수 값을 200 값을 갖는 정수로 선언합니다.  
  
```cpp  
  
int v1 = 100, v2 = 200;  
auto x = v1 > v2 ? v1 : v2;  
```  
  
 다음 코드 조각에서는 `x` 변수를 `int` 형식으로 초기화하고, `y` 변수를 `const` `int` 형식에 대한 참조로 초기화하고, `fp` 변수를 `int` 형식을 반환하는 함수에 대한 포인터로 초기화합니다.  
  
```cpp  
  
int f(int x) { return x; }  
int main()  
{  
    auto x = f(0);  
    const auto & y = f(1);  
    int (*p)(int x);  
    p = f;  
    auto fp = p;  
    //...  
}  
  
```  
  
## 참고 항목  
 [auto 키워드](../cpp/auto-keyword.md)   
 [\(NOTINBUILD\)Storage\-Class Specifiers](http://msdn.microsoft.com/ko-kr/10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [\/Zc:auto\(변수 형식 추론\)](../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 연산자](../cpp/sizeof-operator.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)   
 [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)   
 [선언](../misc/declarations.md)   
 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)   
 [이니셜라이저](../cpp/initializers.md)   
 [decltype](../cpp/decltype-cpp.md)