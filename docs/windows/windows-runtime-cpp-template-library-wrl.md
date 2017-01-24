---
title: "Windows 런타임 C++ 템플릿 라이브러리(WRL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 런타임 C++ 템플릿 라이브러리(WRL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)]([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)])는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 만들고 사용하기 위한 간단한 방법을 제공하는 템플릿 라이브러리입니다.  
  
## <a name="benefits"></a>이점  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하면 COM(구성 요소 개체 모델) 구성 요소를 보다 손쉽게 구현하고 사용할 수 있습니다. 이 라이브러리는 개체의 수명을 관리하기 위해 참조 횟수와 같은 관리 기법을 제공하며, 작업의 성공 또는 실패를 확인하기 위한 테스트 `HRESULT` 값을 제공합니다. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]를 활용하려면 이러한 규칙과 기법을 주의하여 따라야 합니다.  
  
 [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)])는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 사용하기 위한 언어 기반의 고급 방법입니다. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 과 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] 는 사용자가 수행할 관리 작업을 자동화함으로써 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 용 코드를 간편하게 작성할 수 있게 해줍니다.  
  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 과 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] 는 서로 다른 장점을 가지고 있습니다. 다음은 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 대신 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]을 사용하는 몇 가지 이유입니다.  
  
-   [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ABI(응용 프로그램 이진 인터페이스)에 약간의 추상화를 추가하므로 기본 코드를 제어하여 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] API를 보다 잘 만들고 사용할 수 있습니다.  
  
-   [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]는 COM `HRESULT` 값을 예외로 나타냅니다. COM을 사용하는 코드베이스나 예외를 사용하지 않는 코드베이스를 상속받을 경우 예외를 사용할 필요가 없기 때문에 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]에 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]을 사용하는 것이 더 쉬울 수 있습니다.  
  
    > [!NOTE]
    >  [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 은 `HRESULT` 값을 사용하며 예외를 throw하지 않습니다. 또한 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 은 응용 프로그램 코드가 예외를 throw할 때 스마트 포인터와 RAII 패턴을 사용하여 개체가 제대로 삭제되도록 합니다. 스마트 포인터와 RAII에 대 한 자세한 내용은 참조 하십시오. [스마트 포인터](../cpp/smart-pointers-modern-cpp.md) 및 [개체 자체 리소스 (RAII)](../cpp/objects-own-resources-raii.md)합니다.  
  
-   [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 의 용도와 디자인은 COM 개체의 프로그래밍을 간편하게 해주는 템플릿 기반의 C++ 클래스 집합인 ATL(액티브 템플릿 라이브러리)을 기반으로 합니다. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 은 표준 C++를 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]을 래핑하기 때문에 ATL로 작성된 기존의 많은 COM 구성 요소를 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에 손쉽게 이식하고 사용할 수 있습니다. ATL에 대해 알고 있을 경우 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 프로그래밍이 더 쉬울 것입니다.  
  
## <a name="getting-started"></a>시작  
 다음은 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 바로 사용할 수 있도록 도와주는 몇 가지 리소스입니다.  
  
 [Windows 런타임 라이브러리 (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 이 채널 9 비디오에서는 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 이 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램 작성을 지원하는 방식과 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 만들고 사용하는 방법에 대해 알아봅니다.  
  
 [방법: 활성화 및 Windows 런타임 구성 요소를 사용 합니다.](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 을 초기화하는 방법과 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 활성화하여 사용하는 방법을 설명합니다.  
  
 [방법: 비동기 작업 완료](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 비동기 작업을 시작하고 작업 완료 시 작업을 수행하는 방법을 설명합니다.  
  
 [방법: 이벤트 처리](../windows/how-to-handle-events-using-wrl.md)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 개체의 이벤트를 구독하고 처리하는 방법을 설명합니다.  
  
 [연습: 기본 Windows 런타임 구성 요소 만들기](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 두 개의 숫자를 추가하는 기본 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 만드는 방법을 설명합니다. 또한 이벤트를 발생시키는 방법과 JavaScript를 사용하는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램의 구성 요소를 사용하는 방법을 보여 줍니다.  
  
 [연습: WRL 및 Media Foundation을 사용 하 여 Windows 스토어 앱 만들기](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] Microsoft 미디어 파운데이션 [을 사용하는](http://msdn.microsoft.com/library/windows/apps/ms694197)앱을 만드는 방법을 알아봅니다.  
  
 [방법: 기본 COM 구성 요소 만들기](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 기본적인 COM 구성 요소를 만드는 방법과 데스크톱 응용 프로그램의 COM 구성 요소를 등록하고 사용하는 기본 방법을 살펴봅니다.  
  
 [방법: 직접 WRL 구성 요소 인스턴스화](../windows/how-to-instantiate-wrl-components-directly.md)  
 [Microsoft::WRL::Make](../windows/make-function.md) 및 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) 함수를 사용하여 구성 요소를 정의하는 모듈의 구성 요소를 인스턴스화하는 방법을 알아봅니다.  
  
 [방법: winmdidl.exe 및 midlrt.exe를 사용 하 여 windows 메타 데이터에서.h 파일을 만들려면](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 .winmd 메타데이터에서 IDL 파일을 만들어 WRL의 사용자 지정 Windows 런타임 구성 요소를 사용하는 방법을 살펴봅니다.  
  
 [연습: 작업 및 XML HTTP 요청을 사용 하 여 연결](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 [IXMLHTTPRequest2](http://msdn.microsoft.com/ko-kr/bbc11c4a-aecf-4d6d-8275-3e852e309908) 및 [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/ko-kr/aa4b3f4c-6e28-458b-be25-6cce8865fc71) 인터페이스를 작업과 함께 사용하여 HTTP GET 및 POST 요청을 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램의 웹 서비스에 보내는 방법을 살펴봅니다.  
  
 [Bing 지도 여행 최적화 프로그램 샘플](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 사용 하는 `HttpRequest` 클래스에 정의 된 [연습:를 사용 하 여 작업 연결 및 XML HTTP 요청](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) 전체의 컨텍스트에서 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램입니다.  
  
 [C + + 샘플을 사용 하 여 Windows 런타임 DLL 구성 요소를 만들기](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 In-process DLL 구성 요소를 만들고 이를 C++/CX, JavaScript 및 C#에서 사용하는 방법을 살펴봅니다.  
  
 [DirectX marble maze 게임 샘플](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 3D 게임 관점에서 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 DirectX 및 미디어 파운데이션과 같은 COM 구성 요소의 수명을 관리하는 방법을 보여 줍니다.  
  
 [데스크톱 응용 프로그램 샘플에서 알림 보내기](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 데스크톱 응용 프로그램의 알림을 사용하는 방법을 보여 줍니다.  
  
## <a name="includecppwrlshorttokencppwrlshortmdmd-compared-to-atl"></a>[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]과 ATL의 비교  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]은 작고 빠른 COM 개체를 만들 수 있다는 점에서 ATL(액티브 템플릿 라이브러리)과 유사합니다. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]와 ATL은 또한 모듈의 개체 정의, 인터페이스의 명시적 등록, 팩터리를 사용하여 개체 개방 생성 등과 같은 개념을 공유합니다. ATL에 익숙할 경우 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]이 편할 수도 있습니다.  
  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]은 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램에 필요한 COM 기능을 지원합니다. 따라서 다음과 같은 COM 기능에 대한 직접 지원이 생략된다는 점에서 ATL과 구별됩니다.  
  
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
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]은 몇 가지 기본 개념을 나타내는 형식을 제공합니다. 다음 단원에서는 이러한 형식에 대해 설명합니다.  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md) 은 템플릿 매개 변수를 통해 지정된 인터페이스를 나타내는 *스마트 포인터* 형식입니다. `ComPtr` 을 사용하여 인터페이스에서 파생된 개체의 멤버를 액세스할 수 있는 변수를 정의합니다. `ComPtr`은 기본 인터페이스 포인터의 참조 개수를 자동으로 관리하여 참조 횟수가 0이 되면 인터페이스를 릴리스합니다.  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md) 는 지정된 인터페이스 집합을 상속받는 인스턴스화된 클래스를 나타냅니다. `RuntimeClass` 개체는 하나 이상의 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] COM 인터페이스에 대한 여러 지원 또는 구성 요소에 대한 약한 참조를 제공할 수 있습니다.  
  
### <a name="module"></a>모듈  
 [Module](../windows/module-class.md) 은 관련 개체의 컬렉션을 나타냅니다. `Module` 개체는 개체를 생성하는 클래스 팩터리와, 다른 응용 프로그램이 개체를 사용할 수 있도록 하는 등록을 관리합니다.  
  
### <a name="callback"></a>Callback  
 [Callback](../windows/callback-function-windows-runtime-cpp-template-library.md) 함수는 멤버 함수가 이벤트 처리기(콜백 메서드)인 개체를 생성합니다. `Callback` 함수를 사용하여 비동기 작업을 작성합니다.  
  
### <a name="eventsource"></a>EventSource  
 [EventSource](../windows/eventsource-class.md) 는 *대리자* 이벤트 처리기를 관리하는 데 사용됩니다. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 을 사용하여 대리자를 구현하고, `EventSource` 를 사용하여 대리자를 추가, 제거 및 호출합니다.  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md) 는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 비동기 프로그래밍 모델을 나타내는 가상의 메서드를 제공합니다. 비동기 작업을 시작, 중지하거나 작업의 진행률을 확인할 수 있는 사용자 지정 클래스를 만들려면 이 클래스의 멤버를 재정의합니다.  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md) 는 자유 스레드된 마샬러 개체를 나타냅니다. `FtmBase`는 GIT(전역 인터페이스 테이블)을 생성하고 마샬링 및 프록시 개체의 관리를 지원합니다.  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md) 는 액세스할 수 있거나 액세스하지 못할 수 있는 개체를 참조하는 *약한 참조*를 나타내는 스마트 포인터 형식입니다. `WeakRef` 개체는 일반 COM이 아닌 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서만 사용할 수 있습니다.  
  
 `WeakRef` 개체는 일반적으로 외부 스레드나 응용 프로그램에서 제어하는 개체를 나타냅니다. 예를 들어 `WeakRef` 개체는 파일 개체를 참조할 수 있습니다. 파일을 열면 `WeakRef` 가 유효해지고 참조 파일을 액세스할 수 있게 됩니다. 하지만 파일이 닫히면 `WeakRef` 가 무효가 되고 파일을 액세스할 수 없게 됩니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|||  
|-|-|  
|[클래스 라이브러리 프로젝트 템플릿](../windows/wrl-class-library-project-template.md)|WRL 클래스 라이브러리 프로젝트 템플릿에 액세스하는 방법을 설명합니다. 이 템플릿을 사용하면 Visual Studio를 사용하여 간편하게 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 만들 수 있습니다.|  
|[범주별 키 Api](../windows/key-wrl-apis-by-category.md)|기본 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 형식, 함수 및 매크로를 소개합니다.|  
|[참조](../windows/wrl-reference.md)|[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]에 대한 참조 정보를 제공합니다.|  
|[빠른 참조 (Windows 런타임 및 Visual c + +)](http://go.microsoft.com/fwlink/?LinkId=229180)|[!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] 을 지원하는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]기능에 대해 간단히 설명합니다.|  
|[Visual c + +에서 Windows 런타임 구성 요소를 사용 하 여](http://go.microsoft.com/fwlink/?LinkId=229155)|[!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] 를 사용하여 기본적인 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 만드는 방법을 보여 줍니다.|