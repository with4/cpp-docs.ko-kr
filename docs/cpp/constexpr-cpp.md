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
ms.openlocfilehash: 1f95f6c98138ff1eb52750c1b8593795ca28c784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417999"
---
# <a name="constexpr-c"></a>constexpr(C++)

키워드 **constexpr** C + + 11에 도입 된 및 C + + 14에서 향상 되었습니다. 의미 *상수 식*합니다. 마찬가지로 **const**, 모든 코드 값을 수정 하려고 하면 컴파일러 오류가 발생 합니다 있도록 변수에 적용할 수 있습니다. 와 달리 **const**, **constexpr** 클래스 생성자 및 함수에도 적용 될 수 있습니다. **constexpr** 는 값 또는 반환 값이 상수이 고 가능한 경우 컴파일 타임에 계산할 수는 나타냅니다.

A **constexpr** const 정수가 템플릿 인수 및 배열 선언과 같이 필요한 곳 마다 정수 계열 값을 사용할 수 있습니다. 고 런타임 대신 컴파일 타임에 값을 계산할 수 있는 때 더 빠르게 실행 하 고 더 적은 메모리를 사용 하 여 프로그램 지원할 수 있습니다.

컴퓨팅 컴파일 타임 상수의 복잡성 및 잠재적 영향을 컴파일 시간을 최소화 하려면 표준 C + + 14에서는 상수 식에 관련 된 형식 이어야 제한 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

## <a name="syntax"></a>구문

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>매개 변수

 *params*  
하나 이상의 매개 변수에 리터럴 형식 이어야 하며 그 자체가 상수 식 이어야 합니다.

## <a name="return-value"></a>반환 값


 Constexpr 변수 또는 함수 반환 해야 합니다는 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

## <a name="constexpr-variables"></a>constexpr 변수

 const 및 constexpr 변수 간의 주요 차이점은 const 변수의 초기화는 런타임까지 지연시킬 수 있는 반면 constexpr 변수는 컴파일 타임에 초기화해야 한다는 것입니다.  모든 constexpr 변수는 상수입니다.

- 변수를 선언할 수 있습니다 **constexpr**, 변수가 리터럴 형식이 고 초기화 됩니다. 으로 생성자를 선언 해야 하는 생성자가의 초기화를 수행 하는 경우 **constexpr**합니다.

- 참조하는 개체가 상수 식으로 초기화되고 초기화 중에 호출되는 암시적 변환도 모두 상수 식인 경우 참조를 constexpr로 선언할 수 있습니다.

- 모든 선언은 **constexpr** 변수 또는 함수가 있어야는 **constexpr** 지정자입니다.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> constexpr 함수

A **constexpr** 함수는 사용 하는 코드가 필요로 하는 경우 컴파일 시 반환 값을 계산할 수 있습니다.  해당 인수가 **constexpr** 값 및 사용 하는 코드 예를 들어 초기화를 컴파일 타임에 반환 값을 요구는 **constexpr** 변수 나 비형식 템플릿 인수 제공 것 컴파일 타임 상수를 생성합니다. 비-를 사용 하 여 호출**constexpr** 인수, 하거나 해당 값 컴파일 타임에 필요 하지 않을 경우 일반 함수 처럼 런타임에 값을 생성 합니다.  (이 이중 동작 덕분 작성 하지 않아도 **constexpr** 및 비-**constexpr** 버전의 동일한 기능을 합니다.)

A **constexpr** 함수 또는 생성자는 암시적으로 **인라인**합니다.

Constexpr 함수에는 다음 규칙이 적용 됩니다.

- A **constexpr** 함수에 동의 하 고만 반환 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

- A **constexpr** 함수는 재귀적일 수 있습니다.

- 않아야 [가상](../cpp/virtual-cpp.md)합니다. A 바깥쪽 클래스에 있는 경우 가상 기본 클래스 생성자를 constexpr로 정의할 수 없습니다.

- 본문으로 정의할 수 있습니다 **= 기본값** 또는 **= 삭제**합니다.

- No 사용할 수 있습니다 **goto** 문이나 try 블록입니다.

- Constexpr 이외 템플릿의 명시적 특수화로 선언할 수 있습니다 **constexpr**:

- 명시적 특수화는 **constexpr** 템플릿 있어서는 안 될 수도 **constexpr**:

에 다음 규칙이 적용 **constexpr** 함수 및 이후 버전에 Visual Studio 2017:

- 포함 될 수 있습니다 **경우** 및 **전환** 문과 모든 반복 문을 포함 하 여 **에 대 한**범위 기반 for, **동안**, 및 **수행-동안**합니다.
 
- 지역 변수 선언을 포함 될 수 있지만 변수 초기화는 리터럴 형식 이어야 하 고 정적 또는 스레드 로컬이 될 수 없습니다. 로컬로 선언 된 변수는 const 일 필요가 없습니다 하며 변경할 수 있습니다.

- Constexpr 비정적 멤버 함수는 암시적으로 const 일 필요가 없습니다.


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> 참고: Visual Studio 디버거에서 최적화 비 디버깅 빌드를 디버깅할 때 알 수 있습니다 여부는 **constexpr** 함수 내에 중단점을 배치 하 여 컴파일 타임에 계산 되는 합니다. 중단점을 적중할 경우 함수가 런타임에 호출되었습니다.  그렇지 않을 경우 함수가 컴파일 타임에 호출되었습니다.

## <a name="extern-constexpr"></a>extern constexpr

[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md) 컴파일러 옵션을 사용 하도록 컴파일러에 적용 하면 [외부 링크]() 를 사용 하 여 선언 된 변수에 **extern constexpr**합니다. 이전 버전의 Visual Studio 및 기본적으로 또는 **/Zc:externConstexpr-** Visual Studio 적용에 내부 링크가 지정 된 **constexpr** 경우라도 변수는 **extern** 키워드를 사용 합니다. **/Zc:externConstexpr** 옵션은 Visual Studio 2017 업데이트 15.6부터 사용할 수 있습니다. 기본적으로 꺼져 있습니다. /permissive-option /Zc:externConstexpr 수는 없습니다.

## <a name="example"></a>예제

 다음 예제와 **constexpr** 변수, 함수 및 사용자 정의 형식입니다. Main ()에 있는 마지막 문의 사항에 유의 **constexpr** 멤버 함수 getvalue ()는 런타임에 호출 값은 컴파일 타임에 알려진 필요가 없습니다.

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

## <a name="see-also"></a>참고 항목

- [선언 및 정의](../cpp/declarations-and-definitions-cpp.md)
- [const](../cpp/const-cpp.md)
