---
title: "예외 (C + + /cli CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2018
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7e54d98ac4e1398753746dcac074de53ee2e7a0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="exceptions-ccx"></a>예외(C++/CX)

오류 처리에 C + + /cli CX 예외 기반 합니다. 가장 기본적인 수준에서 Windows 런타임 구성 요소는 오류를 HRESULT 값으로 보고합니다. C + + /CX에서는 이러한 값은 HRESULT 값 및 프로그래밍 방식으로 액세스할 수 있는 문자열 설명을 포함 하는 강력한 형식의 예외로 변환 됩니다.  예외는 `ref class` 에서 파생된 `Platform::Exception`로 구현됩니다.  `Platform` 네임스페이스는 가장 일반적인 HRESULT 값에 대한 고유한 예외 클래스를 정의합니다. 다른 모든 값은 `Platform::COMException` 클래스를 통해 보고됩니다. 모든 예외 클래스에는 원래 HRESULT를 검색하는 데 사용할 수 있는 [Exception::HResult](platform-exception-class.md#hresult) 필드가 있습니다. 데 도움이 되는 예외의 원본 소스를 쉽게 파악할 c + + 이외의 언어로 작성 된 코드에서 발생 하는 경우에 디버거의 사용자 코드에에서 대 한 호출 스택 정보를 검사할 수 있습니다.

## <a name="exceptions"></a>예외

C + + 프로그램에서 있습니다 수 throw 및 catch 하는 Windows 런타임 작업에서 가져온 예외에서 파생 된 예외 `std::exception`, 또는 사용자 정의 형식입니다. 응용 프로그램 이진 인터페이스 (ABI) 경계를 예를 들어 경우 넘는 예외를 catch 하는 코드가 JavaScript로 작성 된 경우에 Windows 런타임 예외를 throw 해야 합니다. 예외로 변환 되는 비-Windows 런타임 c + + 예외가 ABI 경계에 도달 하면는 `Platform::FailureException` 예외가 E_FAIL HRESULT를 나타내는 예외입니다. ABI에 대 한 자세한 내용은 참조 [Windows 런타임 구성 요소 만들기 c + +](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)합니다.

선언할 수는 [platform:: exception](platform-exception-class.md) HRESULT 매개 변수 또는 HRESULT 매개 변수 두 생성자 중 하나를 사용 하 여 및 [platform:: string](platform-string-class.md)^ 넘어 전달 될 수 있는 매개 변수는 ABI 처리 하는 모든 Windows 런타임 앱입니다. HRESULT 매개 변수 또는 HRESULT 매개 변수와 [매개 변수를 사용하는 두](platform-exception-class.md#createexception) Exception::CreateException 메서드 `Platform::String^` 오버로드 중 하나를 사용하여 예외를 선언할 수도 있습니다.

## <a name="standard-exceptions"></a>표준 예외

C + + /cli CX는 일반적인 HRESULT 오류를 나타내는 표준 예외 집합을 지원 합니다. 각 표준 예외는 [Platform::COMException](platform-comexception-class.md)에서 파생되고, 이는 `Platform::Exception`에서 파생됩니다. ABI 경계를 넘어 예외를 throw할 경우 표준 예외 중 하나를 throw해야 합니다.

사용자 고유의 예외 형식은 `Platform::Exception`에서 파생할 수 없습니다. 사용자 지정 예외를 throw하려면 사용자 정의 HRESULT를 사용하여 `COMException` 개체를 생성하세요.

다음 표에서는 표준 예외를 보여 줍니다.

|name|내부 HRESULT|설명|
|----------|------------------------|-----------------|
|COMException|*사용자 정의 hresult*|COM 메서드 호출에서 인식할 수 없는 HRESULT가 반환되는 경우에 throw됩니다.|
|AccessDeniedException|E\_액세스 실패|리소스 또는 기능에 대한 액세스가 거부된 경우 throw됩니다.|
|ChangedStateException|E\_CHANGED\_상태|부모 컬렉션이 변경된 후 컬렉션 반복기 또는 컬렉션 뷰의 메서드가 호출되어 메서드 결과가 무효화되면 throw됩니다.|
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|COM 클래스가 등록되지 않은 경우 throw됩니다.|
|DisconnectedException|RPC\_E\_연결 끊김|개체와 클라이언트의 연결이 끊기면 throw됩니다.|
|FailureException|E\_실패|작업이 실패하면 throw됩니다.|
|InvalidArgumentException|E\_INVALIDARG|메서드에 제공된 인수 중 하나가 유효하지 않을 때 throw됩니다.|
|InvalidCastException|E\_NOINTERFACE|형식이 다른 형식에 대한 캐스트가 될 수 없는 경우 throw됩니다.|
|NotImplementedException|E\_NOTIMPL|클래스에 인터페이스 메서드가 구현되어 있지 않은 경우 throw됩니다.|
|NullReferenceException|E\_포인터|null 개체 참조를 역참조하려고 할 때 throw됩니다.|
|ObjectDisposedException|RO\_E\_닫힘|삭제된 개체에서 연산이 수행될 때 throw됩니다.|
|OperationCanceledException|E\_중단|작업이 중단되면 throw됩니다.|
|OutOfBoundsException|E\_범위|작업이 유효한 범위를 벗어난 데이터에 액세스하려고 하면 throw됩니다.|
|OutOfMemoryException|E\_OUTOFMEMORY|메모리가 부족하여 작업을 완료할 수 없는 경우 throw됩니다.|
|WrongThreadException|RPC\_E\_잘못\_스레드|프록시 개체용 인터페이스 포인터를 통해 스레드의 아파트에 속하지 않는 스레드가 호출될 경우 throw됩니다.|

## <a name="hresult-and-message-properties"></a>HResult 및 Message 속성

모든 예외에는 [HResult](platform-comexception-class.md#hresult) 속성과 [Message](platform-comexception-class.md#message) 속성이 있습니다. [Exception::HResult](platform-exception-class.md#hresult) 속성은 예외의 내부 숫자 HRESULT 값을 가져옵니다. [Exception::Message](platform-exception-class.md#message) 속성은 예외를 설명하는 시스템 제공 문자열을 가져옵니다. Windows 8에서이 메시지는 디버거에서 사용할 수 있으며 읽기 전용입니다. 즉, 예외를 다시 throw할 때 변경할 수 없습니다. Windows 8.1에서 이 메시지 문자열을 프로그래밍 방식으로 액세스하고 해당 예외를 다시 throw하는 경우 새 메시지를 제공할 수 있습니다. 비동기 메서드 호출에 대한 호출 스택을 포함하여 디버거에서 보다 나은 호출 스택 정보를 사용할 수 있습니다.

### <a name="examples"></a>예제

이 예제에서는 동기 작업에 대 한 Windows 런타임 예외를 throw 하는 방법을 보여 줍니다.

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

다음 예제에서는 예외를 catch하는 방법을 보여 줍니다.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

비동기 작업 중에 throw된 예외를 catch하려면 작업 클래스를 사용하여 오류 처리 연속을 추가합니다. 오류 처리 연속은 다른 스레드에서 throw된 예외를 다시 호출 스레드로 마샬링하므로 모든 잠재적 예외를 코드의 한 지점에서 처리할 수 있습니다. 자세한 내용은 참조 [c + +의 비동기 프로그래밍](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)합니다.

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected 이벤트

Windows 8.1 구독할 수 있습니다는 [:: unhandlederrordetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror#Windows_ApplicationModel_Core_ICoreApplicationUnhandledError_UnhandledErrorDetected) 정적 이벤트를 프로세스 종료 하려고 하는 처리 되지 않은 오류에 대 한 액세스를 제공 합니다. 이 처리기에 오류가 발생 한 위치에 관계 없이 도달는 [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) 이벤트 인수와 함께 전달 되는 개체입니다. 개체에서 `Propagate` 를 호출하면 해당 개체가 오류 코드에 해당하는 형식의 `Platform::*Exception` 을 만들고 throw합니다. Catch 블록에서는 필요한 경우 사용자 상태를 저장할 수 있으며, 그런 다음 `throw`를 호출하여 프로세스가 종료되도록 허용하거나 프로그램을 알려진 상태로 되돌리기 위한 작업을 수행합니다. 다음 예제에서는 기본 패턴을 보여 줍니다.

app.xaml.h:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

app.xaml.cpp:

```cpp
// Subscribe to the event, for example in the app class constructor:
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);

// Event handler implementation:
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)
{
    auto err = e->UnhandledError;

    if (!err->Handled) //Propagate has not been called on it yet.
{
     try
    {
        err->Propagate();
    }
    // Catch any specific exception types if you know how to handle them
    catch (AccessDeniedException^ ex)
    {
        // TODO: Log error and either take action to recover
        // or else re-throw exception to continue fail-fast
    }

}
```

### <a name="remarks"></a>설명

C + + /cli CX 사용 하지 않습니다는 `finally` 절.

## <a name="see-also"></a>참고 항목

[Visual c + + 언어 참조](visual-c-language-reference-c-cx.md)  
[네임 스페이스 참조](namespaces-reference-c-cx.md)  
