---
title: "방법: WRL을 사용 하 여 이벤트를 처리 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3341992ce2b10897fca165a787e568b5e0bc660
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-handle-events-using-wrl"></a>방법: WRL을 사용하여 이벤트 처리
이 문서에 Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하 여 구독 하 고 Windows 런타임 개체의 이벤트를 처리 하는 방법을 보여 줍니다.  
  
 해당 구성 요소의 인스턴스를 만들고 속성 값을 검색 하는 더 기본적인 예제를 보려면 [하는 방법: 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)합니다.  
  
## <a name="subscribing-to-and-handling-events"></a>구독 하 고 이벤트 처리  
 다음 단계를 시작 프로그램 `ABI::Windows::System::Threading::IDeviceWatcher` 개체 및 이벤트 처리기를 사용 하 여 진행 상황을 모니터링 합니다. `IDeviceWatcher` 인터페이스를 사용 하면 백그라운드에서 비동기적으로 또는 장치를 열거 하 고 장치 추가, 제거 또는 변경 하는 경우 알림을 받을 수 있습니다. [콜백](../windows/callback-function-windows-runtime-cpp-template-library.md) 함수는이 예의 중요 한 부분을 백그라운드 작업의 결과 처리 하는 이벤트 처리기를 지정할 수 있습니다. 전체 예제와 같습니다.  
  
> [!WARNING]
>  유니버설 Windows 플랫폼 앱에서 Windows 런타임 c + + 템플릿 라이브러리를 일반적으로 사용 되지만이 예제에 대 한 예시는 콘솔 응용 프로그램을 사용 합니다. 와 같은 함수가 `wprintf_s` 는 유니버설 Windows 플랫폼 앱에서 사용할 수 없습니다. 형식 및 유니버설 Windows 플랫폼 앱에서 사용할 수 있는 함수에 대 한 자세한 내용은 참조 [CRT 함수는 /zw에서 지원 되지 않습니다](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) 및 [Win32 및 COM에 대 한 Windows 스토어 앱](http://msdn.microsoft.com/library/windows/apps/br205757.aspx)합니다.  
  
1.  포함 (`#include`) Windows 런타임, Windows 런타임 c + + 템플릿 라이브러리 또는 c + + 표준 라이브러리 헤더 필수입니다.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h 장치를 열거 하는 데 필요한 형식을 선언 합니다.  
  
     .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  응용 프로그램에 대 한 지역 변수를 선언 합니다. 이 예제에서는 열거 된 장치 및 등록 토큰 수 있게 이벤트에서 나중에 구독을 취소 하는 수의 개수를 보유 합니다.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  Windows 런타임을 초기화 합니다.  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  만들기는 [이벤트](../windows/event-class-windows-runtime-cpp-template-library.md) 를 주 앱은 열거 프로세스의 완료를 동기화 하는 개체입니다.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  이 이벤트는 콘솔 응용 프로그램의 일부로 데모 목적입니다. 이 예제에서는 이벤트를 사용 하 여 응용 프로그램 종료 되기 전에 비동기 작업이 완료 되도록 합니다. 대다수 앱에서 일반적으로 하지 않는 기다리는 비동기 작업이 완료 합니다.  
  
5.  에 대 한 활성화 팩터리를 만들어는 `IDeviceWatcher` 인터페이스입니다.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     Windows 런타임 정규화 된 이름을 사용 하 여 형식을 식별 합니다. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` 매개 변수는 Windows 런타임에서 제공 하 고 필요한 런타임 클래스 이름을 포함 하는 문자열입니다.  
  
6.  만들기는 `IDeviceWatcher` 개체입니다.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  사용 하 여는 `Callback` 구독할 함수는 `Added`, `EnumerationCompleted`, 및 `Stopped` 이벤트입니다.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     `Added` 이벤트 처리기의 열거 된 장치 수를 증가 시킵니다. 10 개의 장치를 찾지 못한 이후 열거 프로세스를 중지 합니다.  
  
     `Stopped` 이벤트 처리기는 이벤트 처리기를 제거 하 고 완료 이벤트를 설정 합니다.  
  
     `EnumerationCompleted` 이벤트 처리기 열거 프로세스를 중지 합니다. 10 개 이하의 장치가 없는 경우이 이벤트를 처리 했습니다.  
  
    > [!TIP]
    >  이 예제에서는 콜백을 정의 하는 람다 식을 사용 합니다. 함수 포인터, 함수 개체 (함수)을 사용할 수 있습니다 또는 [std:: function](../standard-library/function-class.md) 개체입니다. 람다 식에 대한 자세한 내용은 [람다 식](../cpp/lambda-expressions-in-cpp.md)을 참조하세요.  
  
8.  열거 프로세스를 시작 합니다.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. 열거 프로세스를 완료 하 고 다음 메시지를 출력 될 때까지 기다립니다. 모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 전체 예제는 다음과 같습니다.  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `wrl-consume-events.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe wrl 소비 events.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 C++ 템플릿 라이브러리(WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)