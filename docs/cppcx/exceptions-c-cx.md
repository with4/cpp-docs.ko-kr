---
title: "예외(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: 22
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 22
---
# 예외(C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)의 오류 처리는 예외를 기반으로 합니다. 가장 기본적인 수준에서 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소가 오류를 HRESULT 값으로 보고합니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서 이러한 값은 HRESULT 값과 [!INCLUDE[win81](../cppcx/includes/win81-md.md)]에서 프로그래밍 방식으로 액세스할 수 있는 문자열 설명을 포함하는 강력한 형식의 예외로 변환됩니다.  예외는 `ref class`에서 파생된 `Platform::Exception`로 구현됩니다.`Platform` 네임스페이스는 가장 일반적인 HRESULT 값에 대한 고유한 예외 클래스를 정의합니다. 다른 모든 값은 `Platform::COMException` 클래스를 통해 보고됩니다. 모든 예외 클래스에는 원래 HRESULT를 검색하는 데 사용할 수 있는 [Exception::HResult Property](../cppcx/exception-hresult-property.md) 필드가 있습니다. 또한 [!INCLUDE[win81](../cppcx/includes/win81-md.md)]에서는 예외의 원본 소스를 정확하게 찾는 데 도움이 되는 디버거의 사용자 코드에 대한 호출 스택 정보를 검사할 수 있습니다. 이는 C\+\+ 이외의 언어로 작성된 코드에서 발생한 예외라도 마찬가지입니다.  
  
## 예외  
 C\+\+ 프로그램에서 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 작업에서 가져온 예외, `std::exception`에서 파생된 예외 또는 사용자 정의 형식을 throw하고 catch할 수 있습니다. 예외를 catch하는 코드가 JavaScript로 작성된 경우처럼 ABI\(응용 프로그램 이진 인터페이스\) 경계를 넘는 경우에만 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 예외를 throw해야 합니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] C\+\+가 아닌 예외가 ABI 경계에 도달하면 예외가 E\_FAIL HRESULT를 나타내는 `Platform::FailureException` 예외로 번역됩니다. ABI에 대한 자세한 내용은 [C\+\+로 Windows Runtime 구성 요소 만들기](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)를 참조하세요.  
  
 HRESULT 매개 변수 또는 HRESULT 매개 변수, 그리고 ABI 전반에서 [Platform::String](../cppcx/platform-exception-class.md)^ 매개 변수 처리 Windows 스토어 앱에 전달 가능한 해당 매개 변수를 받는 두 생성자 중 하나를 사용하여 [Platform::Exception](../cppcx/platform-string-class.md)을 선언할 수 있습니다. HRESULT 매개 변수 또는 HRESULT 매개 변수와 `Platform::String^` 매개 변수를 사용하는 두 [Exception::CreateException 메서드](../cppcx/exception-createexception-method.md) 오버로드 중 하나를 사용하여 예외를 선언할 수도 있습니다.  
  
## 표준 예외  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 일반적인 HRESULT 오류를 나타내는 표준 예외 집합을 지원합니다. 각 표준 예외는 [Platform::COMException](../cppcx/platform-comexception-class.md)에서 파생되고, 이는 `Platform::Exception`에서 파생됩니다. ABI 경계를 넘어 예외를 throw할 경우 표준 예외 중 하나를 throw해야 합니다.  
  
 사용자 고유의 예외 형식은 `Platform::Exception`에서 파생할 수 없습니다. 사용자 지정 예외를 throw하려면 사용자 정의 HRESULT를 사용하여 `COMException` 개체를 생성하세요.  
  
 다음 표에서는 표준 예외를 보여 줍니다.  
  
|이름|내부 HRESULT|설명|  
|--------|----------------|--------|  
|COMException|*사용자 정의 hresult*|COM 메서드 호출에서 인식할 수 없는 HRESULT가 반환되는 경우에 throw됩니다.|  
|AccessDeniedException|E\_ACCESSDENIED|리소스 또는 기능에 대한 액세스가 거부된 경우 throw됩니다.|  
|ChangedStateException|E\_CHANGED\_STATE|부모 컬렉션이 변경된 후 컬렉션 반복기 또는 컬렉션 뷰의 메서드가 호출되어 메서드 결과가 무효화되면 throw됩니다.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|COM 클래스가 등록되지 않은 경우 throw됩니다.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|개체와 클라이언트의 연결이 끊기면 throw됩니다.|  
|FailureException|E\_FAIL|작업이 실패하면 throw됩니다.|  
|InvalidArgumentException|E\_INVALIDARG|메서드에 제공된 인수 중 하나가 유효하지 않을 때 throw됩니다.|  
|InvalidCastException|E\_NOINTERFACE|형식이 다른 형식에 대한 캐스트가 될 수 없는 경우 throw됩니다.|  
|NotImplementedException|E\_NOTIMPL|클래스에 인터페이스 메서드가 구현되어 있지 않은 경우 throw됩니다.|  
|NullReferenceException|E\_POINTER|null 개체 참조를 역참조하려고 할 때 throw됩니다.|  
|ObjectDisposedException|RO\_E\_CLOSED|삭제된 개체에서 연산이 수행될 때 throw됩니다.|  
|OperationCanceledException|E\_ABORT|작업이 중단되면 throw됩니다.|  
|OutOfBoundsException|E\_BOUNDS|작업이 유효한 범위를 벗어난 데이터에 액세스하려고 하면 throw됩니다.|  
|OutOfMemoryException|E\_OUTOFMEMORY|메모리가 부족하여 작업을 완료할 수 없는 경우 throw됩니다.|  
|WrongThreadException|RPC\_E\_WRONG\_THREAD|프록시 개체용 인터페이스 포인터를 통해 스레드의 아파트에 속하지 않는 스레드가 호출될 경우 throw됩니다.|  
  
## HResult 및 Message 속성  
 모든 예외에는 [HResult](../cppcx/comexception-hresult-property.md) 속성과 [Message](../cppcx/comexception-message-property.md) 속성이 있습니다.[Exception::HResult](../cppcx/exception-hresult-property.md) 속성은 예외의 내부 숫자 HRESULT 값을 가져옵니다.[Exception::Message](../cppcx/exception-message-property.md) 속성은 예외를 설명하는 시스템 제공 문자열을 가져옵니다.[!INCLUDE[win8](../cppcx/includes/win8-md.md)]에서 이 메시지는 디버거에서만 사용할 수 있으며 읽기 전용입니다. 즉, 예외를 다시 throw할 때 변경할 수 없습니다.[!INCLUDE[win81](../cppcx/includes/win81-md.md)]에서 이 메시지 문자열을 프로그래밍 방식으로 액세스하고 해당 예외를 다시 throw하는 경우 새 메시지를 제공할 수 있습니다. 비동기 메서드 호출에 대한 호출 스택을 포함하여 디버거에서 보다 나은 호출 스택 정보를 사용할 수 있습니다.  
  
## 예제  
 이 예제에서는 동기 작업에 대한 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 예외를 throw하는 방법을 보여 줍니다.  
  
 [!code-cpp[cx_exceptions#01](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#01)]  
  
 다음 예제에서는 예외를 catch하는 방법을 보여 줍니다.  
  
 [!code-cpp[cx_exceptions#02](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#02)]  
  
 비동기 작업 중에 throw된 예외를 catch하려면 작업 클래스를 사용하여 오류 처리 연속을 추가합니다. 오류 처리 연속은 다른 스레드에서 throw된 예외를 다시 호출 스레드로 마샬링하므로 모든 잠재적 예외를 코드의 한 지점에서 처리할 수 있습니다. 자세한 내용은 [C\+\+의 비동기 프로그래밍](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx)을 참조하세요.  
  
## UnhandledErrorDetected 이벤트  
 [!INCLUDE[win81](../cppcx/includes/win81-md.md)]에서 프로세스를 중단시키는 처리되지 않은 오류에 대한 액세스를 제공하는 [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx) 정적 이벤트를 구독할 수 있습니다. 오류가 발생한 위치와 관계없이 이벤트 인수와 함께 전달되는 [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) 개체로 이 처리기에 수신됩니다. 개체에서 `Propagate`를 호출하면 해당 개체가 오류 코드에 해당하는 형식의 `Platform::*Exception`을 만들고 throw합니다. Catch 블록에서는 필요한 경우 사용자 상태를 저장할 수 있으며, 그런 다음 `throw`를 호출하여 프로세스가 종료되도록 허용하거나 프로그램을 알려진 상태로 되돌리기 위한 작업을 수행합니다. 다음 예제에서는 기본 패턴을 보여 줍니다.  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
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
  
## 설명  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서는 `finally` 절을 사용하지 않습니다.  
  
## 참고 항목  
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)   
 [네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)