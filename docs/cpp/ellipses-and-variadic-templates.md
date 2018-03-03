---
title: "Ellipses 및 Variadic 템플릿 | Microsoft Docs"
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
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6d3d0fa1dc4e2e4d817280fa83b26c56732cb2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ellipses-and-variadic-templates"></a>Ellipses 및 Variadic 템플릿
이 문서에서는 가변 매개 변수를 사용 하는 방법을 보여 줍니다 (`...`) c + + variadic 템플릿으로 합니다. 줄임표는 C 및 c + +에서 다양 한 용도로 되었습니다. 여기에 함수에 대 한 가변 인수 목록을 포함 합니다. `printf()` C 런타임 라이브러리에서 함수는 잘 알려진 예 중 하나입니다.  
  
 A *variadic 템플릿* 는 임의 개수의 인수를 지 원하는 클래스 또는 함수 템플릿입니다. 이 메커니즘은 클래스 템플릿 및 함수 템플릿 모두에 적용 하 고 형식이 안전 하 고 특정 기능과 유연성을 제공 함으로써 수 있으므로 c + + 라이브러리 개발자에 게 특히 유용 합니다.  
  
## <a name="syntax"></a>구문  
 줄임표는 variadic 템플릿에서 두 가지 방법으로 사용 됩니다. 매개 변수 이름의 왼쪽에 의미는 *매개 변수 팩*, 및 매개 변수 이름 오른쪽으로 확장 되는 매개 변수 팩을 별도 이름입니다.  
  
 다음은의 기본 예제 *variadic 템플릿 클래스* 정의 구문:  
  
```cpp  
template<typename... Arguments> class classname;  
```  
  
 팩 및 확장 매개 변수의 경우 다음 예에서 같이 기본 설정에 따라 줄임표 주위에 공백을 추가할 수 있습니다.  
  
```cpp  
template<typename ...Arguments> class classname;  
```  
  
 또는  
  
```cpp  
template<typename ... Arguments> class classname;  
```  
  
 이 문서에서는 첫 번째 예제에 표시된 규칙(줄임표가 `typename`에 연결)을 사용합니다.  
  
 위의 예제에서 `Arguments`는 매개 변수 팩입니다. 클래스 `classname` 다음이 예와 같이 인수의 변수 수를 사용할 수 있습니다.  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
vtclass<long, std::vector<int>, std::string> vtinstance4;  
  
```  
  
 Variadic 템플릿 클래스 정의 사용 하 여 매개 변수가 하나 이상 필요할 수도 있습니다.  
  
```cpp  
template <typename First, typename... Rest> class classname;  
  
```  
  
 다음은의 기본 예제 *variadic 템플릿 함수* 구문:  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments... args);  
```  
  
 `Arguments` 매개 변수 팩을 사용 하기 위해 확장 한 다음 다음 섹션에 나와 있는 것 처럼 **variadic 템플릿 이해**합니다.  
  
 다른 형태의 variadic 템플릿 함수 구문은 가능한-를 포함 하지만에 제한 되지 이러한 예제:  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments&... args);   
template <typename... Arguments> returntype functionname(Arguments&&... args);  
template <typename... Arguments> returntype functionname(Arguments*... args);  
```  
  
 와 같은 지정자 `const` 허용 됩니다.  
  
```cpp  
template <typename... Arguments> returntype functionname(const Arguments&... args);  
  
```  
  
 Variadic 템플릿 클래스 정의 하나 이상의 매개 변수를 필요한 함수를 만들 수 있습니다.  
  
```cpp  
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);  
  
```  
  
 Variadic 템플릿 사용는 `sizeof...()` 연산자 (이전에 관련 되지 않은 `sizeof()` 연산자):  
  
```cpp  
template<typename... Arguments>  
void tfunc(const Arguments&... args)  
{  
    constexpr auto numargs{ sizeof...(Arguments) };  
  
    X xobj[numargs]; // array of some previously defined type X  
  
    helper_func(xobj, args...);  
}  
  
```  
  
## <a name="more-about-ellipsis-placement"></a>줄임표 배치에 대한 자세한 내용  
 이 문서의 앞 부분에서 "매개 변수 이름의 왼쪽은 매개 변수 팩을 나타내고 매개 변수 이름 오른쪽은 매개 변수 팩을 별도의 이름으로 확장"한다고 매개 변수 팩과 확장을 정의하는 줄임표 배치에 대해 설명했습니다. 이는 기술적으로는 맞지만 코드로 변환할 때 혼동될 수 있습니다. 고려 사항:  
  
-   템플릿 매개 변수 목록에서 (`template <parameter-list>`), `typename...` 템플릿 매개 변수 팩을 소개 합니다.  
  
-   매개 변수 선언 절에 (`func(parameter-list)`), "최상위" 줄임표 함수 매개 변수 팩을 소개 하 고 줄임표 배치 하는 것이 중요 합니다.  
  
    ```cpp  
    // v1 is NOT a function parameter pack:  
    template <typename... Types> void func1(std::vector<Types...> v1);   
  
    // v2 IS a function parameter pack:  
    template <typename... Types> void func2(std::vector<Types>... v2);   
    ```  
  
-   매개 변수 이름 바로 뒤에 줄임표가 표시된 경우 매개 변수 팩 확장이 있는 것입니다.  
  
## <a name="example"></a>예  
 기능 중 일부의 다시 쓰기를 사용 하는 variadic 템플릿 함수 메커니즘을 설명 하는 좋은 방법 `printf`:  
  
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
  
## <a name="output"></a>출력  
  
```  
  
1  
10, 20  
100, 200, 300  
first, 2, third, 3.14159  
```  
  
> [!NOTE]
>  Variadic 템플릿 함수를 통합 하는 대부분의 구현 특정 형태의 재귀를 사용 하지만 기존의 재귀와에서 약간 다릅니다.  일반적인 재귀는 동일한 서명을 사용 하 여 자신을 호출 하는 함수에 포함 됩니다. (오버 로드 된 입력 했거나 템플릿을 기반으로 하지만 시그니처는 때마다 선택 되었습니다.) Variadic 재귀 될 때마다를 다른 서명 아웃 함으로써 스탬프를 (거의 항상 감소) 서로 다른 개수의 인수를 사용 하 여 variadic 함수 템플릿을 호출 해야 합니다. "기본 사례"는 여전히 필요 있지만 재귀의 특성은 다릅니다.  
  
