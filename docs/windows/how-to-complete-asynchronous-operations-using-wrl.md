---
title: "방법: WRL을 사용하여 비동기 작업 완료 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: WRL을 사용하여 비동기 작업 완료
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 어떻게 [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) 를 비동기 작업을 시작하고 작업이 완료될때 작업을 실행하는데 사용하는 지를 보여줍니다.  
  
 이 문서는 두 가지 예를 보여 줍니다.  첫 번째 예제에서는 비동기 타이머를 시작하고 타이머가 만료될 때까지 기다립니다.  이 예제에서는 타이머 개체를 만들 때 비동기 작업을 지정 합니다.  두 번째 예제에서는 백그라운드 작업자 스레드를 실행합니다.  이 예제는 `IAsyncInfo` 인터페이스를 반환하는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 메서드를 사용하여 어떻게 작업할지를 보여줍니다.  [Callback](../windows/callback-function-windows-runtime-cpp-template-library.md) 함수는 두 예시의 중요한 부분입니다.왜냐하면 이벤트 핸들러를 비동기 작업의 결과를 진행하는데 지정하기 때문입니다.  
  
 해당 구성 요소의 인스턴스를 만들고 속성 값을 검색 하는 기본 예제를 보려면 [방법: Windows 런타임 구성 요소 활성화 및 사용](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  이 예제는 콜백을 정의 하려면 람다 식을 사용 합니다.  함수 포인터, 함수 객체 \(functors\)를 사용할 수도 있습니다, 또는 [std::function](../standard-library/function-class.md) 개체입니다.  C\+\+ 람다 식에 대한 자세한 내용은 [람다 식](../cpp/lambda-expressions-in-cpp.md)을 참조하십시오.  
  
## 예제: 타이머 작업  
 다음 단계는 비동기 타이머를 시작 및 타이머가 만료 될 때까지 기다립니다.  다음은 완성된 예제입니다.  
  
> [!WARNING]
>  일반[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에서, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 를 일반적으로 사용하더라도, 이 예제는 설명을 위해 콘솔 응용프로그램을 사용합니다.  `wprintf_s` 와 같은 함수는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램으로부터 사용가능 하지 않습니다.  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에서 사용할 수 있는 함수와 형식에관한 더 많은 정보는, [CRT functions not supported by \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) 및 [Win32 and COM for Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br205757.aspx)을 참조하십시오.  
  
1.  모든 필수 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 또는 표준 C\+\+ 라이브러리 헤더를 포함\(`#include`\)합니다.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Windows.System.Threading.h는 비동기 타이머를 사용 하는 데 필요한 형식을 선언 합니다.  
  
     .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]를 초기화합니다.  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  `ABI::Windows::System::Threading::IThreadPoolTimer` 인터페이스를 위한 정품 인증 공장을 생성합니다.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 정규화 된 이름을 사용하여 형식을 식별 합니다.  `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` 매개 변수가 제공하는 문자열은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 필요한 런타임 클래스 이름을 포함 합니다.  
  
4.  타이머 콜백을 주요 응용프로그램에 동기화시키는 [이벤트](../windows/event-class-windows-runtime-cpp-template-library.md) 개체를 만듭니다.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  이 이벤트는 콘솔 응용 프로그램의 일부로 데모입니다.  이 예제에서는 이벤트를 사용하여 응용 프로그램 종료하기 전에 비동기 작업이 완료를 보장합니다.  대부분의 응용 프로그램에 일반적으로 기다리는 비동기 작업을 완료 합니다.  
  
5.  2초 후에 만료되는 `IThreadPoolTimer` 개체를 만듭니다.  `Callback` 함수를 이벤트 핸들러 \(`ABI::Windows::System::Threading::ITimerElapsedHandler` 개체\) 를 만들기 위해 사용합니다.  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  콘솔에 메시지를 인쇄하고 타이머 콜백이 완료될 때까지 기다립니다.  모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 전체 예제는 다음과 같습니다:  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### 코드 컴파일  
 코드를 컴파일하기 위하여, 복사하고 그때 Visual Studio 프로젝트에서 복사합니다, 또는 `wrl-consume-async.cpp` 이름의 파일에서 복사하고 그때 Visual Studio 명령어 프롬트 창에서 다음 명령어를 실행합니다.  
  
 **cl.exe wrl\-consume\-async.cpp runtimeobject.lib**  
  
## 예: 백그라운드 스레드를 사용하여 작업합니다.  
 다음 단계는 작업자 스레드를 시작하고 해당 스레드에 의해 수행 되는 동작을 정의합니다.  다음은 완성된 예제입니다.  
  
> [!TIP]
>  이 예제는 `ABI::Windows::Foundation::IAsyncAction` 인터페이스를 사용하여 어떻게 작업할지에 대해 보여줍니다.  인터페이스를 구현 하는이 패턴을 적용할 수 있습니다 `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation`, 및 `IAsyncOperationWithProgress`.  
  
1.  모든 필수 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 또는 표준 C\+\+ 라이브러리 헤더를 포함\(`#include`\)합니다.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Windows.System.Threading.h는 작업자 스레드를 사용하는 데 필요한 형식을 선언 합니다.  
  
     .cpp 파일의 `using namespace` 지시문을 사용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]를 초기화합니다.  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  `ABI::Windows::System::Threading::IThreadPoolStatics` 인터페이스를 위한 정품 인증 공장을 생성합니다.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  주요 응용프로그램에서 작업자 스레드의 완료를 동기화하는 [이벤트](../windows/event-class-windows-runtime-cpp-template-library.md) 개체를 만듭니다.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  이 이벤트는 콘솔 응용 프로그램의 일부로 데모입니다.  이 예제에서는 이벤트를 사용하여 응용 프로그램 종료하기 전에 비동기 작업이 완료를 보장합니다.  대부분의 응용 프로그램에 일반적으로 기다리는 비동기 작업을 완료 합니다.  
  
5.  `IThreadPoolStatics::RunAsync` 를 작업자 스레드를 생성하기 위해 호출합니다.  동작을 정의하기 위해 `Callback` 함수를 사용합니다.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     `IsPrime` 함수는 다음 완료된 예제에서 정의됩니다.  
  
6.  콘솔에 메시지를 인쇄하고 스레드가 완료될 때까지 기다립니다.  모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 전체 예제는 다음과 같습니다:  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### 코드 컴파일  
 코드를 컴파일하기 위하여, 복사하고 그때 Visual Studio 프로젝트에서 복사합니다, 또는 `wrl-consume-asyncOP.cpp` 이름의 파일에서 복사하고 그때 Visual Studio 명령어 프롬트 창에서 다음 명령어를 실행합니다.  
  
 **cl.exe wrl\-consume\-asyncOp.cpp runtimeobject.lib**  
  
## 참고 항목  
 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)