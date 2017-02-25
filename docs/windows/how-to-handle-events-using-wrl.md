---
title: "방법: WRL을 사용하여 이벤트 처리 | Microsoft Docs"
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
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: WRL을 사용하여 이벤트 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 설명하기 위한 [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) 을 어떻게 사용하는지 보여주고 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 개체의 이벤트 처리기를 보여줍니다.  
  
 해당 구성 요소의 인스턴스를 만들고 속성 값을 검색 하는 기본 예제를 보려면 [방법: Windows 런타임 구성 요소 활성화 및 사용](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## 구독 및 이벤트 처리  
 다음 단계는 `ABI::Windows::System::Threading::IDeviceWatcher` 개체를 시작하고 이벤트 처리기를 사용하여 진행률을 모니터링 합니다.  `IDeviceWatcher` 인터페이스를 사용하면 백그라운드에서 비동기적으로 또는 장치를 열거하고 장치의 추가, 제거 또는 변경 될 때 알림을 받을 수 있습니다.  [콜백](../windows/callback-function-windows-runtime-cpp-template-library.md) 함수는이 예제에서 중요 한 부분은 백그라운드 작업의 결과를 처리하는 이벤트 처리기를 지정할 수 있습니다.  다음은 완성된 예제입니다.  
  
> [!WARNING]
>  일반[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에서, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 를 일반적으로 사용하더라도, 이 예제는 설명을 위해 콘솔 응용프로그램을 사용합니다.  `wprintf_s` 와 같은 함수는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램으로부터 사용가능 하지 않습니다.  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에서 사용할 수 있는 형식과 함수에 대한 자세한 설명은, [\/ZW를 사용한 CRT 함수 를 지원하지 않습니다.](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) 및 [윈도우 스토어 앱에 대한 Win32 및 COM](http://msdn.microsoft.com/library/windows/apps/br205757.aspx)을 참조하십시오.  
  
1.  모든 필수 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 또는 표준 C\+\+ 라이브러리 헤더를 포함\(`#include`\)합니다.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h 장치를 열거하는 데 필요한 형식을 선언 합니다.  
  
     .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  응용 프로그램에 대한 지역 변수를 선언 합니다.  이 예제 열거 장치 및 나중에 이벤트에서 등록을 취소할 수 있는 등록 토큰 수를 보유 합니다.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]를 초기화합니다.  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  메인 응용프로그램에 대한 열거 프로세스의 완료를 동기화 시킨 [이벤트](../windows/event-class-windows-runtime-cpp-template-library.md) 개체를 생성합니다.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  이 이벤트는 콘솔 응용 프로그램의 일부로 데모입니다.  이 예제에서는 이벤트를 사용하여 응용 프로그램 종료하기 전에 비동기 작업이 완료를 보장합니다.  대부분의 응용 프로그램에 일반적으로 기다리는 비동기 작업을 완료 합니다.  
  
5.  `IDeviceWatcher` 인터페이스를 위한 정품 인증 공장을 생성합니다.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 정규화 된 이름을 사용하여 형식을 식별 합니다.  `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` 매개 변수가 제공하는 문자열은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 필요한 런타임 클래스 이름을 포함 합니다.  
  
6.  `IDeviceWatcher` 개체를 만듭니다.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  `Callback` 함수를 `Added`, `EnumerationCompleted` 및 `Stopped` 이벤트를 등록하기 위해 사용합니다.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     `Added` 이벤트 처리기의 열거된 장치 수를 증가시킵니다.  10 개의 장치를 찾은 후 열거형 프로세스를 중지 합니다.  
  
     `Stopped` 이벤트 처리기는 이벤트 처리기를 제거하고 완료 이벤트를 설정합니다.  
  
     `EnumerationCompleted` 이벤트 처리기 열거형 프로세스를 중지 합니다.  10 개 이하의 장치가 없는 경우에 이 이벤트를 처리 했습니다.  
  
    > [!TIP]
    >  콜백을 정의하는 람다식을 사용하는 예제.  함수 포인터, 함수 객체 \(functors\)를 사용할 수도 있습니다, 또는 [std::function](../standard-library/function-class.md) 개체입니다.  람다 식에 대한 자세한 내용은 [람다 식](../cpp/lambda-expressions-in-cpp.md)을 참조하십시오.  
  
8.  열거 프로세스를 시작 합니다.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. 열거 프로세스를 완료하고 다음 메시지가 인쇄될 때까지 기다립니다.  모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 전체 예제는 다음과 같습니다:  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## 코드 컴파일  
 코드를 컴파일 하기 위하여, 복사하고 그때 Visual Studio 프로젝트에서 복사합니다, 또는 `wrl-consume-events.cpp` 이름의 파일에서 복사하고 그때 Visual Studio 명령어 프롬트 창에서 다음 명령어를 실행합니다.  
  
 **cl.exe wrl\-consume\-events.cpp runtimeobject.lib**  
  
## 참고 항목  
 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)