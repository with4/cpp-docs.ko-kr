---
title: "CHtmlView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlView
- AFXHTML/CHtmlView
- AFXHTML/CHtmlView::Create
- AFXHTML/CHtmlView::CreateControlSite
- AFXHTML/CHtmlView::ExecFormsCommand
- AFXHTML/CHtmlView::ExecWB
- AFXHTML/CHtmlView::GetAddressBar
- AFXHTML/CHtmlView::GetApplication
- AFXHTML/CHtmlView::GetBusy
- AFXHTML/CHtmlView::GetContainer
- AFXHTML/CHtmlView::GetFullName
- AFXHTML/CHtmlView::GetFullScreen
- AFXHTML/CHtmlView::GetHeight
- AFXHTML/CHtmlView::GetHtmlDocument
- AFXHTML/CHtmlView::GetLeft
- AFXHTML/CHtmlView::GetLocationName
- AFXHTML/CHtmlView::GetLocationURL
- AFXHTML/CHtmlView::GetMenuBar
- AFXHTML/CHtmlView::GetOffline
- AFXHTML/CHtmlView::GetParentBrowser
- AFXHTML/CHtmlView::GetProperty
- AFXHTML/CHtmlView::GetReadyState
- AFXHTML/CHtmlView::GetRegisterAsBrowser
- AFXHTML/CHtmlView::GetRegisterAsDropTarget
- AFXHTML/CHtmlView::GetSilent
- AFXHTML/CHtmlView::GetSource
- AFXHTML/CHtmlView::GetStatusBar
- AFXHTML/CHtmlView::GetTheaterMode
- AFXHTML/CHtmlView::GetToolBar
- AFXHTML/CHtmlView::GetTop
- AFXHTML/CHtmlView::GetTopLevelContainer
- AFXHTML/CHtmlView::GetType
- AFXHTML/CHtmlView::GetVisible
- AFXHTML/CHtmlView::GetWidth
- AFXHTML/CHtmlView::GoBack
- AFXHTML/CHtmlView::GoForward
- AFXHTML/CHtmlView::GoHome
- AFXHTML/CHtmlView::GoSearch
- AFXHTML/CHtmlView::LoadFromResource
- AFXHTML/CHtmlView::Navigate
- AFXHTML/CHtmlView::Navigate2
- AFXHTML/CHtmlView::OnBeforeNavigate2
- AFXHTML/CHtmlView::OnCommandStateChange
- AFXHTML/CHtmlView::OnDocumentComplete
- AFXHTML/CHtmlView::OnDocWindowActivate
- AFXHTML/CHtmlView::OnDownloadBegin
- AFXHTML/CHtmlView::OnDownloadComplete
- AFXHTML/CHtmlView::OnEnableModeless
- AFXHTML/CHtmlView::OnFilterDataObject
- AFXHTML/CHtmlView::OnFrameWindowActivate
- AFXHTML/CHtmlView::OnFullScreen
- AFXHTML/CHtmlView::OnGetDropTarget
- AFXHTML/CHtmlView::OnGetExternal
- AFXHTML/CHtmlView::OnGetHostInfo
- AFXHTML/CHtmlView::OnGetOptionKeyPath
- AFXHTML/CHtmlView::OnHideUI
- AFXHTML/CHtmlView::OnMenuBar
- AFXHTML/CHtmlView::OnNavigateComplete2
- AFXHTML/CHtmlView::OnNavigateError
- AFXHTML/CHtmlView::OnNewWindow2
- AFXHTML/CHtmlView::OnProgressChange
- AFXHTML/CHtmlView::OnPropertyChange
- AFXHTML/CHtmlView::OnQuit
- AFXHTML/CHtmlView::OnResizeBorder
- AFXHTML/CHtmlView::OnShowContextMenu
- AFXHTML/CHtmlView::OnShowUI
- AFXHTML/CHtmlView::OnStatusBar
- AFXHTML/CHtmlView::OnStatusTextChange
- AFXHTML/CHtmlView::OnTheaterMode
- AFXHTML/CHtmlView::OnTitleChange
- AFXHTML/CHtmlView::OnToolBar
- AFXHTML/CHtmlView::OnTranslateAccelerator
- AFXHTML/CHtmlView::OnTranslateUrl
- AFXHTML/CHtmlView::OnUpdateUI
- AFXHTML/CHtmlView::OnVisible
- AFXHTML/CHtmlView::PutProperty
- AFXHTML/CHtmlView::QueryFormsCommand
- AFXHTML/CHtmlView::QueryStatusWB
- AFXHTML/CHtmlView::Refresh
- AFXHTML/CHtmlView::Refresh2
- AFXHTML/CHtmlView::SetAddressBar
- AFXHTML/CHtmlView::SetFullScreen
- AFXHTML/CHtmlView::SetHeight
- AFXHTML/CHtmlView::SetLeft
- AFXHTML/CHtmlView::SetMenuBar
- AFXHTML/CHtmlView::SetOffline
- AFXHTML/CHtmlView::SetRegisterAsBrowser
- AFXHTML/CHtmlView::SetRegisterAsDropTarget
- AFXHTML/CHtmlView::SetSilent
- AFXHTML/CHtmlView::SetStatusBar
- AFXHTML/CHtmlView::SetTheaterMode
- AFXHTML/CHtmlView::SetToolBar
- AFXHTML/CHtmlView::SetTop
- AFXHTML/CHtmlView::SetVisible
- AFXHTML/CHtmlView::SetWidth
- AFXHTML/CHtmlView::Stop
dev_langs:
- C++
helpviewer_keywords:
- browsers, MFC support for
- CHtmlView class
- WebBrowser control
- WebBrowser control, MFC support
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d9d96ab02a0c49a2ece12c933f5d550a46204a39
ms.lasthandoff: 02/24/2017

---
# <a name="chtmlview-class"></a>CHtmlView 클래스
MFC의 문서/뷰 아키텍처 컨텍스트 내에서 WebBrowser 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHtmlView : public CFormView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHtmlView::Create](#create)|WebBrowser 컨트롤을 만듭니다.|  
|[CHtmlView::CreateControlSite](#createcontrolsite)|폼에서 컨트롤을 호스트할 컨트롤 사이트 인스턴스를 만드는 데 사용되는 Overridable입니다.|  
|[CHtmlView::ExecFormsCommand](#execformscommand)|`IOleCommandTarget::Exec` 메서드를 사용하여 지정된 명령을 실행합니다.|  
|[CHtmlView::ExecWB](#execwb)|명령을 실행합니다.|  
|[CHtmlView::GetAddressBar](#getaddressbar)|Internet Explorer 개체의 주소 표시줄을 표시할지 여부를 결정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::GetApplication](#getapplication)|Internet Explorer 응용 프로그램의 현재 인스턴스를 포함하는 응용 프로그램을 나타내는 응용 프로그램 개체를 검색합니다.|  
|[CHtmlView::GetBusy](#getbusy)|다운로드 또는 기타 작업이 계속 진행 중인지 여부를 나타내는 값을 검색합니다.|  
|[CHtmlView::GetContainer](#getcontainer)|WebBrowser 컨트롤의 컨테이너를 검색합니다.|  
|[CHtmlView::GetFullName](#getfullname)|웹 브라우저에 표시되는 리소스의 전체 이름(경로 포함)을 검색합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::GetFullScreen](#getfullscreen)|WebBrowser 컨트롤이 전체 화면 모드 또는 표준 창 모드로 작동 중인지를 나타냅니다.|  
|[CHtmlView::GetHeight](#getheight)|Internet Explorer 주 창의 높이를 검색합니다.|  
|[CHtmlView::GetHtmlDocument](#gethtmldocument)|활성 HTML 문서를 검색합니다.|  
|[CHtmlView::GetLeft](#getleft)|Internet Explorer 주 창에서 왼쪽 가장자리의 화면 좌표를 검색합니다.|  
|[CHtmlView::GetLocationName](#getlocationname)|현재 WebBrowser에 표시되는 리소스의 이름을 검색합니다.|  
|[CHtmlView::GetLocationURL](#getlocationurl)|현재 WebBrowser에 표시되는 리소스의 URL을 검색합니다.|  
|[CHtmlView::GetMenuBar](#getmenubar)|메뉴 모음을 표시할지 여부를 결정하는 값을 검색합니다.|  
|[CHtmlView::GetOffline](#getoffline)|컨트롤이 오프라인 상태인지 여부를 결정하는 값을 검색합니다.|  
|[CHtmlView::GetParentBrowser](#getparentbrowser)|`IDispatch` 인터페이스에 대한 포인터를 검색합니다. 자세한 내용은 참조 [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)합니다.|  
|[CHtmlView::GetProperty](#getproperty)|지정된 개체와 연결된 속성의 현재 값을 검색합니다.|  
|[CHtmlView::GetReadyState](#getreadystate)|웹 브라우저 개체의 준비 상태를 검색합니다.|  
|[CHtmlView::GetRegisterAsBrowser](#getregisterasbrowser)|WebBrowser 컨트롤이 대상 이름 확인을 위한 최상위 브라우저로 등록되었는지 여부를 나타냅니다.|  
|[CHtmlView::GetRegisterAsDropTarget](#getregisterasdroptarget)|WebBrowser 컨트롤이 탐색을 위한 놓기 대상으로 등록되었는지 여부를 나타냅니다.|  
|[CHtmlView::GetSilent](#getsilent)|대화 상자를 표시할 수 있는지 여부를 나타냅니다.|  
|[CHtmlView::GetSource](#getsource)|웹 페이지의 HTML 소스 코드입니다.|  
|[CHtmlView::GetStatusBar](#getstatusbar)|Internet Explorer의 상태 표시줄을 표시할지 여부를 나타냅니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::GetTheaterMode](#gettheatermode)|WebBrowser 컨트롤이 극장 모드인지 여부를 나타냅니다.|  
|[CHtmlView::GetToolBar](#gettoolbar)|도구 모음을 표시할지 여부를 결정하는 값을 검색합니다.|  
|[CHtmlView::GetTop](#gettop)|Internet Explorer 주 창에서 위쪽 가장자리의 화면 좌표를 검색합니다.|  
|[CHtmlView::GetTopLevelContainer](#gettoplevelcontainer)|현재 개체가 WebBrowser 컨트롤의 최상위 컨테이너인지 여부를 나타내는 값을 검색합니다.|  
|[CHtmlView::GetType](#gettype)|문서 개체의 형식 이름을 검색합니다.|  
|[CHtmlView::GetVisible](#getvisible)|개체를 표시할지 또는 숨길지를 나타내는 값을 검색합니다.|  
|[CHtmlView::GetWidth](#getwidth)|Internet Explorer 주 창의 너비를 검색합니다.|  
|[CHtmlView::GoBack](#goback)|기록 목록에서 이전 항목으로 이동합니다.|  
|[CHtmlView::GoForward](#goforward)|기록 목록에서 다음 항목으로 이동합니다.|  
|[CHtmlView::GoHome](#gohome)|현재 홈페이지 또는 시작 페이지로 이동합니다.|  
|[CHtmlView::GoSearch](#gosearch)|현재 검색 페이지로 이동합니다.|  
|[CHtmlView::LoadFromResource](#loadfromresource)|WebBrowser 컨트롤에 리소스를 로드합니다.|  
|[CHtmlView::Navigate](#navigate)|URL로 식별된 리소스로 이동합니다.|  
|[CHtmlView::Navigate2](#navigate2)|URL로 식별된 리소스 또는 전체 경로로 식별된 파일로 이동합니다.|  
|[CHtmlView::OnBeforeNavigate2](#onbeforenavigate2)|창 또는 프레임셋 요소에 지정된 WebBrowser에서 이동하기 전에 호출됩니다.|  
|[CHtmlView::OnCommandStateChange](#oncommandstatechange)|웹 브라우저 명령의 사용 상태가 변경되었음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnDocumentComplete](#ondocumentcomplete)|문서가 `READYSTATE_COMPLETE` 상태에 도달했음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnDocWindowActivate](#ondocwindowactivate)|Internet Explorer 또는 MSHTML 구현에서 호출 [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281), 컨테이너의 문서 창 활성화 되거나 비활성화 될 때 현재 위치에서 개체에 알립니다.|  
|[CHtmlView::OnDownloadBegin](#ondownloadbegin)|이동 작업이 시작되었음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnDownloadComplete](#ondownloadcomplete)|이동 작업이 중단 또는 실패한 상태로 마치면 호출됩니다.|  
|[CHtmlView::OnEnableModeless](#onenablemodeless)|컨테이너가 모달 대화 상자를 만들거나 삭제할 때 모덜리스 대화 상자를 사용하거나 사용하지 않도록 설정하기 위해 호출됩니다.|  
|[CHtmlView::OnFilterDataObject](#onfilterdataobject)|호스트가 Internet Explorer 또는 MSHTML의 데이터 개체를 바꿀 수 있도록 하기 위해 Internet Explorer 또는 MSHTML에 의해 호스트에서 호출됩니다.|  
|[CHtmlView::OnFrameWindowActivate](#onframewindowactivate)|호출 [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) 프레임 창의 경우 컨테이너의 최상위 개체에 알리기 위해 활성화 되거나 비활성화 합니다.|  
|[CHtmlView::OnFullScreen](#onfullscreen)|FullScreen 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnGetDropTarget](#ongetdroptarget)|에 대 한 대안을 제공 하는 놓기 대상으로 사용 하는 경우 Internet Explorer 또는 MSHTML 호출한 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)합니다.|  
|[CHtmlView::OnGetExternal](#ongetexternal)|호스트의 `IDispatch` 인터페이스를 가져오기 위해 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnGetHostInfo](#ongethostinfo)|Internet Explorer 또는 MSHTML 호스트의 UI 기능을 검색합니다.|  
|[CHtmlView::OnGetOptionKeyPath](#ongetoptionkeypath)|Internet Explorer 또는 MSHTML이 사용자 기본 설정을 저장하는 레지스트리 키를 반환합니다.|  
|[CHtmlView::OnHideUI](#onhideui)|Internet Explorer 또는 MSHTML이 해당 메뉴 및 도구 모음을 제거하면 호출됩니다.|  
|[CHtmlView::OnMenuBar](#onmenubar)|MenuBar 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnNavigateComplete2](#onnavigatecomplete2)|창 또는 프레임셋 요소의 하이퍼링크로 이동한 후에 호출됩니다.|  
|[CHtmlView::OnNavigateError](#onnavigateerror)|하이퍼링크로 이동이 실패할 경우 프레임워크에 의해 호출됩니다.|  
|[CHtmlView::OnNewWindow2](#onnewwindow2)|리소스를 표시하기 위해 새 창이 만들어지면 호출됩니다.|  
|[CHtmlView::OnProgressChange](#onprogresschange)|다운로드 작업 진행률이 업데이트되었음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnPropertyChange](#onpropertychange)|응용 프로그램에 알리기 위해 호출 하는 [의](#putproperty) 메서드가 속성의 값을 변경 되었습니다.|  
|[CHtmlView::OnQuit](#onquit)|Internet Explorer 응용 프로그램을 끝낼 준비가 되었음을 응용 프로그램에 알리기 위해 호출됩니다. (Internet Explorer에만 적용됨)|  
|[CHtmlView::OnResizeBorder](#onresizeborder)|Internet Explorer 또는 MSHTML 구현에서 호출 [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), 해당 테두리 공간 크기를 조정 하는 데 필요한 개체를 경고 하 합니다.|  
|[CHtmlView::OnShowContextMenu](#onshowcontextmenu)|상황에 맞는 메뉴를 표시하려는 경우 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnShowUI](#onshowui)|Internet Explorer 또는 MSHTML이 해당 메뉴 및 도구 모음을 표시하기 전에 호출됩니다.|  
|[CHtmlView::OnStatusBar](#onstatusbar)|StatusBar 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnStatusTextChange](#onstatustextchange)|응용 프로그램에 WebBrowser 컨트롤과 연결된 상태 표시줄의 텍스트가 변경되었음을 알리기 위해 호출됩니다.|  
|[CHtmlView::OnTheaterMode](#ontheatermode)|TheaterMode 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnTitleChange](#ontitlechange)|WebBrowser 컨트롤의 문서 제목을 사용할 수 있게 되거나 변경할 경우 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnToolBar](#ontoolbar)|ToolBar 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnTranslateAccelerator](#ontranslateaccelerator)|Internet Explorer 또는 MSHTML 호출 때 [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) 또는 [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) 컨테이너의 메시지 큐에서 메뉴 바로 가기 키 메시지를 처리 하기 위해 호출 됩니다.|  
|[CHtmlView::OnTranslateUrl](#ontranslateurl)|호스트가 로드할 URL을 수정할 수 있도록 하기 위해 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnUpdateUI](#onupdateui)|명령 상태가 변경되었음을 호스트에 알립니다.|  
|[CHtmlView::OnVisible](#onvisible)|WebBrowser 컨트롤의 창을 표시하거나 숨기면 호출됩니다.|  
|[CHtmlView::PutProperty](#putproperty)|지정된 개체와 연결된 속성의 값을 설정합니다.|  
|[CHtmlView::QueryFormsCommand](#queryformscommand)|사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.|  
|[CHtmlView::QueryStatusWB](#querystatuswb)|WebBrowser 컨트롤에 의해 처리되는 명령의 상태를 쿼리합니다.|  
|[CHtmlView::Refresh](#refresh)|현재 파일을 다시 로드합니다.|  
|[CHtmlView::Refresh2](#refresh2)|현재 파일을 다시 로드하고 필요에 따라 `pragma:nocache` 헤더가 전송되지 않도록 합니다.|  
|[CHtmlView::SetAddressBar](#setaddressbar)|Internet Explorer 개체의 주소 표시줄을 표시하거나 숨깁니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetFullScreen](#setfullscreen)|컨트롤이 전체 화면 모드 또는 표준 창 모드로 작동 중인지를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetHeight](#setheight)|Internet Explorer 주 창의 높이를 설정합니다.|  
|[CHtmlView::SetLeft](#setleft)|Internet Explorer 주 창의 가로 위치를 설정합니다.|  
|[CHtmlView::SetMenuBar](#setmenubar)|컨트롤의 메뉴 모음을 표시할지 여부를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetOffline](#setoffline)|컨트롤이 오프라인 상태인지 여부를 결정할 값을 설정합니다.|  
|[CHtmlView::SetRegisterAsBrowser](#setregisterasbrowser)|WebBrowser 컨트롤이 대상 이름 확인을 위한 최상위 브라우저로 등록되었는지 여부를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetRegisterAsDropTarget](#setregisterasdroptarget)|WebBrowser 컨트롤이 탐색을 위한 놓기 대상으로 등록되었는지 여부를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetSilent](#setsilent)|컨트롤이 대화 상자를 표시할지 여부를 결정할 값을 설정합니다.|  
|[CHtmlView::SetStatusBar](#setstatusbar)|Internet Explorer의 상태 표시줄을 표시할지 여부를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetTheaterMode](#settheatermode)|WebBrowser 컨트롤이 극장 모드인지 여부를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetToolBar](#settoolbar)|컨트롤의 도구 모음을 표시할지 여부를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetTop](#settop)|Internet Explorer 주 창의 세로 위치를 설정합니다.|  
|[CHtmlView::SetVisible](#setvisible)|개체를 표시할지 또는 숨길지를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetWidth](#setwidth)|Internet Explorer 주 창의 너비를 설정합니다.|  
|[CHtmlView::Stop](#stop)|파일 열기를 중지합니다.|  
  
## <a name="remarks"></a>주의  
 WebBrowser 컨트롤은 사용자가 로컬 파일 시스템과 네트워크의 폴더뿐 아니라 World Wide Web에서 사이트를 찾을 수 있는 창입니다. WebBrowser 컨트롤은 하이퍼링크와 URL(Uniform Resource Locator) 탐색을 지원하고 기록 목록을 유지 관리합니다.  
  
## <a name="using-the-chtmlview-class-in-an-mfc-application"></a>MFC 응용 프로그램에서 CHtmlView 클래스 사용  
 표준 MFC 프레임워크 응용 프로그램(SDI 또는 MDI 기반)에서 뷰 개체는 일반적으로 특수한 클래스 집합에서 파생됩니다. 이러한 클래스는 모두 `CView`에서 파생되며, `CView`에서 제공하는 것 이상의 특수 기능을 제공합니다.  
  
 응용 프로그램의 뷰 클래스가 `CHtmlView` 를 기반으로 하는 경우 뷰에 WebBrowser 컨트롤이 제공됩니다. 이렇게 하면 실제로 응용 프로그램이 웹 브라우저가 됩니다. 웹 브라우저 스타일 응용 프로그램을 만드는 기본 방법은 MFC 응용 프로그램 마법사를 사용하고 `CHtmlView` 를 뷰 클래스로 지정하는 것입니다. 구현 및 MFC 응용 프로그램 내에서 WebBrowser 컨트롤 사용에 대 한 자세한 내용은 참조 하십시오. [웹 브라우저 스타일 응용 프로그램을 만드는](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)합니다.  
  
> [!NOTE]
>  WebBrowser ActiveX 컨트롤(및 따라서 `CHtmlView`)은 Internet Explorer 4.0 이상이 설치된 Windows NT 버전 4.0 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.  
  
 `CHtmlView`는 웹(및/또는 HTML 문서)에 액세스하는 응용 프로그램용으로 작성되었습니다. 다음 `CHtmlView` 멤버 함수는 Internet Explorer 응용 프로그램에만 적용됩니다. 해당 함수는 WebBrowser 컨트롤에서 성공하지만 아무런 가시적 효과가 없습니다.  
  
- [GetAddressBar](#getaddressbar)  
  
- [GetFullName](#getfullname)  
  
- [GetStatusBar](#getstatusbar)  
  
- [SetAddressBar](#setaddressbar)  
  
- [SetFullScreen](#setfullscreen)  
  
- [SetMenuBar](#setmenubar)  
  
- [SetStatusBar](#setstatusbar)  
  
- [SetToolBar](#settoolbar)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxhtml.h  
  
##  <a name="create"></a>CHtmlView::Create  
 WebBrowser 컨트롤 또는 만들 컨테이너 Internet Explorer에 대 한 실행 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다. 클래스 이름에 등록 되는 이름 수는 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) 전역 함수 또는 **RegisterClass** Windows 함수입니다. 경우 **NULL**, 미리 정의 된 기본값을 사용 하 여 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 특성입니다.  
  
 `lpszWindowName`  
 창 이름을 나타내는 null로 끝나는 문자열을 가리킵니다.  
  
 `dwStyle`  
 창 스타일 특성을 지정합니다. 기본적으로는 **WS_VISIBLE** 및 **WS_CHILD** 창 스타일 설정 됩니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와 창의 위치를 지정 하는 구조입니다. `rectDefault` 값을 사용 하면 Windows 크기와 새 창의 위치를 지정할 수 있습니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 보기의 ID. 기본적으로 설정 **AFX_IDW_PANE_FIRST**합니다.  
  
 `pContext`  
 에 대 한 포인터는 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)합니다. **NULL** 기본적으로 합니다.  
  
##  <a name="createcontrolsite"></a>CHtmlView::CreateControlSite  
 폼에서 컨트롤을 호스트할 컨트롤 사이트 인스턴스를 만드는 데 사용되는 Overridable입니다.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT nID,  
    REFCLSID clsid);
```  
  
### <a name="parameters"></a>매개 변수  
 `pContainer`  
 에 대 한 포인터는 [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) 컨트롤을 포함 하는 개체입니다.  
  
 `ppSite`  
 에 대 한 포인터에 대 한 포인터는 [COleControlSite](../../mfc/reference/colecontrolsite-class.md) 개체를 컨트롤에 대 한 사이트를 제공 합니다.  
  
 `nID`  
 호스트 컨트롤의 식별자입니다.  
  
 `clsid`  
 컨트롤의 CLSID를 호스팅할 수  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 컨트롤 사이트 클래스의 인스턴스를 반환 하려면이 멤버 함수를 재정의할 수 있습니다.  
  
##  <a name="execformscommand"></a>CHtmlView::ExecFormsCommand  
 `IOleCommandTarget::Exec` 메서드를 사용하여 지정된 명령을 실행합니다.  
  
```  
HRESULT ExecFormsCommand(
    DWORD dwCommandID,  
    VARIANT* pVarIn,  
    VARIANT* pVarOut);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCommandID`  
 실행할 명령입니다. 이 명령은에 속해야 합니다는 **CMDSETID3_Forms3** 그룹입니다.  
  
 *pVarIn*  
 에 대 한 포인터는 **VARIANT** 입력된 인수를 포함 하는 구조입니다. 수 **NULL**합니다.  
  
 *pVarOut*  
 에 대 한 포인터는 **VARIANT** 구조 명령 출력을 받을 수 있습니다. 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다. 가능한 값의 전체 목록을 보려면 [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 **ExecFormsCommand** 의 동작을 구현 하는 [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) 메서드.  
  
##  <a name="execwb"></a>CHtmlView::ExecWB  
 WebBrowser 또는 Internet Explorer에서 명령을 실행 하려면이 멤버 함수를 호출 합니다.  
  
```  
void ExecWB(
    OLECMDID cmdID,  
    OLECMDEXECOPT cmdexecopt,  
    VARIANT* pvaIn,  
    VARIANT* pvaOut);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 실행할 명령입니다.  
  
 *cmdexecopt*  
 명령을 실행 하는 것에 대 한 설정 옵션입니다.  
  
 `pvaIn`  
 명령 입력된 인수를 지정 하는 데 사용 되는 variant입니다.  
  
 *pvaOut*  
 명령 출력 인수를 지정 하는 데 사용 되는 variant입니다.  
  
### <a name="remarks"></a>주의  
 참조 [IWebBrowser2::ExecWB](https://msdn.microsoft.com/library/aa752117.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getaddressbar"></a>CHtmlView::GetAddressBar  
 Internet Explorer의 주소 표시줄을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetAddressBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 주소 표시줄에 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="getapplication"></a>CHtmlView::GetApplication  
 WebBrowser 컨트롤을 포함 하는 응용 프로그램에서 지원 되는 자동화 개체를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
LPDISPATCH GetApplication() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `IDispatch` 현재 문서 개체의 인터페이스입니다. 자세한 내용은 참조 [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)합니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getbusy"></a>CHtmlView::GetBusy  
 WebBrowser 컨트롤 작업에 탐색 또는 다운로드 작업이 포함 되어 있는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetBusy() const;  
```  
  
### <a name="return-value"></a>반환 값  
 웹 브라우저에서 사용 중입니다.&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getcontainer"></a>CHtmlView::GetContainer  
 웹 브라우저의 컨테이너에 계산 되는 개체를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
LPDISPATCH GetContainer() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `IDispatch` 현재 문서 개체의 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getfullname"></a>CHtmlView::GetFullName  
 현재 Internet Explorer를 표시 하는 파일의 전체 경로 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 현재 표시 된 파일의 이름과 경로 포함 하는 개체입니다. 없는 경로 파일 이름이 없으면 `GetFullName` 빈 반환 `CString`합니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="getfullscreen"></a>CHtmlView::GetFullScreen  
 WebBrowser 컨트롤 표준 창 모드 또는 전체 화면 모드에서 작동 하는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetFullScreen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 WebBrowser 전체 화면 모드에서 작동 하 고 있으면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 전체 화면 모드에서 Internet Explorer 주 창을 최대화 하 고 상태 표시줄, 도구 모음, 메뉴 모음 및 제목 표시줄 숨겨집니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getheight"></a>CHtmlView::GetHeight  
 WebBrowser 컨트롤의 프레임 창의 픽셀 높이 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
long GetHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤의 프레임 창 높이 (픽셀)에서입니다.  
  
##  <a name="gethtmldocument"></a>CHtmlView::GetHtmlDocument  
 현재 문서에 대 한 HTML 문서를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
LPDISPATCH GetHtmlDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `IDispatch` 현재 문서 개체의 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getleft"></a>CHtmlView::GetLeft  
 WebBrowser 컨트롤의 내부 왼쪽된 가장자리와 해당 컨테이너의 왼쪽된 가장자리 사이의 거리를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
long GetLeft() const;  
```  
  
### <a name="return-value"></a>반환 값  
 왼쪽 가장자리의 거리 (픽셀)에서입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getlocationname"></a>CHtmlView::GetLocationName  
 WebBrowser에 표시 되는 리소스의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetLocationName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) WebBrowser에 현재 표시 된 리소스의 이름을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 리소스가 World Wide Web에 HTML 페이지 있으면 이름이 해당 페이지의 제목입니다. 폴더 또는 파일에서 네트워크 또는 로컬 컴퓨터에 리소스가 있으면 UNC 또는 폴더 또는 파일의 전체 경로 이름이입니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getlocationurl"></a>CHtmlView::GetLocationURL  
 WebBrowser 컨트롤을 표시 하는 현재 리소스의 URL을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetLocationURL() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) WebBrowser에 현재 표시 된 리소스의 URL을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 폴더 또는 파일에서 네트워크 또는 로컬 컴퓨터에 리소스가 있으면 UNC 또는 폴더 또는 파일의 전체 경로 이름이입니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getmenubar"></a>CHtmlView::GetMenuBar  
 메뉴 모음에 표시 되는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 모음에 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getoffline"></a>CHtmlView::GetOffline  
 웹 브라우저 오프 라인에서 작동 하는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetOffline() const;  
```  
  
### <a name="return-value"></a>반환 값  
 웹 브라우저에서 현재 오프 라인;&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getparentbrowser"></a>CHtmlView::GetParentBrowser  
 WebBrowser 컨트롤의 부모 개체에 대 한 포인터를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
LPDISPATCH GetParentBrowser() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `IDispatch` WebBrowser 컨트롤의 부모 개체의 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getproperty"></a>CHtmlView::GetProperty  
 이 컨트롤에서 현재 연결 된 속성의 값을 가져오는 함수를 호출 합니다.  
  
```  
BOOL GetProperty(
    LPCTSTR lpszProperty,  
    CString& strValue);  
  
COleVariant GetProperty(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProperty`  
 검색할 속성을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `strValue`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 속성의 현재 값을 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공적으로 완료 한 경우&0;이 아니고 첫 번째 버전 그렇지 않으면&0;입니다. 두 번째 버전에는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getreadystate"></a>CHtmlView::GetReadyState  
 WebBrowser 개체의 준비 상태를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
READYSTATE GetReadyState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) 값에 설명 된 대로 값은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getregisterasbrowser"></a>CHtmlView::GetRegisterAsBrowser  
 WebBrowser 개체가 대상 이름 확인에 대 한 최상위 브라우저로 등록 되어 있는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetRegisterAsBrowser() const;  
```  
  
### <a name="return-value"></a>반환 값  
 브라우저는 최상위 브라우저;로 등록 되어 있으면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getregisterasdroptarget"></a>CHtmlView::GetRegisterAsDropTarget  
 WebBrowser 컨트롤 탐색에 대 한 놓기 대상으로 등록 되어 있는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetRegisterAsDropTarget() const;  
```  
  
### <a name="return-value"></a>반환 값  
 브라우저는 놓기 대상;로 등록 되어 있으면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getsilent"></a>CHtmlView::GetSilent  
 WebBrowser 컨트롤에는 모든 대화 상자를 표시할 수 있는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetSilent() const;  
```  
  
### <a name="return-value"></a>반환 값  
 WebBrowser 컨트롤;에서 대화 상자를 표시할 수 없는 경우&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getsource"></a>CHtmlView::GetSource  
 웹 페이지에 대 한 HTML 소스 코드를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetSource(CString& strRef);
```  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="parameters"></a>매개 변수  
 `refString`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 하는 소스 코드를 저장 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 Internet Explorer의 "소스 보기" 명령과 동일 제외 하 고 소스 코드에 반환 되는 `CString`합니다.  
  
##  <a name="getstatusbar"></a>CHtmlView::GetStatusBar  
 WebBrowser 컨트롤 상태 표시줄 표시 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetStatusBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태 표시줄을 표시할 수 있으면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="gettheatermode"></a>CHtmlView::GetTheaterMode  
 웹 브라우저 극장 모드에 있는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetTheaterMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 웹 브라우저 극장 모드에 있으면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 웹 브라우저 극장 모드에 있을 때 브라우저 창의 전체 화면을 채웁니다, 그리고 최소 탐색 도구 집합이 있는 도구 모음을 나타나고 상태 표시줄을 화면의 오른쪽 아래 모서리에 표시 합니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="gettoolbar"></a>CHtmlView::GetToolBar  
 도구 모음 표시 되는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
int GetToolBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음 표시 되는지를 나타내는 값입니다. 도구 모음 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
##  <a name="gettop"></a>CHtmlView::GetTop  
 WebBrowser 컨트롤의 주 창의 위쪽 가장자리의 화면 좌표를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
long GetTop() const;  
```  
  
### <a name="return-value"></a>반환 값  
 주소는 주 창의 위쪽 가장자리의 화면 좌표를 수신 하는 변수입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="gettoplevelcontainer"></a>CHtmlView::GetTopLevelContainer  
 Internet Explorer WebBrowser 컨트롤의 최상위 컨테이너 인지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetTopLevelContainer() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 컨테이너는 최상위 컨테이너입니다. 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="gettype"></a>CHtmlView::GetType  
 포함 된 액티브 문서의 형식 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 포함 된 현재 문서의 형식 이름을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getvisible"></a>CHtmlView::GetVisible  
 포함 된 개체 표시 되는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 개체가 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="getwidth"></a>CHtmlView::GetWidth  
 Internet Explorer 주 창의 너비를 검색합니다.  
  
```  
long GetWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 창의 현재 너비입니다.  
  
##  <a name="goback"></a>CHtmlView::GoBack  
 기록 목록에서 이전 버전과 한 항목을 이동합니다.  
  
```  
void GoBack();
```  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="goforward"></a>CHtmlView::GoForward  
 기록 목록에서 한 항목을 앞으로 이동합니다.  
  
```  
void GoForward();
```  
  
##  <a name="gohome"></a>CHtmlView::GoHome  
 Internet Explorer 인터넷 옵션 대화 상자 또는 제어판을 통해 액세스하는 인터넷 속성 대화 상자에서 지정된 현재 홈페이지 또는 시작 페이지로 이동합니다.  
  
```  
void GoHome();
```  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="gosearch"></a>CHtmlView::GoSearch  
 현재 검색 페이지를 Internet Explorer 인터넷 옵션 대화 상자 또는 인터넷 속성 대화 상자에 지정 된 제어판에서 액세스를 탐색 합니다.  
  
```  
void GoSearch();
```  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="loadfromresource"></a>CHtmlView::LoadFromResource  
 WebBrowser 컨트롤에 지정된 된 리소스를 로드 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszResource`  
 로드할 리소스의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nRes`  
 로드할 리소스의 이름을 포함 하는 버퍼의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="navigate"></a>CHtmlView::Navigate  
 URL로 식별 되는 리소스를 이동 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Navigate(
    LPCTSTR URL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *URL*  
 탐색 하는 URL을 포함 하는 호출자가 할당 문자열 또는 표시할 파일의 전체 경로입니다.  
  
 `dwFlags`  
 기록 목록에 리소스를 추가할 것인지를에 대 한 읽기 또는 쓰기 캐시를 사용할지 여부 및 리소스를 새 창에 표시할지 여부를 지정 하는 변수의 플래그입니다. 변수에서 정의 된 값의 조합 수는 [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) 열거형입니다.  
  
 `lpszTargetFrameName`  
 리소스를 표시 하는 프레임의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `lpszHeaders`  
 서버에 보낼 HTTP 헤더를 지정 하는 값에 대 한 포인터입니다. 이러한 헤더는 Internet Explorer 기본 머리글에 추가 됩니다. 헤더는 서버는 서버 또는 상태 코드에 전달 되는 데이터의 형식에 필요한 작업으로 등의 작업을 지정할 수 있습니다. 이 매개 변수는 *URL* HTTP URL이 아닙니다.  
  
 `lpvPostData`  
 HTTP POST 트랜잭션과 함께 보낼 데이터를 한 포인터입니다. 예를 들어 HTML 형식에서 수집 된 데이터를 보낼 POST 트랜잭션이 사용 됩니다. 이 매개 변수는 모든 게시 데이터를 지정 하지 않는 경우 **Navigate** 는 HTTP GET 거래를 발급 합니다. 이 매개 변수는 *URL* HTTP URL이 아닙니다.  
  
 `dwPostDataLen`  
 HTTP POST 트랜잭션과 함께 보낼 데이터입니다. 예를 들어 HTML 형식에서 수집 된 데이터를 보낼 POST 트랜잭션이 사용 됩니다. 이 매개 변수는 모든 게시 데이터를 지정 하지 않는 경우 **Navigate** 는 HTTP GET 거래를 발급 합니다. 이 매개 변수는 *URL* HTTP URL이 아닙니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="navigate2"></a>CHtmlView::Navigate2  
 전체 경로 의해 식별 된 파일 또는 URL을 통해 식별 되는 리소스를 이동 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Navigate2(
    LPITEMIDLIST pIDL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags,  
    CByteArray& baPostedData,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeader = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pIDL*  
 에 대 한 포인터는 [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) 구조입니다.  
  
 `dwFlags`  
 기록 목록에 리소스를 추가할 것인지를에 대 한 읽기 또는 쓰기 캐시를 사용할지 여부 및 리소스를 새 창에 표시할지 여부를 지정 하는 변수의 플래그입니다. 변수에서 정의 된 값의 조합 수는 [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) 열거형입니다.  
  
 `lpszTargetFrameName`  
 리소스를 표시 하는 프레임의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `lpszURL`  
 URL을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `lpvPostData`  
 HTTP POST 트랜잭션과 함께 보낼 데이터입니다. 예를 들어 HTML 형식에서 수집 된 데이터를 보낼 POST 트랜잭션이 사용 됩니다. 이 매개 변수는 모든 게시 데이터를 지정 하지 않는 경우 `Navigate2` 는 HTTP GET 거래를 발급 합니다. 이 매개 변수는 *URL* 는 HTTP 또는 HTTPS URL이 아닙니다.  
  
 `dwPostDataLen`  
 가리키는 데이터의 길이 (바이트)는 `lpvPostData` 매개 변수입니다.  
  
 `lpszHeaders`  
 서버에 보낼 HTTP 또는 HTTPS 헤더를 지정 하는 값에 대 한 포인터입니다. 이러한 헤더는 Internet Explorer 기본 머리글에 추가 됩니다. 헤더는 서버는 서버 또는 상태 코드에 전달 되는 데이터의 형식에 필요한 작업으로 등의 작업을 지정할 수 있습니다. 이 매개 변수는 *URL* 는 HTTP 또는 HTTPS URL이 아닙니다.  
  
 `baPostedData`  
 에 대 한 참조는 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 확장 된 **Navigate** 매개 변수에 의해 표현 되는 데스크톱 및 내 컴퓨터와 같은 특수 폴더, 검색을 지원 하 여 멤버 함수 *pIDL*합니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCHtmlHttp #&7;](../../mfc/reference/codesnippet/cpp/chtmlview-class_1.cpp)]  
  
##  <a name="onbeforenavigate2"></a>CHtmlView::OnBeforeNavigate2  
 이 멤버 함수를 웹 브라우저에서 발생 하는 탐색 하기 전에 발생 한 이벤트 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnBeforeNavigate2(
    LPCTSTR lpszURL,  
    DWORD nFlags,  
    LPCTSTR lpszTargetFrameName,  
    CByteArray& baPostedData,  
    LPCTSTR lpszHeaders,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszURL`  
 탐색할 URL을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nFlags`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `lpszTargetFrameName`  
 리소스를 표시 하는 프레임의 이름을 포함 하는 문자열 또는 **NULL** 프레임이 없는 명명 된 리소스에 대 한 대상 하는 경우.  
  
 `baPostedData`  
 에 대 한 참조는 `CByteArray` HTTP POST 트랜잭션이 사용 되는 경우 서버에 보낼 데이터를 포함 하는 개체입니다.  
  
 `lpszHeaders`  
 (HTTP Url에만 해당) 서버로 보낼 추가 HTTP 헤더를 포함 하는 문자열에 대 한 포인터입니다. 헤더는 서버는 서버 또는 상태 코드에 전달 되는 데이터의 형식에 필요한 작업으로 등의 작업을 지정할 수 있습니다.  
  
 `pbCancel`  
 취소 플래그에 대 한 포인터입니다. 응용 프로그램 탐색 작업을 취소 하거나 계속 진행 하도록 허용할 수&0;&0;이 아닌 값을이 매개 변수를 설정할 수 있습니다.  
  
##  <a name="oncommandstatechange"></a>CHtmlView::OnCommandStateChange  
 이 멤버 함수는 웹 브라우저 명령의 활성화 상태가 변경 되는 응용 프로그램에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnCommandStateChange(
    long nCommand,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 *된 명령*  
 활성화 된 상태가 변경 된 명령 식별자입니다.  
  
 `bEnable`  
 활성화 된 상태입니다. 이 매개 변수는 명령이 활성화 또는 비활성화 된 경우에&0; 경우&0;이 아닌 값입니다.  
  
##  <a name="ondocumentcomplete"></a>CHtmlView::OnDocumentComplete  
 이 멤버 함수는 문서에 도달 하는 응용 프로그램에 알리기 위해 프레임 워크에서 호출 되는 `READYSTATE_COMPLETE` 상태입니다.  
  
```  
virtual void OnDocumentComplete(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszURL`  
 UNC URL로 계산 되는 문자열에 대 한 포인터에는 이름 또는 탐색 PIDL (식별자 목록 항목에 포인터) 파일입니다.  
  
### <a name="remarks"></a>주의  
 모든 프레임 발생 하는 각 프레임 하지만이 이벤트는 발생 한 [OnDownloadBegin](#ondownloadbegin) 해당 이벤트는 발생 `OnDocumentComplete` 이벤트입니다.  
  
 로 표시 된 URL `lpszURL` 이 URL은 정규화 및 정규화 된 URL 때문에 브라우저를 이동 하 여을 들었습니다 된 URL에서 다를 수 있습니다. 예를 들어, 응용 프로그램에 대 한 호출에서 "www.microsoft.com"의 URL을 지정 하는 경우 [Navigate](#navigate) 또는 [Navigate2](#navigate2), 전달한 URL `OnNavigateComplete2` "http://www.microsoft.com/" 됩니다. 또한 서버가 다른 URL로 브라우저 리디렉션, 리디렉션된 URL 여기에 반영 됩니다.  
  
##  <a name="ondocwindowactivate"></a>CHtmlView::OnDocWindowActivate  
 **IOleInPlaceActiveObject::OnDocWindowActivate**의 Internet Explorer 또는 MSHTML 구현에서 호출되며, 컨테이너의 문서 창이 활성화 또는 비활성화될 경우 활성 현재 위치 개체에 알립니다.  
  
```  
virtual HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 `fActivate`  
 문서 창의 상태를 나타냅니다. 이 값이&0;이 아닌 경우 창이 활성화 되 고 있습니다. 이 값이&0; 인 경우 창 비활성화 하는 중입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnDocWindowActivate` 에 반응 하는 `OnDocWindowActivate` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="ondownloadbegin"></a>CHtmlView::OnDownloadBegin  
 이 멤버 함수는 문서 다운로드를 시작 하려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDownloadBegin();
```  
  
### <a name="remarks"></a>주의  
 이 이벤트가 발생 하 고 잠시 후는 [OnBeforeNavigate2](#onbeforenavigate2) 이벤트, 탐색을 취소 하지 않는 한 합니다. 모든 애니메이션 또는 "사용 중" 표시를 표시 해야 하는 컨테이너는이 이벤트에 연결 되어야 합니다.  
  
##  <a name="ondownloadcomplete"></a>CHtmlView::OnDownloadComplete  
 이 멤버 함수는 탐색 작업 완료, 중단 되었거나 실패를 나타내기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDownloadComplete();
```  
  
##  <a name="onenablemodeless"></a>CHtmlView::OnEnableModeless  
 Internet Explorer 또는 MSHTML 모달 UI를 표시 하는 경우 호출 됩니다.  
  
```  
virtual HRESULT OnEnableModeless(BOOL fEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 `fEnable`  
 호스트의 모덜리스 대화 상자를 설정 하거나 해제 하는 경우를 나타냅니다. 이 값은&0;이 아니고, 모덜리스 대화 상자를 사용할 수 있습니다. 이 값이&0; 인 경우에 모덜리스 대화 상자는 사용할 수 없습니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 컨테이너를 만들거나 모달 대화 상자가 소멸 모덜리스 대화 상자를 사용 하지 않도록 설정 하거나 사용 합니다. 재정의 `OnEnableModeless` 에 반응 하는 `EnableModeless` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onfilterdataobject"></a>CHtmlView::OnFilterDataObject  
 호스트가 Internet Explorer 또는 MSHTML의 데이터 개체를 바꿀 수 있도록 하기 위해 Internet Explorer 또는 MSHTML에 의해 호스트에서 호출됩니다.  
  
```  
virtual HRESULT OnFilterDataObject(
    LPDATAOBJECT pDataObject,  
    LPDATAOBJECT* ppDataObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 주소에 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Internet Explorer 또는 MSHTML에서 제공 하는 인터페이스입니다.  
  
 *ppDataObject*  
 주소를 수신 하는 `IDataObject` 호스트에서 제공 하는 인터페이스 포인터입니다. 이 매개 변수 콘텐츠를 항상 초기화 **NULL**메서드가 실패 하는 경우에 합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`데이터 개체는 교체 하는 경우 **S_FALSE** 데이터 개체를 대체 하지 않는 경우 또는 오류가 발생 하는 경우 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnFilterDataObject` 에 반응 하는 `FilterDataObject` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onframewindowactivate"></a>CHtmlView::OnFrameWindowActivate  
 호출 [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) 프레임 창의 경우 컨테이너의 최상위 개체에 알리기 위해 활성화 되거나 비활성화 합니다.  
  
```  
virtual HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 `fActivate`  
 컨테이너의 최상위 프레임 창의 상태를 나타냅니다. 이 값이&0;이 아닌 경우 창이 활성화 되 고 있습니다. 이 값이&0; 인 경우 창 비활성화 하는 중입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnFrameWindowActivate` 에 반응 하는 `OnFrameWindowActivate` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onfullscreen"></a>CHtmlView::OnFullScreen  
 프레임 워크에서이 멤버 함수를 호출 하는 경우는 [전체 화면](https://msdn.microsoft.com/library/aa752119.aspx) 속성이 변경 합니다.  
  
```  
virtual void OnFullScreen(BOOL bFullScreen);
```  
  
### <a name="parameters"></a>매개 변수  
 *bFullScreen*  
 전체 화면 모드에서 Internet Explorer가&0;이 아닌 그렇지 않으면&0;입니다.  
  
##  <a name="ongetdroptarget"></a>CHtmlView::OnGetDropTarget  
 에 대 한 대안을 제공 하는 놓기 대상으로 사용 하는 경우 Internet Explorer 또는 MSHTML 호출한 `IDropTarget`합니다.  
  
```  
virtual HRESULT OnGetDropTarget(
    LPDROPTARGET pDropTarget,  
    LPDROPTARGET* ppDropTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDropTarget`  
 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) 사용 하 여 Internet Explorer 또는 MSHTML 제안 합니다.  
  
 `ppDropTarget`  
 주소에 `IDropTarget` 를 받는 `IDropTarget` 호스트 제공 하고자 하는 경우 인터페이스 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 참조 [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 반환 코드 목록은 합니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnGetDropTarget` 에 반응 하는 `GetDropTarget` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="ongetexternal"></a>CHtmlView::OnGetExternal  
 호스트의 `IDispatch` 인터페이스를 가져오기 위해 Internet Explorer 또는 MSHTML에 의해 호출됩니다.  
  
```  
virtual HRESULT OnGetExternal(LPDISPATCH* lppDispatch);
```  
  
### <a name="parameters"></a>매개 변수  
 *lppDispatch*  
 수신 하는 주소에 대 한 포인터는 `IDispatch` 호스트 응용 프로그램의 인터페이스 포인터입니다. 호스트 자동화 인터페이스를 노출 하는 경우이 매개 변수를 통해 Internet Explorer 또는 MSHTML에 대 한 참조를 제공할 수 있습니다. 이 매개 변수 콘텐츠를 항상 초기화 **NULL**메서드가 실패 하는 경우에 합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnGetExternal` 에 반응 하는 `GetExternal` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="ongethostinfo"></a>CHtmlView::OnGetHostInfo  
 Internet Explorer 또는 MSHTML 호스트의 UI 기능을 검색합니다.  
  
```  
virtual HRESULT OnGetHostInfo(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pInfo`  
 주소에 [DOCHOSTUIINFO](https://msdn.microsoft.com/library/aa770044.aspx) 구조체는 호스트의 UI 기능입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnGetHostInfo` 에 반응 하는 `GetHostInfo` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="ongetoptionkeypath"></a>CHtmlView::OnGetOptionKeyPath  
 Internet Explorer 또는 MSHTML 사용자 기본 설정을 저장 됩니다. 레지스트리 키를 가져오려면이 함수를 호출 합니다.  
  
```  
virtual HRESULT OnGetOptionKeyPath(
    LPOLESTR* pchKey,  
    DWORD dwReserved);
```  
  
### <a name="parameters"></a>매개 변수  
 `pchKey`  
 주소에 `LPOLESTR` 을 받는 호스트의 기본 옵션을 저장 하는 레지스트리 하위 키 문자열입니다. 이 하위 키 HKEY_CURRENT_USER 키 아래에 있게 됩니다. 사용 하 여이 메모리를 할당할 [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)합니다. 호출 응용 프로그램을 사용 하 여이 메모리를 확보 담당 [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)합니다. 항상이 매개 변수를 초기화 해야 **NULL**메서드가 실패 하는 경우에 합니다.  
  
 `dwReserved`  
 나중에 사용하기 위해 예약되어 있습니다. 현재 사용 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 **S_FALSE** 그렇지 않은 경우. 경우 **S_FALSE**, Internet Explorer 또는 MSHTML 기본적으로 자체 사용자 옵션입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnGetOptionKeyPath` 에 반응 하는 `GetOptionKeyPath` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onhideui"></a>CHtmlView::OnHideUI  
 이 멤버 함수는 Internet Explorer 또는 MSHTML 해당 메뉴 및 도구 모음을 제거 하는 경우 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual HRESULT OnHideUI();
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnHideUI` 에 반응 하는 `HideUI` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 에 대 한 자세한 내용은 합니다.  
  
##  <a name="onmenubar"></a>CHtmlView::OnMenuBar  
 프레임 워크에서이 멤버 함수를 호출 하는 경우는 [메뉴 모음](https://msdn.microsoft.com/library/aa752131.aspx) 속성이 변경 합니다.  
  
```  
virtual void OnMenuBar(BOOL bMenuBar);
```  
  
### <a name="parameters"></a>매개 변수  
 *bMenuBar*  
 Internet Explorer 메뉴 모음에 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
##  <a name="onnavigatecomplete2"></a>CHtmlView::OnNavigateComplete2  
 이 멤버 함수 (창이 나 프레임 요소)에 대 한 하이퍼링크를 탐색 완료 된 후 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnNavigateComplete2(LPCTSTR strURL);
```  
  
### <a name="parameters"></a>매개 변수  
 *strURL*  
 해당 URL로 계산 되는 문자열 식 UNC 파일 이름 또는 탐색 PIDL (식별자 목록 항목에 포인터).  
  
### <a name="remarks"></a>주의  
 URL 매개 변수는 셸 이름 공간 엔터티 URL 표현이 없기는 경우 PIDL 수 있습니다.  
  
 에 포함 된 URL을 *strURL* 이 URL은 정규화 된와 정규화 된 URL 때문에 브라우저를 이동 하 여을 들었습니다 URL에서 다를 수 있습니다. 예를 들어, 응용 프로그램에 대 한 호출에서 "www.microsoft.com"의 URL을 지정 하는 경우 [Navigate](#navigate) 또는 [Navigate2](#navigate2), 전달한 URL `OnNavigateComplete2` "http://www.microsoft.com/" 됩니다. 또한 서버가 다른 URL로 브라우저 리디렉션, 리디렉션된 URL 여기에 반영 됩니다.  
  
##  <a name="onnavigateerror"></a>CHtmlView::OnNavigateError  
 하이퍼링크로 이동이 실패할 경우 프레임워크에 의해 호출됩니다.  
  
```  
virtual void OnNavigateError(
    LPCTSTR lpszURL,  
    LPCTSTR lpszFrame,  
    DWORD dwError,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszURL`  
 URL 탐색 하지 못했습니다.  
  
 *lpszFrame*  
 리소스 표시, 또는 NULL 경우 리소스에 대 한 명명 된 프레임이 대상 프레임의 이름입니다.  
  
 `dwError`  
 오류 상태 코드를 사용할 수 있는 경우입니다. 가능한 HRESULT 및 HTTP 상태 코드 목록은 참조 하십시오. [NavigateError 이벤트 상태 코드입니다.](https://msdn.microsoft.com/library/aa768365.aspx)  
  
 `pbCancel`  
 오류 페이지 또는 모든 추가 자동 검색에 대 한 탐색을 취소할 것인지 지정 합니다. 경우 **TRUE** (기본값), 경우에 오류 페이지 또는 자동 검색;에 대 한 탐색을 계속 **FALSE**, 오류 페이지 또는 자동 검색에 대 한 탐색을 취소 합니다.  
  
### <a name="remarks"></a>주의  
 오류 처리 사용자 지정 탐색을 제공 하려면이 메서드를 재정의 합니다.  
  
 자세한 내용은 참조 [DWebBrowserEvents2::NavigateError](https://msdn.microsoft.com/library/aa768286.aspx)  
  
##  <a name="onnewwindow2"></a>CHtmlView::OnNewWindow2  
 이 멤버 함수는 새 창이 표시 된 리소스에 대해 생성 될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnNewWindow2(
    LPDISPATCH* ppDisp,  
    BOOL* Cancel);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppDisp`  
 필요에 따라 수신 하는 인터페이스 포인터에 대 한 포인터는 `IDispatch` 새 WebBrowser 또는 Internet Explorer 개체의 인터페이스 포인터입니다.  
  
 `Cancel`  
 취소 플래그에 대 한 포인터입니다. 응용 프로그램 탐색 작업을 취소 하거나 계속 진행 하도록 허용할 수&0;&0;이 아닌 값을이 매개 변수를 설정할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 이 이벤트 WebBrowser 내에서 창 새로 만드는 것 보다 우선 합니다.  
  
##  <a name="onprogresschange"></a>CHtmlView::OnProgressChange  
 이 멤버 함수는 다운로드 작업의 진행 상황 업데이트 된 응용 프로그램에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnProgressChange(
    long nProgress,  
    long nProgressMax);
```  
  
### <a name="parameters"></a>매개 변수  
 *nProgress*  
 표시, 또는-1 작업이 완료 되 면 총 진행률의 양입니다.  
  
 *nProgressMax*  
 최대 진행률 값입니다.  
  
### <a name="remarks"></a>주의  
 컨테이너 지금까지 다운로드 된 바이트 수를 표시 또는 진행률 표시기를 업데이트 하려면이 이벤트에서 제공 되는 정보를 사용할 수 있습니다.  
  
##  <a name="onpropertychange"></a>CHtmlView::OnPropertyChange  
 응용 프로그램에 알리기 위해 프레임 워크에서이 멤버 함수를 호출 하는 [의](#putproperty) 속성의 값이 변경 되었습니다.  
  
```  
virtual void OnPropertyChange(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProperty`  
 속성의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
##  <a name="onquit"></a>CHtmlView::OnQuit  
 이 멤버 함수는 Internet Explorer 응용 프로그램을 종료 준비가 된 응용 프로그램에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnQuit();
```  
  
##  <a name="onresizeborder"></a>CHtmlView::OnResizeBorder  
 Internet Explorer 또는 MSHTML 구현에서 호출 [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), 해당 테두리 공간 크기를 조정 하는 데 필요한 개체를 경고 하 합니다.  
  
```  
virtual HRESULT OnResizeBorder(
    LPCRECT prcBorder,  
    LPOLEINPLACEUIWINDOW pUIWindow,  
    BOOL fFrameWindow);
```  
  
### <a name="parameters"></a>매개 변수  
 `prcBorder`  
 테두리 공간에 대 한 새 외부 사각형입니다.  
  
 `pUIWindow`  
 테두리 변경 된 프레임 또는 문서 창 개체에 대 한 인터페이스에 대 한 포인터입니다.  
  
 `fFrameWindow`  
 **True 이면** 프레임 창을 호출 하는 경우 [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), 그렇지 않으면 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnResizeBorder` 에 반응 하는 `ResizeBorder` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onshowcontextmenu"></a>CHtmlView::OnShowContextMenu  
 상황에 맞는 메뉴를 표시하려는 경우 Internet Explorer 또는 MSHTML에 의해 호출됩니다.  
  
```  
virtual HRESULT OnShowContextMenu(
    DWORD dwID,  
    LPPOINT ppt,  
    LPUNKNOWN pcmdtReserved,  
    LPDISPATCH pdispReserved);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwID`  
 표시 되는 상황에 맞는 메뉴의 식별자입니다. 참조 **IDocHostUIHandler::ShowContextMenu** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
 `ppt`  
 메뉴에 대 한 화면 좌표입니다.  
  
 `pcmdtReserved`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) 명령 상태를 쿼리하고이 개체에서 명령을 실행 하는 데 사용 되는 인터페이스입니다.  
  
 `pdispReserved`  
 화면 좌표에 있는 개체의 IDispatch 인터페이스입니다. 따라서 보다 자세한 컨텍스트를 제공 하는 특정 개체를 구별 하는 호스트 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 참조 [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnShowContextMenu` 에 반응 하는 `ShowContextMenu` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onshowui"></a>CHtmlView::OnShowUI  
 Internet Explorer 또는 MSHTML이 해당 메뉴 및 도구 모음을 표시하기 전에 호출됩니다.  
  
```  
virtual HRESULT OnShowUI(
    DWORD dwID,  
    LPOLEINPLACEACTIVEOBJECT pActiveObject,  
    LPOLECOMMANDTARGET pCommandTarget,  
    LPOLEINPLACEFRAME pFrame,  
    LPOLEINPLACEUIWINDOW pDoc);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwID`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `pActiveObject`  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) 현재 활성화 된 개체의 인터페이스입니다.  
  
 `pCommandTarget`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) 개체의 인터페이스입니다.  
  
 `pFrame`  
 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) 개체의 인터페이스입니다. 메뉴 및 도구 모음을이 작업이 필요 합니다.  
  
 `pDoc`  
 [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) 개체에 대 한 인터페이스입니다. 도구 모음을이 작업이 필요 합니다.  
  
### <a name="return-value"></a>반환 값  
 참조 [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnShowUI` 에 반응 하는 `ShowUI` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 에 대 한 자세한 내용은 합니다.  
  
##  <a name="onstatusbar"></a>CHtmlView::OnStatusBar  
 프레임 워크에서이 멤버 함수를 호출 하는 경우는 [StatusBar](https://msdn.microsoft.com/library/aa768270.aspx) 속성이 변경 합니다.  
  
```  
virtual void OnStatusBar(BOOL bStatusBar);
```  
  
### <a name="parameters"></a>매개 변수  
 *bStatusBar*  
 Internet Explorer의 상태 표시줄 표시 되 면&0;이 아니고 그렇지 않으면&0;입니다.  
  
##  <a name="onstatustextchange"></a>CHtmlView::OnStatusTextChange  
 이 멤버 함수는 WebBrowser 컨트롤에 연결 된 상태 표시줄의 텍스트가 변경 하는 응용 프로그램에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnStatusTextChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 새 상태 표시줄 텍스트를 포함 하는 문자열입니다.  
  
##  <a name="ontheatermode"></a>CHtmlView::OnTheaterMode  
 프레임 워크에서이 멤버 함수를 호출 하는 경우는 [TheaterMode](https://msdn.microsoft.com/library/aa768273.aspx) 속성이 변경 합니다.  
  
```  
virtual void OnTheaterMode(BOOL bTheaterMode);
```  
  
### <a name="parameters"></a>매개 변수  
 *bTheaterMode*  
 Internet Explorer 극장 모드에 있으면&0;이 아닌 그렇지 않으면&0;입니다.  
  
##  <a name="ontitlechange"></a>CHtmlView::OnTitleChange  
 이 멤버 함수는 WebBrowser 컨트롤에서 문서의 제목을 사용할 수 있으면 응용 프로그램에 알리기 위해 프레임 워크 또는 변경에 의해 호출 됩니다.  
  
```  
virtual void OnTitleChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 새 문서 제목입니다.  
  
### <a name="remarks"></a>주의  
 HTML에 대 한 제목 변경 될 수 있습니다. HTML을 아직 다운로드 하는 동안에 문서의 URL 제목으로 설정 됩니다. 실제 제목 (있는 경우)에서 구문 분석 된 HTML, 후 제목 실제 제목을 반영 하도록 변경 됩니다.  
  
##  <a name="ontoolbar"></a>CHtmlView::OnToolBar  
 프레임 워크에서이 멤버 함수를 호출 하는 경우는 [도구 모음](https://msdn.microsoft.com/library/aa768274.aspx) 속성이 변경 합니다.  
  
```  
virtual void OnToolBar(BOOL bToolBar);
```  
  
### <a name="parameters"></a>매개 변수  
 *bToolBar*  
 Internet Explorer의 도구 모음을 표시 하는 경우&0;이 아니고 그렇지 않으면&0;입니다.  
  
##  <a name="ontranslateaccelerator"></a>CHtmlView::OnTranslateAccelerator  
 Internet Explorer 또는 MSHTML 호출 때 [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) 또는 [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) 컨테이너의 메시지 큐에서 메뉴 바로 가기 키 메시지를 처리 하기 위해 호출 됩니다.  
  
```  
virtual HRESULT OnTranslateAccelerator(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMsg`  
 번역 해야 하는 메시지를 가리킵니다.  
  
 `pguidCmdGroup`  
 명령 그룹 식별자입니다.  
  
 `nCmdID`  
 명령 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 **S_FALSE** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 재정의 `OnTranslateAccelerator` 에 반응 하는 `TranslateAccelerator` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 에 대 한 자세한 내용은 합니다.  
  
##  <a name="ontranslateurl"></a>CHtmlView::OnTranslateUrl  
 호스트가 로드할 URL을 수정할 수 있도록 하기 위해 Internet Explorer 또는 MSHTML에 의해 호출됩니다.  
  
```  
virtual HRESULT OnTranslateUrl(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwTranslate`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `pchURLIn`  
 Internet Explorer 또는 변환 하는 URL을 나타내는 MSHTML에서 제공 하는 문자열의 주소입니다.  
  
 `ppchURLOut`  
 번역 된 URL의 주소를 수신 하는 문자열 포인터의 주소입니다. 호스트는 작업 메모리 할당자를 사용 하 여 버퍼를 할당 합니다. 이 매개 변수 콘텐츠를 항상 초기화 **NULL**URL 변환 되지 않는 또는 메서드가 실패 하는 경우에 합니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`URL 변환 된 경우 **S_FALSE** URL 없이 번역 되지 않습니다 하는 경우 또는 OLE 정의 된 오류 코드에 오류가 발생 합니다.  
  
### <a name="remarks"></a>주의  
 재정의 `OnTranslateUrl` 에 반응 하는 `TranslateUrl` Microsoft의 웹 브라우저 컨트롤에서 알림. 참조 [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
##  <a name="onupdateui"></a>CHtmlView::OnUpdateUI  
 명령 상태가 변경되었음을 호스트에 알립니다.  
  
```  
virtual HRESULT OnUpdateUI();
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 호스트의 도구 모음 단추 상태를 업데이트 해야 합니다. 반환 된 값에 관계 없이이 메서드는 `ShowUI`합니다. 재정의 `OnUpdateUI` 에 반응 하는 `UpdateUI` Microsoft의 웹 브라우저 컨트롤에서 알림.  
  
##  <a name="onvisible"></a>CHtmlView::OnVisible  
 이 멤버 함수는 WebBrowser 창을 표시 하거나 숨길 수 해야 하는 경우 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnVisible(BOOL bVisible);
```  
  
### <a name="parameters"></a>매개 변수  
 `bVisible`  
 개체를 표시 하는 경우&0;이 아니고 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이렇게 하면 Internet Explorer 창이 작동 하는 동일한 방식으로 동작 하는 개체 컨트롤 호스트 창.  
  
##  <a name="putproperty"></a>CHtmlView::PutProperty  
 지정된 된 개체와 연결 된 속성을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void PutProperty(
    LPCTSTR lpszProperty,  
    const VARIANT& vtValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    double dValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    long lValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    LPCTSTR lpszValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    short nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProperty`  
 설정할 속성을 포함 하는 문자열입니다.  
  
 *vtValue*  
 속성의 새 값으로 표시 `lpszProperty`합니다.  
  
 *lpszPropertyName*  
 설정할 속성의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *dValue*  
 속성의 새 값입니다.  
  
 `lValue`  
 속성의 새 값입니다.  
  
 `lpszValue`  
 속성의 새 값을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nValue`  
 속성의 새 값입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="queryformscommand"></a>CHtmlView::QueryFormsCommand  
 사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.  
  
```  
HRESULT QueryFormsCommand(
    DWORD dwCommandID,  
    BOOL* pbSupported,  
    BOOL* pbEnabled,  
    BOOL* pbChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCommandID`  
 식별자에 대 한 쿼리 중인 명령입니다.  
  
 *pbSupported*  
 에 대 한 포인터는 **BOOL** 지정 하는 경우 명령 (으로 식별 `dwCommandID`) 지원 됩니다. True 이면 명령이 지원 됩니다. 그렇지 않으면 FALSE입니다.  
  
 `pbEnabled`  
 에 대 한 포인터는 **BOOL** 지정 하는 경우 명령 (로 식별 되 `dwCommandID`)를 사용할 수 있습니다. True 이면 명령이 지원 됩니다. 그렇지 않으면 FALSE입니다.  
  
 *pbChecked*  
 에 대 한 포인터는 **BOOL** 지정할 경우 명령 (으로 식별 `dwCommandID`)가 선택 되어 있습니다. True 이면 명령이 지원 됩니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다. 가능한 값의 전체 목록을 보려면 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 `QueryFormsCommand`동작을 구현 하는 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) 메서드.  
  
##  <a name="querystatuswb"></a>CHtmlView::QueryStatusWB  
 명령 상태 쿼리를이 멤버 함수를 호출 합니다.  
  
```  
OLECMDF QueryStatusWB(OLECMDID cmdID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 [OLECMDID](http://msdn.microsoft.com/library/windows/desktop/ms691264) 호출자가 상태 정보를 필요로 하는 명령 값입니다.  
  
### <a name="return-value"></a>반환 값  
 주소는 [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) 명령의 상태를 수신 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 `QueryStatusWB`동작을 구현 하는 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) 메서드.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="refresh"></a>CHtmlView::Refresh  
 URL 또는 현재 웹 브라우저를 표시 하는 파일을 다시 로드 합니다.  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>주의  
 **새로 고침** 새로 고침 수준 설정에 대 한 매개 변수를 포함 합니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="refresh2"></a>CHtmlView::Refresh2  
 현재 Internet Explorer를 표시 하는 파일을 다시 로드 합니다.  
  
```  
void Refresh2(int nLevel);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLevel`  
 새로 고침 수준을 지정 하는 변수의 주소입니다. 가능한 변수에 정의 된 [RefreshConstants](https://msdn.microsoft.com/library/aa768363.aspx)에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 와 달리 [새로 고침](#refresh), `Refresh2` 새로 고침 수준을 지정 하는 매개 변수를 포함 합니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setaddressbar"></a>CHtmlView::SetAddressBar  
 이 멤버 함수는 Internet Explorer 개체의 주소 표시줄 표시 / 숨기기를 호출 합니다.  
  
```  
void SetAddressBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 주소 표시줄을 표시 하려면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="setfullscreen"></a>CHtmlView::SetFullScreen  
 Internet Explorer 두 창 전체 화면 또는 표준 모드를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetFullScreen(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 전체 화면 모드에 대해&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 전체 화면 모드에서 Internet Explorer 주 창을 최대화 하 고 상태 표시줄, 도구 모음, 메뉴 모음 및 제목 표시줄 숨겨집니다.  
  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="setheight"></a>CHtmlView::SetHeight  
 Internet Explorer 주 창의 높이 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetHeight(long nNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewValue`  
 주 창의 픽셀 높이입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setleft"></a>CHtmlView::SetLeft  
 Internet Explorer 주 창의 가로 위치를 설정합니다.  
  
```  
void SetLeft(long nNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewValue`  
 주 창의 왼쪽된 가장자리의 화면 좌표입니다.  
  
##  <a name="setmenubar"></a>CHtmlView::SetMenuBar  
 Internet Explorer 메뉴 표시줄 표시 / 숨기기를이 멤버 함수를 호출 합니다.  
  
```  
void SetMenuBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 메뉴 모음; 표시에&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="setoffline"></a>CHtmlView::SetOffline  
 WebBrowser 컨트롤은 오프 라인 모드에서 현재 작동 하 고 있는지 여부를 나타내는 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetOffline(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 로컬 캐시에서 읽을 수는&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 오프 라인 모드에서 브라우저는 소스 문서 대신 로컬 캐시에서 HTML 페이지를 읽습니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setregisterasbrowser"></a>CHtmlView::SetRegisterAsBrowser  
 WebBrowser 컨트롤 대상 이름 확인에 대 한 최상위 브라우저로 등록 되어 있는지 여부를 나타내는 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetRegisterAsBrowser(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 Internet Explorer 최상위 브라우저로 등록 되어 있는지 여부를 결정 합니다. 웹 브라우저 최상위 브라우저;로 등록 되어 있으면&0;이 아닌 경우&0; 이면 최상위 브라우저 않습니다. 기본값은&0;입니다.  
  
### <a name="remarks"></a>주의  
 최상위 브라우저는 레지스트리에 기본 브라우저로 설정 하는 브라우저입니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setregisterasdroptarget"></a>CHtmlView::SetRegisterAsDropTarget  
 WebBrowser 컨트롤 탐색에 대 한 놓기 대상으로 등록 되었는지 여부를 나타내는 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetRegisterAsDropTarget(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 WebBrowser 컨트롤 탐색에 대 한 놓기 대상으로 등록 되어 있는지 확인 합니다. 0이 아니면는 개체는 놓기 대상;로 등록&0; 이면 놓기 대상 않습니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setsilent"></a>CHtmlView::SetSilent  
 모든 대화 상자를 표시할 수 있는지 여부를 나타내는 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetSilent(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 0이 아니면 대화 상자가 표시 되지 않습니다.&0; 이면 대화 상자가 표시 됩니다. 기본값은&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setstatusbar"></a>CHtmlView::SetStatusBar  
 상태 표시줄을 표시 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetStatusBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 상태 표시줄 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="settheatermode"></a>CHtmlView::SetTheaterMode  
 WebBrowser 컨트롤 극장 모드 인지 여부를 나타내는 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetTheaterMode(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 WebBrowser 컨트롤 극장 모드를 설정 하려면&0;이 아닌 그렇지 않으면&0;입니다. 기본값은&0;입니다.  
  
### <a name="remarks"></a>주의  
 웹 브라우저 극장 모드에 있을 때 브라우저 창의 전체 화면을 채웁니다, 그리고 최소 탐색 도구 집합이 있는 도구 모음을 나타나고 상태 표시줄을 화면의 오른쪽 아래 모서리에 표시 합니다.  
  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="settoolbar"></a>CHtmlView::SetToolBar  
 이 멤버 함수를 Internet Explorer 도구 모음을 표시할지를 호출 합니다.  
  
```  
void SetToolBar(int nNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewValue`  
 도구 모음을 표시할지 여부를 나타냅니다. 도구 모음이 표시 됩니다.&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer에 적용 됩니다. 이 호출은 WebBrowser 컨트롤을 사용 하면 오류가 반환 됩니다 있지만이 호출을 무시 합니다.  
  
##  <a name="settop"></a>CHtmlView::SetTop  
 WebBrowser 컨트롤의 내부 위쪽 가장자리와 해당 컨테이너의 위쪽 가장자리 사이의 거리를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetTop(long nNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewValue`  
 주 창의 위쪽 가장자리의 화면 좌표입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setvisible"></a>CHtmlView::SetVisible  
 WebBrowser 컨트롤의 표시 여부 상태를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetVisible(BOOL bNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNewValue`  
 컨트롤이 표시 되 면&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
##  <a name="setwidth"></a>CHtmlView::SetWidth  
 Internet Explorer 주 창의 너비를 설정합니다.  
  
```  
void SetWidth(long nNewValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewValue`  
 Internet Explorer 주 창의 픽셀 너비입니다.  
  
##  <a name="stop"></a>CHtmlView::Stop  
 또는 보류 중인 모든 탐색을 취소 하 고, 작업을 다운로드 하 고, 배경 소리 및 애니메이션과 같은 모든 동적 페이지 요소를 중지 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Stop();
```  
  
### <a name="remarks"></a>주의  
 Internet Explorer 및 WebBrowser에 적용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MFCIE](../../visual-cpp-samples.md)   
 [CFormView 클래스](../../mfc/reference/cformview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)


