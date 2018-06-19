---
title: C + + 표준 특성 | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.topic: language-reference
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: 7bd7fd4e01fb210069f4dbae42a671e4dd9c64c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416199"
---
# <a name="attributes-in-c"></a>C + + 특성

C + + 표준 특성 집합을 정의 하 고도 (공급 업체 특정 네임 스페이스 내)를 자체 특성을 정의 하는 컴파일러 공급 업체를 허용 하지만 컴파일러에서 표준에 정의 된 특성에만 인식 하는 데 필요한 합니다.

경우에 따라 표준 특성이 컴파일러 관련 declspec 매개 변수와 함께 겹칩니다. Visual c + +에서 사용할 수 있습니다는 `[[deprecated]]` 사용 하는 대신 특성 `declspec(deprecated)` 는 규칙에 부합 되 컴파일러에서 특성을 인식 됩니다. 모든 다른 declspec 매개 변수에 대해 dllimport 및 dllexport 등,가 아직 특성 해당 키 없음 declspec 구문을 사용 하 여 계속 합니다. 특성 형식 시스템에 영향을 주지 않는 하 고 프로그램의 의미를 변경 하지 않습니다. 컴파일러는 인식 하지 않는 특성 값을 무시 합니다.

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 특성 목록 범위에 단일 모든 이름에 대 한 네임 스페이스를 지정할 수 있습니다 `using` 유도:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C + + 표준 특성

C + + 11에 특성 주석을 공급 업체별 아닐 수 있는 추가 정보가 있는 c + + 구문 (클래스, 함수, 변수 및 블록에 제한 되지 않음 포함)를 지정 하는 표준화 된 방법을 제공 합니다. 정보 메시지를 생성 하거나 특성 사용된 하는 코드를 컴파일할 때 특별 한 논리를 적용 하려면 컴파일러에서이 정보를 사용할 수 있습니다. 컴파일러 즉,이 구문을 사용 하 여 사용자 지정 특성을 정의할 수 없습니다 인식 하지 않는 모든 특성을 무시 합니다. 특성은 대괄호로 이중:

```cpp
[[deprecated]]
void Foo(int);
```

특성이 나타내는 대신 #pragma 지시문을 추가 (Visual c + +), 등의 공급 업체별 확장 하는 표준화 된 표현 또는 &#95; &#95;특성&#95; &#95; (GNU). 그러나 대부분의 용도 대 한 공급 업체 특정 구문을 사용 해야 여전히 합니다. 현재 표준에는 컴파일러를 인식 해야 하는 다음 특성을 지정 합니다.

- `[[noreturn]]` 지정 하는 함수 반환 하지 않습니다. 즉 예외가 항상 throw 됩니다. 컴파일러는 해당 컴파일 규칙에 대 한 조정할 수 `[[noreturn]]` 엔터티.

- `[[carries_dependency]]` 함수는 데이터 종속성 순서 스레드 동기화와 관련 하 여 전파 있는지를 지정 합니다. 특성 지정 전달 된 인수는 함수 본문에 대 한 종속성을 수행 하려면 하나 이상의 매개 변수에 적용할 수 있습니다. 함수 반환 값 전달 함수의 종속성을 지정 하려면 자체에 특성을 적용할 수 있습니다. 컴파일러는 보다 효율적인 코드를 생성 하려면이 정보를 사용할 수 있습니다.

- `[[deprecated]]` **Visual Studio 2015 이상:** 지정 함수는 사용할 수 없습니다 및 이후 버전의 라이브러리 인터페이스 존재 하지 않을 수 있습니다. 컴파일러는 클라이언트 코드에서 함수를 호출 하려고 하면 정보 메시지를 생성 하는 데 사용할 수 있습니다. 클래스, 형식 정의 이름, 변수, 비정적 데이터 멤버, 함수, 네임 스페이스, 열거형, 열거자, 또는 템플릿 특수화의 선언에 적용할 수 있습니다.  

- `[[fallthrough]]` **2017 이상 visual Studio:** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md))는 `[[fallthrough]]` 특성의 컨텍스트에서 사용할 수 있습니다 [전환](switch-statement-cpp.md) 컴파일러 (또는 읽는 사람에 대 한 힌트를 사용 하 여 문 코드) fallthrough 동작이 지정 된입니다. Visual c + + 컴파일러 현재 경고 하지 않습니다 fallthrough 동작에 있으므로이 특성에 영향을 주지 컴파일러 동작이 없습니다.

- `[[nodiscard]]` **Visual Studio 2017 15.3 이상 버전:** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)) 함수의 반환 값에 취소 하려고 하지 지정 합니다. 이 예제에 표시 된 대로 C4834, 경고를 발생 시킵니다.

   ```cpp
   [[nodiscard]]
   int foo(int i) { return i * i; }

   int main()
   {
       foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
       return 0;
   }
   ```

- `[[maybe_unused]]` **Visual Studio 2017 15.3 이상 버전:** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)) 지정 하는 변수, 함수, 클래스, typedef, 비정적 데이터 멤버, 열거형 또는 템플릿 특수화 의도적으로 사용할 수 없습니다. 엔터티의 표시 하면 컴파일러에서 경고 하지 않습니다 `[[maybe_unused]]` 사용 되지 않습니다. 특성 없이 선언 된 엔터티 특성으로, 그 반대의 다시 선언 나중 수 있습니다. 표시 된 첫 번째 선언을 분석 한 후 및 현재 변환 단위의 나머지에 대해 표시 된 엔터티 간주 됩니다.

## <a name="microsoft-specific-attributes"></a>Microsoft 전용 특성

- `[[gsl::suppress(rules)]]` 이 Microsoft 전용 특성을 적용 하는 검사에서 경고가 표시 되지 않도록 하는 데 사용 됩니다 [지침 지원 라이브러리 (GSL)](https://github.com/Microsoft/GSL) 코드에는 규칙입니다. 예를 들어이 코드 조각을 참조 하십시오.

    ```cpp
    void main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

   이 예제에서는 이러한 경고를 발생 시킵니다.

   - 26494 (유형 규칙 5: 항상 개체를 초기화 합니다.)

   - 26485 (범위 규칙 3: 포인터 decay 배열이 없습니다.)

   - 26481 (범위 규칙 1: 포인터 산술 연산을 사용 하지 마십시오. 범위 대신 사용 합니다.)

   처음 두 가지 경고를 설치 하 고 활성화 CppCoreCheck 코드 분석 도구를 사용 하 여이 코드를 컴파일하면 발생 합니다. 하지만 세 번째 경고는 특성으로 인해 발생 하지 않습니다. 특정 규칙 번호를 포함 하지 않고 [[gsl::suppress(bounds)]]를 작성 하 여 전체 범위 프로 파일을 억제할 수 있습니다. C + + 코어 지침 향상 하 고 안전한 코드를 작성할 수 있도록 설계 되었습니다. 표시 안 함 특성을 사용 하면 손쉽게 필요 하지는 때에 경고를 해제 하려면.
