---
title: '방법: WRL을 사용 하 여 비동기 작업 완료 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fff0a6e98dd6fdd28b1fbc2e9146d5b68975e0f0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>방법: WRL을 사용하여 비동기 작업 완료
이 문서에서는 Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하 여 비동기 작업을 시작 하 고 작업 완료 시 작업을 수행 하는 방법을 보여 줍니다.  
  
 이 문서에서는 두 가지 예를 보여 줍니다. 비동기 타이머를 시작 하 고 타이머가 만료 될 때까지 대기 하는 첫 번째 예제입니다. 이 예제에서는 타이머 개체를 만들 때 비동기 동작을 지정 합니다. 두 번째 예제에서는 백그라운드 작업자 스레드를 실행합니다. 반환 하는 Windows 런타임 메서드를 사용 하는 방법을 보여 주는이 예제는 `IAsyncInfo` 인터페이스입니다. [콜백](../windows/callback-function-windows-runtime-cpp-template-library.md) 비동기 작업의 결과 처리할 이벤트 처리기를 지정 수 있기 때문에 함수는 두 예제 모두의 중요 한 부분입니다.  
  
 구성 요소의 인스턴스를 만들고 속성 값을 검색 하는 더 기본적인 예제를 보려면 [하는 방법: 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)합니다.  
  
> [!TIP]
>  이 예에서는 콜백을 정의 하려면 람다 식을 사용 합니다. 함수 포인터, 함수 개체 (함수)을 사용할 수 있습니다 또는 [std:: function](../standard-library/function-class.md) 개체입니다. C + + 람다 식에 대 한 자세한 내용은 참조 [람다 식](../cpp/lambda-expressions-in-cpp.md)합니다.  
  
## <a name="example-working-with-a-timer"></a>예: 타이머 작업  
 다음 단계 비동기 타이머를 시작 하 고 타이머가 만료 될 때까지 대기 합니다. 전체 예제와 같습니다.  
  
> [!WARNING]
>  일반적으로 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 Windows 런타임 c + + 템플릿 라이브러리를 사용 되지만이 예제에 대 한 예시는 콘솔 응용 프로그램을 사용 합니다. 와 같은 함수가 `wprintf_s` 는 UWP 앱에서 사용할 수 없습니다. 형식 및 UWP 앱에서 사용할 수 있는 함수에 대 한 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 및 [UWP 앱 용 Win32 및 COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)합니다.  
  
1.  포함 (`#include`) Windows 런타임, Windows 런타임 c + + 템플릿 라이브러리 또는 c + + 표준 라이브러리 헤더 필수입니다.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Windows.System.Threading.h 비동기 타이머를 사용 하는 데 필요한 형식을 선언 합니다.  
  
     .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  Windows 런타임을 초기화 합니다.  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  에 대 한 활성화 팩터리를 만들어는 `ABI::Windows::System::Threading::IThreadPoolTimer` 인터페이스입니다.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     Windows 런타임 정규화 된 이름을 사용 하 여 형식을 식별 합니다. `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` 매개 변수는 Windows 런타임에서 제공 하 고 필요한 런타임 클래스 이름을 포함 하는 문자열입니다.  
  
4.  만들기는 [이벤트](../windows/event-class-windows-runtime-cpp-template-library.md) 타이머 콜백 기본 응용 프로그램을 동기화 하는 개체입니다.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  이 이벤트는 콘솔 응용 프로그램의 일부로 데모 목적입니다. 이 예제에서는 이벤트를 사용 하 여 응용 프로그램 종료 되기 전에 비동기 작업이 완료 되도록 합니다. 대다수 앱에서 일반적으로 하지 않는 기다리는 비동기 작업이 완료 합니다.  
  
5.  만들기는 `IThreadPoolTimer` 2 초 후에 만료 되는 개체입니다. 사용 하 여는 `Callback` 이벤트 처리기를 만들 함수 (한 `ABI::Windows::System::Threading::ITimerElapsedHandler` 개체).  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  콘솔에 메시지를 인쇄 하 고 타이머 콜백이 완료 될 때까지 기다립니다. 모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 전체 예제는 다음과 같습니다.  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `wrl-consume-async.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe wrl-consume-async.cpp runtimeobject.lib**  
  
## <a name="example-working-with-a-background-thread"></a>예: 백그라운드 스레드 작업  
 다음 단계 작업자 스레드를 시작 하 고 해당 스레드에 의해 수행 되는 작업을 정의 합니다. 전체 예제와 같습니다.  
  
> [!TIP]
>  사용 하는 방법을 보여 주는이 예제는 `ABI::Windows::Foundation::IAsyncAction` 인터페이스입니다. 구현 하는 모든 인터페이스에이 패턴을 적용할 수 있습니다 `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation`, 및 `IAsyncOperationWithProgress`합니다.  
  
1.  포함 (`#include`) Windows 런타임, Windows 런타임 c + + 템플릿 라이브러리 또는 c + + 표준 라이브러리 헤더 필수입니다.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Windows.System.Threading.h는 작업자 스레드를 사용 하는 데 필요한 형식을 선언 합니다.  
  
     사용 하는 것이 좋습니다는 `using namespace` 코드를 더 쉽게 읽을 수 있도록.cpp 파일의 지시문입니다.  
  
2.  Windows 런타임을 초기화 합니다.  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  에 대 한 활성화 팩터리를 만들어는 `ABI::Windows::System::Threading::IThreadPoolStatics` 인터페이스입니다.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  만들기는 [이벤트](../windows/event-class-windows-runtime-cpp-template-library.md) 작업자 스레드를 주 앱은의 완료를 동기화 하는 개체입니다.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  이 이벤트는 콘솔 응용 프로그램의 일부로 데모 목적입니다. 이 예제에서는 이벤트를 사용 하 여 응용 프로그램 종료 되기 전에 비동기 작업이 완료 되도록 합니다. 대다수 앱에서 일반적으로 하지 않는 기다리는 비동기 작업이 완료 합니다.  
  
5.  호출 된 `IThreadPoolStatics::RunAsync` 작업자 스레드를 만드는 메서드. 사용 하 여는 `Callback` 동작을 정의 하는 함수입니다.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     `IsPrime` 뒤에 전체 예제에 함수가 정의 되어 있습니다.  
  
6.  콘솔에 메시지를 인쇄 하 고 스레드가을 완료할 때까지 기다립니다. 모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 전체 예제는 다음과 같습니다.  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `wrl-consume-asyncOp.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe wrl 소비 asyncOp.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 C++ 템플릿 라이브러리(WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)
