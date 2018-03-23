---
title: Windows 런타임 c + + 템플릿 라이브러리 (WRL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d362fdde185f5d9345977ca58d7679a448976555
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows 런타임 C++ 템플릿 라이브러리(WRL)
WRL(Windows 런타임 C++ 템플릿 라이브러리)은 Windows 런타임 구성 요소를 만들고 사용하기 위한 간단한 방법을 제공하는 템플릿 라이브러리입니다.

> [!NOTE]
> WRL은 이제 대체 C + + /cli WinRT, 표준 C + + 17 언어 프로젝션 Windows 런타임 Api에 대 한 합니다. C + + /cli WinRT는 Windows 10 SDK 부터는 1803 버전에서 사용할 수 있습니다. C + + /cli WinRT 헤더 파일에서 완전히 구현 되며 하 게 고급 액세스 권한이 있는 최신 Windows API를 제공 합니다.

> C + + /cli WinRT, 둘 다 사용 하는 모든 표준 호환 C + + 17 컴파일러를 사용 하 여 Windows 런타임 Api를 작성 합니다. C + + /cli WinRT에서 일반적으로 더 나은 성능을 제공 하 고 Windows 런타임에 대 한 다른 언어 옵션 보다 더 작은 이진 파일을 생성 합니다. 우리는 계속 지원 C + + /CX 및 WRL, 되지만 매우 권장 구성이 새 응용 프로그램에서 사용할 C + + /cli WinRT 합니다. 자세한 내용은 참조 [C + + /cli WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)합니다.   
  
## <a name="benefits"></a>이점  
 Windows 런타임 c + + 템플릿 라이브러리를 사용 하면 보다 손쉽게 구현 하 고 구성 요소 개체 모델 (COM) 구성 요소를 사용할 수 있습니다. 이 라이브러리는 개체의 수명을 관리하기 위해 참조 횟수와 같은 관리 기법을 제공하며, 작업의 성공 또는 실패를 확인하기 위한 테스트 `HRESULT` 값을 제공합니다. Windows 런타임 c + + 템플릿 라이브러리를 사용 하려면 이러한 규칙과 기법 신중 하 게 수행 해야 합니다.  
  
 C + + /cli CX는 Windows 런타임 구성 요소를 사용 하는, 언어 기반의 고급 방법입니다. Windows 런타임 c + + 템플릿 라이브러리와 C + + /cli CX 자동으로 사용자 대신 관리 작업을 수행 하 여 Windows 런타임에 대 한 코드의 작성을 단순화 합니다.  
  
 Windows 런타임 c + + 템플릿 라이브러리 및 C + + /cli CX 서로 다른 이점을 제공 합니다. 대신 C + Windows 런타임 c + + 템플릿 라이브러리를 사용 하려면 몇 가지 이유는 + / CX:  
  
-   Windows 런타임 c + + 템플릿 라이브러리는 약간의 추상화를 통해 Windows 런타임 응용 프로그램 이진 인터페이스 (ABI)를 추가, 제공 기본 코드 더 나은를 제어 하는 기능을 만들거나 Windows 런타임 Api를 사용 합니다.  
  
-   C + + /cli CX 나타내는 COM `HRESULT` 값을 예외로 합니다. COM, 또는 예외를 사용 하지 않는 사용 하는 코드 베이스를 상속 받을 경우 예외를 사용할 필요가 없기 때문에 Windows 런타임와 작동 하는 더 자연 스러운 방법을 Windows 런타임 c + + 템플릿 라이브러리는 경우가 있습니다.  
  
    > [!NOTE]
    >  Windows 런타임 c + + 템플릿 라이브러리를 사용 하 여 `HRESULT` 값 및 예외를 throw 하지 않습니다. 또한 Windows 런타임 c + + 템플릿 라이브러리를 사용 하 여 스마트 포인터와 RAII 패턴 응용 프로그램 코드가 예외를 throw 하는 경우 개체는 올바르게 제거 되도록 합니다. 스마트 포인터와 RAII에 대 한 자세한 내용은 참조 하십시오. [스마트 포인터](../cpp/smart-pointers-modern-cpp.md) 및 [개체 자체 리소스 (RAII)](../cpp/objects-own-resources-raii.md)합니다.  
  
-   용도 디자인의 Windows 런타임 c + + 템플릿 라이브러리는 영감을 얻은으로 ATL 액티브 템플릿 라이브러리 (), COM 개체의 프로그래밍을 단순화 하는 템플릿 기반 c + + 클래스 집합인 합니다. Windows 런타임 c + + 템플릿 라이브러리를 래핑하는 Windows 런타임에서 표준 c + +를 사용 하므로 더 쉽게 포트 고 기존의 많은 COM 구성 요소는 Windows 런타임으로 ATL 작성 된 상호 작용할 수 있습니다. ATL를 이미 알고 Windows 런타임 c + + 템플릿 라이브러리 프로그래밍이 더 쉬울 것을 확인할 수 있습니다.  
  
## <a name="getting-started"></a>시작  
 다음은 Windows 런타임 c + + 템플릿 라이브러리를 바로 사용할 수 있는 몇 가지 리소스입니다.  
  
 [Windows 런타임 라이브러리 (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 이 채널 9 비디오에서 자세히 방법에 대 한 Windows 런타임 c + + 템플릿 라이브러리 Windows 런타임 구성 요소를 사용 하는 방법 및 유니버설 Windows 플랫폼 (UWP) 앱을 작성 합니다.  
  
 [방법: 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 Windows 런타임을 초기화 및 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여 Windows 런타임 c + + 템플릿 라이브러리를 사용 하는 방법을 보여 줍니다.  
  
 [방법: 비동기 작업 완료](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 Windows 런타임 c + + 템플릿 라이브러리를 사용 하 여 비동기 작업을 시작 하 고 작업 완료 시 작업을 수행 하는 방법을 보여 줍니다.  
  
 [방법: 이벤트 처리](../windows/how-to-handle-events-using-wrl.md)  
 구독 하 고 Windows 런타임 개체의 이벤트를 처리 하는 Windows 런타임 c + + 템플릿 라이브러리를 사용 하는 방법을 보여 줍니다.  
  
 [연습: WRL 및 미디어 파운데이션을 사용하여 UWP 앱 만들기](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 사용 하는 UWP 앱을 만드는 방법을 배울 [Microsoft 미디어 파운데이션](http://msdn.microsoft.com/library/windows/apps/ms694197)합니다.  
  
 [방법: 기본 COM 구성 요소 만들기](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 Windows 런타임 c + + 템플릿 라이브러리를 기본 COM 구성 요소를 만들고 등록 하 고 데스크톱 앱에서 COM 구성 요소를 사용 하는 기본 방법을 사용 하는 방법을 보여 줍니다.  
  
 [방법: 직접 WRL 구성 요소 인스턴스화](../windows/how-to-instantiate-wrl-components-directly.md)  
 사용 하는 방법에 알아봅니다는 [Microsoft::WRL::Make](../windows/make-function.md) 및 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) 를 정의 하는 모듈에서 구성 요소를 인스턴스화하는 함수입니다.  
  
 [방법: winmdidl.exe 및 midlrt.exe를 사용하여 Windows 메타데이터에서 .h 파일 만들기](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 .winmd 메타데이터에서 IDL 파일을 만들어 WRL의 사용자 지정 Windows 런타임 구성 요소를 사용하는 방법을 살펴봅니다.  
  
 [연습: 작업 및 XML HTTP 요청을 사용하여 연결](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 사용 하는 방법을 보여 줍니다.는 [IXMLHTTPRequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) 및 [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) UWP 앱에서 웹 서비스에 HTTP GET 및 POST 요청을 보낼 함께 인터페이스입니다.  
  
 [Bing 지도 여행 최적화 프로그램 샘플](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 사용 하 여는 `HttpRequest` 클래스에 정의 된 [연습:를 사용 하 여 작업 연결 및 XML HTTP 요청](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) 전체 UWP 앱의 컨텍스트에서 합니다.  
  
 [C + + 샘플을 사용 하 여 Windows 런타임 DLL 구성 요소 만들기](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 in-process DLL 구성 요소를 만들고 C +에서 사용 하는 Windows 런타임 c + + 템플릿 라이브러리를 사용 하는 방법을 보여 줍니다. + /CX, JavaScript 및 C#입니다.  
  
 [DirectX marble maze 게임 샘플](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 3d 게임 관점 전체 컨텍스트에서 DirectX 및 미디어 파운데이션 같은 COM 구성 요소의 수명을 관리 하는 Windows 런타임 c + + 템플릿 라이브러리를 사용 하는 방법을 보여 줍니다.  
  
 [데스크톱 응용 프로그램 샘플에서 알림 메시지 보내기](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 데스크톱 응용 프로그램의 알림을 사용 하려면 Windows 런타임 c + + 템플릿 라이브러리를 사용 하는 방법을 보여 줍니다.  
  
## <a name="windows-runtime-c-template-library-compared-to-atl"></a>과 ATL의 비교 하는 Windows 런타임 c + + 템플릿 라이브러리  
 작고 빠른 COM 개체 만들기를 사용할 수 있으므로 Windows 런타임 c + + 템플릿 라이브러리 액티브 템플릿 라이브러리 (ATL)을 유사 합니다. Windows 런타임 c + + 템플릿 라이브러리 및 ATL 또한 인터페이스의 명시적 등록, 모듈의 개체 정의와 같은 개념을 공유 하 고 개체 개방 생성 팩터리를 사용 하 여 합니다. Atl 익숙하다면 모두에 Windows 런타임 c + + 템플릿 라이브러리 수도 있습니다.  
  
 Windows 런타임 c + + 템플릿 라이브러리는 UWP 앱에 필요한 COM 기능을 지원 합니다. 따라서 다음과 같은 COM 기능에 대한 직접 지원이 생략된다는 점에서 ATL과 구별됩니다.  
  
-   집계  
  
-   재고 구현  
  
-   이중 인터페이스(`IDispatch`)  
  
-   표준 열거자 인터페이스  
  
-   연결 지점  
  
-   분리 인터페이스  
  
-   OLE 포함  
  
-   ActiveX 컨트롤  
  
-   COM+  
  
## <a name="concepts"></a>개념  
 Windows 런타임 c + + 템플릿 라이브러리에는 몇 가지 기본 개념을 나타내는 형식을 제공 합니다. 다음 단원에서는 이러한 형식에 대해 설명합니다.  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md) 는 *스마트 포인터* 템플릿 매개 변수로 지정 된 인터페이스를 나타내는 형식입니다. `ComPtr` 을 사용하여 인터페이스에서 파생된 개체의 멤버를 액세스할 수 있는 변수를 정의합니다. `ComPtr`은 기본 인터페이스 포인터의 참조 개수를 자동으로 관리하여 참조 횟수가 0이 되면 인터페이스를 릴리스합니다.  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md) 일련의 지정 된 인터페이스를 상속 하는 인스턴스화된 클래스를 나타냅니다. A `RuntimeClass` 개체가 하나 이상의 Windows 런타임 COM 인터페이스 또는 구성 요소에 대 한 약한 참조에 대 한 지원의 조합을 제공할 수 있습니다.  
  
### <a name="module"></a>Module  
 [모듈](../windows/module-class.md) 관련된 개체의 컬렉션을 나타냅니다. `Module` 개체는 개체를 생성하는 클래스 팩터리와, 다른 응용 프로그램이 개체를 사용할 수 있도록 하는 등록을 관리합니다.  
  
### <a name="callback"></a>Callback  
 [콜백](../windows/callback-function-windows-runtime-cpp-template-library.md) 함수 멤버 함수가 이벤트 처리기 (콜백 메서드)가 개체를 생성 합니다. `Callback` 함수를 사용하여 비동기 작업을 작성합니다.  
  
### <a name="eventsource"></a>EventSource  
 [EventSource](../windows/eventsource-class.md) 관리 하는 데는 *위임* 이벤트 처리기입니다. Windows 런타임 c + + 템플릿 라이브러리를 사용 하 여 대리자를 구현 하 여 사용할 `EventSource` 추가, 제거 및 대리자를 호출 합니다.  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md) Windows 런타임 비동기 프로그래밍 모델을 나타내는 가상 메서드를 제공 합니다. 비동기 작업을 시작, 중지하거나 작업의 진행률을 확인할 수 있는 사용자 지정 클래스를 만들려면 이 클래스의 멤버를 재정의합니다.  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md) 자유 스레드된 마샬러 개체를 나타냅니다. `FtmBase`는 GIT(전역 인터페이스 테이블)을 생성하고 마샬링 및 프록시 개체의 관리를 지원합니다.  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md) 나타내는 스마트 포인터 형식이 *약한 참조*, 하거나 액세스 하지 못할 수 있는 개체를 참조 하 합니다. A `WeakRef` 클래식 COM. 아니라에 Windows 런타임에만에 의해 개체를 사용할 수 있습니다  
  
 `WeakRef` 개체는 일반적으로 외부 스레드나 응용 프로그램에서 제어하는 개체를 나타냅니다. 예를 들어 `WeakRef` 개체는 파일 개체를 참조할 수 있습니다. 파일을 열면 `WeakRef` 가 유효해지고 참조 파일을 액세스할 수 있게 됩니다. 하지만 파일이 닫히면 `WeakRef` 가 무효가 되고 파일을 액세스할 수 없게 됩니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|||  
|-|-|  
|[범주별 키 Api](../windows/key-wrl-apis-by-category.md)|기본 Windows 런타임 c + + 템플릿 라이브러리 형식, 함수 및 매크로 강조 표시합니다.|  
|[참조](../windows/wrl-reference.md)|Windows 런타임 c + + 템플릿 라이브러리에 대 한 참조 정보를 포함합니다.|  
|[빠른 참조 (Windows 런타임 및 Visual c + +)](http://go.microsoft.com/fwlink/p/?linkid=229180)|간략하게 설명 하는 C + + /cli CX 기능에는 Windows 런타임에서 지원 합니다.|  
|[Visual c + +에서 Windows 런타임 구성 요소를 사용 하 여](http://go.microsoft.com/fwlink/p/?linkid=229155)|에서는 사용 하 여 C + + /CX 기본적인 Windows 런타임 구성 요소를 합니다.|