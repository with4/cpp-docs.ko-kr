---
title: "/Zc:twoPhase-(사용 안 함 2 단계 이름 lookup) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4582a5532d9fd410224ee4174ca3973bfe539656
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase-(2 단계 이름 조회 사용 안 함)

경우는 **/Zc:twoPhase-** 옵션을 지정 하면 컴파일러 구문 분석 하 고 동일한 맞지 않는 방식으로 버전의 Visual Studio 2017 버전 15.3 하기 전에 Visual Studio에서 클래스 템플릿과 템플릿 함수를 인스턴스화합니다. 

## <a name="syntax"></a>구문

> **/Zc:twoPhase-**

## <a name="remarks"></a>설명

Visual Studio 2017 15.3 이상 버전에서는 기본적으로 버전의 컴파일러는 템플릿 이름 확인에 대 한 2 단계 이름 조회를 사용합니다. 경우 **/Zc:twoPhase-** 지정, 컴파일러는 이전 맞지 않는 클래스 템플릿 및 함수 템플릿 이름 확인 및 대체 동작 되돌아갑니다.

**/Zc:twoPhase-** 맞지 않는 동작을 사용 하는 옵션 기본 설정 되지 않습니다. [관대 한 /-](permissive-standards-conformance.md) 옵션 표준에 맞는 2 단계 조회 컴파일러 동작을 암시적으로 설정 되지만 사용 하 여 재정의할 수 있습니다 **/Zc:twoPhase-**합니다.

버전 10.0.15063.0 (작성자가 업데이트 또는 Redstone 2) 및 이전 버전의 Windows SDK 헤더 파일 규격 모드에서 제대로 작동 하지 않습니다. 사용 해야 **/Zc:twoPhase-** Visual Studio 2017 버전 15.3 및 이상 버전을 사용 하는 경우 해당 SDK 버전에 대 한 코드를 컴파일할 수 있습니다. 버전의 Windows SDK 버전부터 10.0.15254.0 (Redstone 3 또는 Fall 작성자 업데이트) 규격 모드에서 제대로 작동 하 고 필요 하지 않습니다는 **/Zc:twoPhase-** 옵션입니다.

사용 하 여 **/Zc:twoPhase-** 코드 올바르게 컴파일하기 위해 이전 동작이 필요한 경우. 강력 하 게 표준에 맞게 코드를 업데이트 하는 것이 좋습니다.

### <a name="compiler-behavior-under-zctwophase-"></a>/Zc:twoPhase-에서 컴파일러 동작

버전의 Visual Studio 2017 버전 15.3 하기 전에 컴파일러에서 언제 **/Zc:twoPhase-** 지정, 컴파일러는이 동작을 사용 합니다.

- 구문 분석 하는 템플릿 선언에만, 클래스 헤드와 기본 클래스 목록. 템플릿 본문으로 토큰 스트림이 캡처됩니다. 함수 본문, 이니셜라이저, 기본 인수 또는 noexcept 인수를 갖지 구문 분석 됩니다. 클래스 템플릿은 클래스 템플릿의 선언이 올바른지 유효성을 검사 하는 임시 종류에 의사 인스턴스화입니다. 이 클래스 템플릿을 고려해 야 합니다.

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   템플릿 선언 `template <typename T`>, 클래스 헤드 `class Derived`, 및 기본 클래스 목록 `public Base<T>` 구문 분석 되 있지만 템플릿 본문으로 토큰 스트림이 캡처됩니다.

- 함수 템플릿에 구문 분석할 때 컴파일러는 함수 서명에 구문 분석 합니다. 함수 본문을 구문 분석 되지 않습니다. 대신, 토큰 스트림으로 캡처됩니다.

결과적으로, 템플릿 본문에 구문 오류가 발생 하는 경우 템플릿이 인스턴스화되지 오류 진단 되지 됩니다.

이 동작의 다른 효과 오버 로드 확인에입니다. 토큰 스트림을 인스턴스화의 사이트에서 확장 되는 방식으로 인해 템플릿 선언에서 표시 되지 않은 기호 인스턴스화 시 표시 될 수 있습니다 및 오버 로드 확인에 참여 합니다. 표준 달리 서식 파일을 정의할 때 표시 되는 코드에 따라 동작을 변경 하는 템플릿을 발생할 수 있습니다.

예를 들어 다음 코드를 고려합니다.

```cpp
#include <cstdio>

void func(void*) { std::puts("The call resolves to void*") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("The call resolves to int"); }

int main() 
{
    g(3.14);
}
```

컴파일된 경우 **/Zc:twoPhase-**,이 프로그램 "int로 호출 확인"에 출력 합니다. 규격 모드에서 **관대 한 /-**,이 프로그램 "호출에 void * 확인", 두 번째 오버 로드 때문에 인쇄 `func` 컴파일러에서 서식 파일을 발견 한 경우 표시 되지 않습니다.

*종속 이름*를 템플릿 매개 변수에 종속 되는 이름에서 다른 이기도 조회 동작을 내포 **/Zc:twoPhase-**합니다. 규격 모드에서 종속 이름 서식 파일의 정의 시 바인딩되지 않습니다. 대신, 이러한 이름은 조회 됩니다 템플릿이 인스턴스화될 때. 종속 함수 이름으로 함수 호출에 대 한 이름은 위와 같은 서식 파일의 정의에 대 한 호출 시 표시 되는 함수 집합에 바인딩되어 있습니다. 인수 종속 조회의 추가 오버 로드는 모두 템플릿 정의 시점의 끝점 및 템플릿이 인스턴스화될 위치에 추가 됩니다. 2 단계 조회의 두 단계는 템플릿 인스턴스화 시 종속 이름에 대 한 템플릿 정 및 조회의 시간에 종속 되지 않은 이름에 대 한 조회 있습니다. 아래 **/Zc:twoPhase-**, 컴파일러에서 일반, 정규화 되지 않은 조회 인수 종속 조회를 별도로 수행 하지는 않습니다 (즉,는 일은 2 단계 조회), 하므로 오버 로드 확인의 결과 다를 수 있습니다.

또 다른 예는 다음과 같습니다.

```cpp
// zctwophase1.cpp
// Compile by using
// cl /EHsc /W4 /permissive- zctwophase1.cpp
// cl /EHsc /W4 /permissive- /Zc:twoPhase- zctwophase1.cpp

#include <cstdio>

void func(long) { std::puts("func(long)"); }

template <typename T> void tfunc(T t) {
    func(t);
}

void func(int) { std::puts("func(int)"); }

namespace NS {
    struct S {};
    void func(S) { std::puts("NS::func(NS::S)"); }
}

int main() {
    tfunc(1729);
    NS::S s;
    tfunc(s);
}
```

사용 하지 않고 컴파일하면 **/Zc:twoPhase-**,이 옵션을 인쇄

```Output
func(long)
NS::func(NS::S)
```

로 컴파일하는 경우 **/Zc:twoPhase-**,이 옵션을 인쇄

```Output
func(int)
NS::func(NS::S)
```

규격 모드에서 **관대 한 /-**, 호출 `tfunc(1729)` 확인 되는 `void func(long)` 오버 로드, 하지 `void func(int)` 미만으로 오버 로드 **/Zc:twoPhase-**때문에, 정규화 되지 않은 `func(int)` 서식 파일의 정의 뒤에 선언 되며 인수 종속 조회를 통해 찾을 수 없습니다. 하지만 `void func(S)` 는 오버 로드는 호출에 대 한 설정에 추가 인수 종속 조회에 참여 `tfunc(s)` 템플릿 함수 뒤에 선언 된 경우에 합니다.

### <a name="update-your-code-for-two-phase-conformance"></a>2 단계 규칙에 대 한 코드 업데이트

이전 버전의 컴파일러 키워드 필요 하지 않습니다 `template` 및 `typename` everywhere c + + 표준에 필요한 합니다. 이러한 키워드 컴파일러 종속 이름이 구문 분석 해야 조회의 첫 번째 단계는 어떻게 명확 하 게 일부 위치에 필요 합니다. 예:

`T::Foo<a || b>(c);`

컴파일러 구문 분석 `Foo` 의 범위에서 변수로 `T`,이 코드를 의미 하는 논리적-또는 식을 `T::foo < a` 왼쪽 피연산자로 및 `b > (c)` 오른쪽 피연산자와 합니다. =을 사용 하는 경우 `Foo` 추가 하 여 서식 파일 인지 지정 해야 함수 템플릿으로 `template` 키워드:

`T::template Foo<a || b>(c);`

Visual Studio 2017 버전 15.3, 이전 버전에서는 언제 **/Zc:twoPhase-** 를 지정 하지 않고이 코드는 컴파일러에서 허용는 `template` 키워드 의인수와함께함수가서식파일에대한호출으로해석하고`a || b`매우 제한 된 방식으로 서식 파일을 구문 분석 하기 때문에, 합니다. 위의 코드 첫 번째 단계에서 전혀 구문 분석 되지 않습니다. 두 번째 단계는 충분 한 컨텍스트는 `T::Foo` 이므로 변수를 사용 하지 않고 템플릿을 컴파일러는 키워드의 사용을 적용 하지 않습니다.

키워드를 제거 하 여이 문제를 확인할 수도 있습니다 `typename` 이름 앞에 함수 템플릿 본문, 이니셜라이저, 기본 인수 및 noexcept 인수입니다. 예:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

키워드를 사용 하지 않는 경우 `typename` 함수 본문에서이 코드에서 컴파일됩니다 **/Zc:twoPhase-**, 아니라 **관대 한 /-**합니다. `typename` 키워드는 해당 필요는 `TYPE` 따라 달라 집니다. 본문을 구문 분석할 **/Zc:twoPhase-**, 컴파일러와 키워드가 필요 합니다. **관대 한 /-** 준수 모드, 없이 코드는 `typename` 키워드 오류를 생성 합니다. Visual Studio 2017 15.3 버전에 코드를 마이그레이션하고 beyond를 삽입 하는 `typename` 누락 된 키워드입니다.

마찬가지로,이 코드 예제를 고려해 야 합니다.

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

아래 **/Zc:twoPhase-** 이전 컴파일러에서 컴파일러만 필요 하 고는 `template` 2 줄에는 키워드입니다. 기본적으로과 준수 모드에서는 컴파일러가 이제도 필요는 `template` 4 임을 나타내는 선에 키워드 `T::X<T>` 템플릿입니다. 이 키워드 없는 코드가 살펴보고 표준을 준수 하 여 코드를 찾을 수 있도록 제공 합니다.

규칙과 관련 된 문제에 대 한 자세한 내용은 참조 [Visual Studio에서 c + + 규칙 향상](../../cpp-conformance-improvements-2017.md) 및 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zc:twoPhase-** 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고 항목

[/Zc(규칙)](../../build/reference/zc-conformance.md)<br/>
