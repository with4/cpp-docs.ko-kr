---
title: constexpr (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe13dbe61b0a50226f82ae8fb09ab46c922309d1
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406938"
---
# <a name="constexpr-c"></a>constexpr(C++)

키워드 **constexpr** c++11에서 도입 되었으며 c++14에서 향상 되었습니다. 의미 *상수 식*합니다. 와 같은 **const**, 코드 값을 수정 하려고 하는 경우 컴파일러 오류가 발생 되도록 변수에 적용할 수 있습니다. 와 달리 **상수**를 **constexpr** 클래스 생성자 및 함수에 적용할 수도 있습니다. **constexpr** 함을 나타냅니다 값 또는 반환 값이 상수입니다. 가능한 경우 컴파일 시간에 계산할 수 됩니다.

A **constexpr** const 정수 필요할 때마다와 같은 템플릿 인수 및 배열 선언에서 정수 계열 값을 사용할 수 있습니다. 및 더 빠르게 실행 하 고 메모리를 적게 사용 하 여 프로그램을 런타임 대신 컴파일 타임에 계산할 수, 하는 경우 도움이 됩니다.

컴퓨팅 컴파일 타임 상수의 복잡성 및 컴파일 타임에 대 한 잠재적 영향을 제한, 표준 C + + 14 하려면 상수 식에 관련 된 형식으로 제한 되도록 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

## <a name="syntax"></a>구문

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>매개 변수

 *params*  
하나 이상의 매개 변수는 리터럴 형식 이어야 하며 그 자체가 상수 식 이어야 합니다.

## <a name="return-value"></a>반환 값

 Constexpr 변수 또는 함수 반환 해야 합니다는 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

## <a name="constexpr-variables"></a>constexpr 변수

 const 및 constexpr 변수 간의 주요 차이점은 const 변수의 초기화는 런타임까지 지연시킬 수 있는 반면 constexpr 변수는 컴파일 타임에 초기화해야 한다는 것입니다.  모든 constexpr 변수는 상수입니다.

- 사용 하 여 변수를 선언할 수 있습니다 **constexpr**이면 변수가 리터럴 형식이 고 초기화 됩니다. 생성자에서 초기화는 수행 하는 경우 생성자로 선언 되어야 합니다 **constexpr**합니다.

- 참조하는 개체가 상수 식으로 초기화되고 초기화 중에 호출되는 암시적 변환도 모두 상수 식인 경우 참조를 constexpr로 선언할 수 있습니다.

- 모든 선언을 **constexpr** 변수나 함수가 있어야 합니다 **constexpr** 지정자입니다.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> constexpr 함수

A **constexpr** 함수는 필요한 코드를 사용 하는 경우 컴파일 시 반환 값을 계산할 수 있습니다.  해당 인수가 **constexpr** 값 및 사용 하는 코드를 초기화 하는 예제에 대 한 컴파일 시간에 반환 값이 필요는 **constexpr** 변수는 비형식 템플릿 인수를 제공 하거나 해당 컴파일 시간 상수를 생성합니다. 비-를 사용 하 여 호출 하는 경우**constexpr** 인수 또는 일반 함수 처럼 런타임에 값을 해당 값 컴파일 타임에 필요 하지 않은 경우 생성 합니다.  (이 이중 동작 덕분 작성 하지 않고도 **constexpr** 및 비-**constexpr** 동일한 함수의 버전입니다.)

A **constexpr** 함수 또는 생성자는 암시적 **인라인**합니다.

Constexpr 함수에 다음 규칙이 적용 됩니다.

- A **constexpr** 함수 수락 해야 하 고만 반환 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

- A **constexpr** 함수는 재귀적일 수 있습니다.

- 일 수 없습니다 [가상](../cpp/virtual-cpp.md)합니다. 바깥쪽 클래스에 있는 경우 모든 가상 기본 클래스 생성자를 constexpr로 정의할 수 없습니다.

- 본문은 `= default` 또는 `= delete`로 정의할 수 있습니다.

- 본문에는 아니요 포함 될 수 있습니다 **goto** 문이나 try 블록입니다.

- Constexpr이 아닌 템플릿의 명시적 특수화를 선언할 수 있습니다 **constexpr**:

- 명시적 특수화를 **constexpr** 템플릿 수도 않아도 **constexpr**:

다음 규칙이 적용 됩니다 **constexpr** 함수 Visual Studio 2017 이상:

- 포함할 수 있습니다 **하는 경우** 및 **전환** 문과 포함 하는 모든 반복 문을 **에 대 한**에 대 한 범위 기반 **하는 동안**, 및 **수행-동안**합니다.
 
- 지역 변수 선언, 포함 될 수 있지만 변수 초기화는 리터럴 형식 이어야 하 고 정적 또는 스레드 로컬 일 수 없습니다. 로컬로 선언 된 변수는 const 일 필요가 없습니다 및 변경할 수 있습니다.

- Constexpr 비정적 멤버 함수는 암시적으로 생성 될 필요가 없습니다.


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> 참고: Visual Studio 디버거에서 최적화 되지 않은 디버깅 빌드를 디버그 하는 경우 알 수 있는지 여부를 **constexpr** 함수 내에 중단점을 배치 하 여 컴파일 시간에 평가 되는 합니다. 중단점을 적중할 경우 함수가 런타임에 호출되었습니다.  그렇지 않을 경우 함수가 컴파일 타임에 호출되었습니다.

## <a name="extern-constexpr"></a>extern constexpr

[/zc: externconstexpr](../build/reference/zc-externconstexpr.md) 컴파일러 옵션을 사용 하면 적용할 컴파일러 [외부 링크가]() 사용 하 여 선언 된 변수를 **extern constexpr**합니다. 이전 버전의 Visual Studio 및 기본적으로 이거나 **/Zc:externConstexpr-** 지정 된 경우 Visual Studio 내부 링크에 적용 됩니다 **constexpr** 경우에도 변수는 **extern** 키워드를 사용 합니다. 합니다 **/zc: externconstexpr** 옵션은 Visual Studio 2017 업데이트 15.6부터 사용할 수 있습니다. 기본적으로 꺼져 있습니다. /permissive-option /zc: externconstexpr 활성화 되지 않습니다.

## <a name="example"></a>예

 다음 예와 **constexpr** 변수, 함수 및 사용자 정의 형식입니다. Main ()의 마지막 문에서 유의 합니다 **constexpr** 멤버 함수 getvalue () 값은 컴파일 타임에 알려질 필요가 없으므로 런타임에 호출 됩니다.

```cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    //foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    //Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    //Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}
```

## <a name="requirements"></a>요구 사항

Visual Studio 2015

## <a name="see-also"></a>참고자료
 [선언 및 정의](../cpp/declarations-and-definitions-cpp.md)  
 [const](../cpp/const-cpp.md)
