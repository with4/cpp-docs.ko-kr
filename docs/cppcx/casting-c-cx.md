---
title: 캐스팅 (C + + /cli CX) | Microsoft Docs
ms.custom: ''
ms.date: 06/19/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66c0e6bc9d987c400c709e74586e6e37ccc0b715
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305997"
---
# <a name="casting-ccx"></a>캐스팅(C++/CX)

Windows 런타임 형식에 적용 된 네 가지 캐스트 연산자: [static_cast 연산자](../cpp/static-cast-operator.md), [dynamic_cast Operator](../cpp/dynamic-cast-operator.md), **safe_cast Operator**, 및 [ reinterpret_cast 연산자](../cpp/reinterpret-cast-operator.md)합니다. **safe_cast** 및 **static_cast** 는 변환이 수행 될 수 없는 경우 예외를 throw 합니다. [static_cast 연산자](../cpp/static-cast-operator.md) 도 컴파일 타임 형식 검사를 수행 합니다. **dynamic_cast** 반환 **nullptr** 형식을 서로 변환할 수 없는 경우. 하지만 **reinterpret_cast** null이 아닌 값을 반환 잘못 없을 수 있습니다. 이러한 이유로 사용 하는 권장 **reinterpret_cast** 캐스팅이 성공할 지를 알고 있습니다. 또한 좋습니다 사용 하는 C 스타일 캐스트에 프로그램 C + + /cli CX 동일 하기 때문에 코드 **reinterpret_cast**합니다.

또한 컴파일러와 런타임은 암시적 캐스트를 수행합니다. 예를 들어, 매개 변수 형식이 `Object^`인 메서드에 값 형식 또는 기본 제공 형식이 인수로 전달될 때 boxing 연산에서 암시적 캐스트를 수행합니다. 이론적으로 런타임에는 암시적 캐스트로 인해 예외가 발생하지 않습니다. 컴파일러가 암시적 변환을 수행할 수 없는 경우 컴파일 시 오류가 발생합니다.

Windows Runtime 예외 대신 HRESULT 오류 코드를 사용 하는 COM을 통한 추상화입니다. 일반적으로 [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) 은 E_NOINTERFACE의 하위 수준 COM 오류를 나타냅니다.

## <a name="staticcast"></a>static_cast

A **static_cast** 두 형식 간에 상속 관계가 있는지 여부를 확인 하려면 컴파일 타임에 확인 합니다. 형식이 관련되지 않은 경우 컴파일러 오류가 발생합니다.

A **static_cast** 는 ref 클래스 의해서도 런타임 검사가을 수행할 수 있습니다. A **static_cast** 에서 ref 클래스 수 컴파일 타임 확인을 통과할 수 있지만 런타임 시;이 경우에는 여전히 실패는 `Platform::InvalidCastException` throw 됩니다. 대개 이러한 예외는 거의 항상 개발 및 테스트 중에 제거할 수 있는 프로그래밍 오류를 나타내기 때문에 무시해도 됩니다.

사용 하 여 **static_cast** 확실히 캐스팅 작동 하 고 코드에서 두 형식 간의 관계를 명시적으로 선언 합니다.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

**safe_cast** 연산자는 일부 Windows 런타임입니다. 변환에 실패하는 경우 런타임 형식 검사를 수행하고 `Platform::InvalidCastException` 을 throw합니다. 사용 하 여 **safe_cast** 런타임 오류가 예외 상황을 나타낼 때. 주요 목적은 **safe_cast** 개발 중 프로그래밍 오류를 식별 하 고 테스트 단계에서 발생 하는 지점입니다. 처리되지 않은 예외가 오류 발생 시점을 나타내므로 예외를 처리할 필요가 없습니다.

코드에서 관계를 선언하지는 않지만 캐스팅이 확실히 작동하는 경우 safe_cast를 사용합니다.

```cpp
    // A and B are not related
    interface class A{};
    interface class B{};
    public ref class Class1 sealed : A, B { };
    // ...
    A^ obj = ref new Class1();

    // You know that obj’s backing type implements A and B, but
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.
    B^ obj2 = safe_cast<B^>(obj);
```

## <a name="dynamiccast"></a>dynamic_cast

사용 하 여 **dynamic_cast** 개체를 캐스팅 하는 경우 (hat 보다 구체적으로, **^**) 더 많이 파생 된 형식으로 예상 하는 중 하나가 대상 개체가 있을 경우에 따라 수도 있습니다 **nullptr** 상황을 예외 대신 일반 코드 경로로 처리 하려는 아니며 캐스팅에 실패할 수 있습니다. 예를 들어,는 **비어 있는 앱 (유니버설 Windows)** 프로젝트 템플릿에 `OnLaunched` app.xamp.cpp 사용 하 여에서 메서드 **dynamic_cast** 응용 프로그램 창에 내용이 있는지 여부를 테스트 합니다. 내용이 없어도 오류가 아니며 예기된 상황입니다. `Windows::Current::Content` 는 `Windows::UI::XAML::UIElement` 이며 상속 계층 구조에서 더 많이 파생된 형식인 `Windows::UI.XAML::Controls::Frame`으로 변환됩니다.

```cpp
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args)
{
    auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content);

    // Do not repeat app initialization when the window already has content,
    // just ensure that the window is active
    if (rootFrame == nullptr)
    {
        // Create a Frame to act as the navigation context and associate it with
        // a SuspensionManager key
        rootFrame = ref new Frame();
        // ...
    }
}
```

또 다른 용도 **dynamic_cast** 검색 한 `Object^` boxed 값 형식이 포함 되어 있는지 여부를 확인할 수 있습니다. 이 경우 `dynamic_cast<Platform::Box>` 나 `dynamic_cast<Platform::IBox>`를 시도합니다.

## <a name="dynamiccast-and-tracking-references-"></a>dynamic_cast 및 추적 참조(%)

적용할 수 있습니다는 **dynamic_cast** 캐스팅 처럼 동작 추적 참조에 있지만이 경우 **safe_cast**합니다. Throw `Platform::InvalidCastException` 실패에 대 한 추적 참조의 값을 가질 수 없으므로 **nullptr**합니다.

## <a name="reinterpretcast"></a>reinterpret_cast

컴파일 타임 검사 또는 런타임 검사 중 어느 것도 수행되지 않으므로 [reinterpret_cast](../cpp/reinterpret-cast-operator.md) 를 사용하지 않는 것이 좋습니다. 최악의 경우에는 **reinterpret_cast** 프로그래밍 오류가 개발 시 감지 되지 않은 이동 및 프로그램의 동작에 어려운 오류나 심각한 오류가 발생할 수 있습니다. 사용 하는 권장 따라서 **reinterpret_cast** 드문 경우 지만 관련 되지 않은 형식 간의 캐스팅이 필요 하며 캐스팅이 성공할 때에 합니다. 사용 하는 드문 예는 Windows 런타임 형식을 내부 ABI 형식으로 변환 하는-즉, 해당 참조는 개체에 대 한 횟수를 제어 수행 되어 있습니다. 이렇게 하려면 [ComPtr Class](../cpp/com-ptr-t-class.md) 스마트 포인터를 사용하는 것이 좋습니다. 그렇지 않으면 인터페이스에서 릴리스를 명시적으로 호출해야 합니다. 다음 예제에서는 ref 클래스를 `IInspectable*`로 캐스팅하는 방법을 보여 줍니다.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

사용 하는 경우 **reinterpret_cast** oneWindows 런타임 인터페이스 간에 변환할 있습니다으로 인해 두 번 해제 됩니다. 따라서[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] 가 아닌 인터페이스로 변환할 때만 이 캐스트를 사용하세요.

## <a name="abi-types"></a>ABI 형식

- ABI 형식은 Windows SDK의 헤더에 있습니다. 편의를 위해 헤더는 네임스페이스의 이름을 따릅니다(예: `windows.storage.h`).

- ABI 형식은 특수 특수 네임스페이스 ABI에 있습니다(예: `ABI::Windows::Storage::Streams::IBuffer*`).

- Windows 런타임 인터페이스 형식과 동일한 ABI 형식 간의 변환에는 안전 항상-즉, `IBuffer^` 를 `ABI::IBuffer*`합니다.

- Windows 런타임 런타임 클래스를 항상 변환할 `IInspectable*` 이나 알려진 기본 인터페이스로 합니다.

- ABI 형식으로 변환한 후에는 형식의 수명을 승인하고 COM 규칙을 따라야 합니다. ABI 포인터의 수명 관리 간소화를 위해 `WRL::ComPtr` 을 사용하는 것이 좋습니다.

다음 표에서 안전 하 게 하는 경우 요약 **reinterpret_cast**합니다. 모든 경우에 캐스팅은 양방향으로 안전합니다.

|||
|-|-|
|`HSTRING`|`String^`|
|`HSTRING*`|`String^*`|
|`IInspectable*`|`Object^`|
|`IInspectable**`|`Object^*`|
|`IInspectable-derived-type*`|`same-interface-from-winmd^`|
|`IInspectable-derived-type**`|`same-interface-from-winmd^*`|
|`IDefault-interface-of-RuntimeClass*`|`same-RefClass-from-winmd^`|
|`IDefault-interface-of-RuntimeClass**`|`same-RefClass-from-winmd^*`|

## <a name="see-also"></a>참고자료

- [형식 시스템](../cppcx/type-system-c-cx.md)
- [Visual c + + 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)
- [네임 스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
