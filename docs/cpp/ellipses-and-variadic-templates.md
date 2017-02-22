---
title: "Ellipses 및 Variadic 템플릿 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Ellipses 및 Variadic 템플릿
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 variadic C\+\+ 템플릿을 사용하여 줄임표\(`...`\)를 사용하는 방법을 보여 줍니다.  줄임표는 C 및 C\+\+에서 [여러 용도](../misc/ellipsis-dot-dot-dot.md)가 있습니다.    함수에 가변 인수 목록이 포함됩니다.  C 런타임 라이브러리에서 `printf()` 함수는 가장 잘 알려진 예 중 하나입니다.  
  
 *variadic 템플릿*은 임의의 인수 개수를 지원하는 클래스 또는 함수 템플릿입니다.  이 메커니즘은 클래스 템플릿과 함수 템플릿 모두에 적용할 수 있기 때문에 다양한 형식 안전성과 특수 기능 및 유연성을 제공하므로 C\+\+ 라이브러리 개발자들에게 특히 유용합니다.  
  
## 구문  
 줄임표는 variadic 템플릿에서 두 가지 방식으로 사용됩니다.  매개 변수 이름의 왼쪽은 *매개 변수 팩*을 나타내고 매개 변수 이름의 오른쪽은 매개 변수 팩을 별도 이름으로 확장합니다.  
  
 다음은 *variadic 템플릿 클래스* 정의 구문의 기본적인 예입니다.  
  
```cpp  
template<typename... Arguments> class classname;  
```  
  
 팩 매개 변수 및 확장, 다음 예에서 같이 사용자의 기본 설정에 따라 줄임표는 주위의 공백을 추가할 수 있습니다.  
  
```cpp  
template<typename ...Arguments> class classname;  
```  
  
 혹은 이것:  
  
```cpp  
template<typename ... Arguments> class classname;  
```  
  
 이 문서에서는 첫 번째 예제\(줄임표에 연결 된 `typename`\)에 표시 된 규칙 공지합니다.  
  
 위의 예제에서, `Arguments` 은 매개 변수 팩입니다.  클래스 `classname`은 이러한 예와 같이 인수의 변수 숫자를 적용할 수 있습니다.  
  
```cpp  
  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
vtclass<long, std::vector<int>, std::string> vtinstance4;  
  
```  
  
 variadic 템플릿 클래스 정의를 사용할 경우 하나 이상의 매개 변수가 필요할 수도 있습니다.  
  
```cpp  
template <typename First, typename... Rest> class classname;  
  
```  
  
 다음은 *variadic 템플릿 함수* 정의 구문의 기본적인 예입니다.  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments... args);  
```  
  
 `Arguments` 매개 변수 팩은 다음 단원 **variadic 템플릿 이해**에 나와 있는 대로 사용을 위해 확장됩니다.  
  
 Variadic 템플릿 함수 구문에는 다른 형식을 사용할 수 있습니다 즉, 이 예제에 포함되나 제한되지 않음:  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments&... args);   
template <typename... Arguments> returntype functionname(Arguments&&... args);  
template <typename... Arguments> returntype functionname(Arguments*... args);  
```  
  
 `const` 와 같은 지정자도 사용할 수 있습니다.  
  
```cpp  
template <typename... Arguments> returntype functionname(const Arguments&... args);  
  
```  
  
 Variadic 템플릿 클래스 정의와 마찬가지로 하나 이상의 매개 변수가 필요한 함수를 만들 수 있습니다.  
  
```cpp  
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);  
  
```  
  
 Variadic 템플릿에는 `sizeof...()` 연산자\(이전의 `sizeof()` 연산자와 관계 없음\)가 사용됩니다.  
  
```cpp  
template<typename... Arguments>  
void tfunc(const Arguments&... args)  
{  
    const unsigned numargs = sizeof...(Arguments);  
  
    X xobj[numargs]; // array of some previously defined type X  
  
    helper_func(xobj, args...);  
}  
  
```  
  
## 줄임표 \(...\) 위치에 대한 자세히 보입니다  
 이전에,이 문서는 "매개 변수 팩 매개 변수 이름의 가장 왼쪽에 의미 및 매개 변수 이름, 오른쪽에 별도 이름으로 매개 변수 팩 확장" 으로 매개 변수 팩과 확장을 정의 줄임표 위치를 설명했다.  이 기술적으로 하지만 코드 변환에 혼동 될 수 있습니다.  가정할 수 있습니다.  
  
-   템플릿 매개 변수 목록에서 \(`template <parameter-list>`\), `typename...` 템플릿 매개 변수 팩을 소개합니다.  
  
-   매개 변수 선언의 절에서 \(`func(parameter-list)`\), "최상위" 줄임표 함수 매개 변수 팩을 소개하고 줄임표 \(...\) 위치 하는 것이 중요 합니다.  
  
    ```cpp  
  
    // v1 is NOT a function parameter pack:  
    template <typename... Types> void func1(std::vector<Types...> v1);   
  
    // v2 IS a function parameter pack:  
    template <typename... Types> void func2(std::vector<Types>... v2);   
    ```  
  
-   매개 변수 이름 바로 뒤에 줄임표 표시된 매개 변수 팩 확장을 해야 합니다.  
  
## 예제  
 variadic 템플릿 함수 메커니즘을 보여주는 좋은 방법은 `printf`의 기능을 다시 작성하는 데 함수를 사용하는 것입니다  
  
```cpp  
#include <iostream>  
  
using namespace std;  
  
void print() {  
    cout << endl;  
}  
  
template <typename T> void print(const T& t) {  
    cout << t << endl;  
}  
  
template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {  
    cout << first << ", ";  
    print(rest...); // recursive call using pack expansion syntax  
}  
  
int main()  
{  
    print(); // calls first overload, outputting only a newline  
    print(1); // calls second overload  
  
    // these call the third overload, the variadic template,   
    // which uses recursion as needed.  
    print(10, 20);  
    print(100, 200, 300);  
    print("first", 2, "third", 3.14159);  
}  
  
```  
  
## Output  
  
```  
  
1  
10, 20  
100, 200, 300  
first, 2, third, 3.14159  
```  
  
> [!NOTE]
>  variadic 템플릿 함수를 통합하는 대부분의 구현은 일부 양식의 재귀를 사용하지만 전통적인 재귀와는 약간 다릅니다. 전통적인 재귀는 같은 서명을 사용하여 자신을 호출하는 함수를 포함합니다. \(오버로드하거나 템플릿화할 수 있지만 매번 동일한 시그너처가 선택됩니다.\) Variadic 재귀에는 다른 수의 인수\(거의 항상 줄어듦\)를 사용하여 variadic 함수 템플릿을 호출하는 작업이 포함되므로 매번 다른 서명을 사용하지 않게 됩니다.  "기본 사례"는 여전히 필요하지만 재귀적 특성은 다릅니다.  
  
## 참고 항목  
 [줄임표\(...\)](../misc/ellipsis-dot-dot-dot.md)