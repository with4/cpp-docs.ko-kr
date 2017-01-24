---
title: "CHtmlView 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "브라우저, MFC 지원"
  - "CHtmlView 클래스"
  - "WebBrowser 컨트롤"
  - "WebBrowser 컨트롤, MFC 지원"
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlView 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC의 문서\/뷰 아키텍처 컨텍스트 내에서 WebBrowser 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CHtmlView : public CFormView  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CHtmlView::Create](../Topic/CHtmlView::Create.md)|WebBrowser 컨트롤을 만듭니다.|  
|[CHtmlView::CreateControlSite](../Topic/CHtmlView::CreateControlSite.md)|폼에서 컨트롤을 호스트할 컨트롤 사이트 인스턴스를 만드는 데 사용되는 Overridable입니다.|  
|[CHtmlView::ExecFormsCommand](../Topic/CHtmlView::ExecFormsCommand.md)|`IOleCommandTarget::Exec` 메서드를 사용하여 지정된 명령을 실행합니다.|  
|[CHtmlView::ExecWB](../Topic/CHtmlView::ExecWB.md)|명령을 실행합니다.|  
|[CHtmlView::GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)|Internet Explorer 개체의 주소 표시줄을 표시할지 여부를 결정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::GetApplication](../Topic/CHtmlView::GetApplication.md)|Internet Explorer 응용 프로그램의 현재 인스턴스를 포함하는 응용 프로그램을 나타내는 응용 프로그램 개체를 검색합니다.|  
|[CHtmlView::GetBusy](../Topic/CHtmlView::GetBusy.md)|다운로드 또는 기타 작업이 계속 진행 중인지 여부를 나타내는 값을 검색합니다.|  
|[CHtmlView::GetContainer](../Topic/CHtmlView::GetContainer.md)|WebBrowser 컨트롤의 컨테이너를 검색합니다.|  
|[CHtmlView::GetFullName](../Topic/CHtmlView::GetFullName.md)|웹 브라우저에 표시되는 리소스의 전체 이름\(경로 포함\)을 검색합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::GetFullScreen](../Topic/CHtmlView::GetFullScreen.md)|WebBrowser 컨트롤이 전체 화면 모드 또는 표준 창 모드로 작동 중인지를 나타냅니다.|  
|[CHtmlView::GetHeight](../Topic/CHtmlView::GetHeight.md)|Internet Explorer 주 창의 높이를 검색합니다.|  
|[CHtmlView::GetHtmlDocument](../Topic/CHtmlView::GetHtmlDocument.md)|활성 HTML 문서를 검색합니다.|  
|[CHtmlView::GetLeft](../Topic/CHtmlView::GetLeft.md)|Internet Explorer 주 창에서 왼쪽 가장자리의 화면 좌표를 검색합니다.|  
|[CHtmlView::GetLocationName](../Topic/CHtmlView::GetLocationName.md)|현재 WebBrowser에 표시되는 리소스의 이름을 검색합니다.|  
|[CHtmlView::GetLocationURL](../Topic/CHtmlView::GetLocationURL.md)|현재 WebBrowser에 표시되는 리소스의 URL을 검색합니다.|  
|[CHtmlView::GetMenuBar](../Topic/CHtmlView::GetMenuBar.md)|메뉴 모음을 표시할지 여부를 결정하는 값을 검색합니다.|  
|[CHtmlView::GetOffline](../Topic/CHtmlView::GetOffline.md)|컨트롤이 오프라인 상태인지 여부를 결정하는 값을 검색합니다.|  
|[CHtmlView::GetParentBrowser](../Topic/CHtmlView::GetParentBrowser.md)|`IDispatch` 인터페이스에 대한 포인터를 검색합니다. 자세한 내용은 [Implementing the IDispatch Interface](http://msdn.microsoft.com/ko-kr/0e171f7f-0022-4e9b-ac8e-98192828e945)을 참조하십시오.|  
|[CHtmlView::GetProperty](../Topic/CHtmlView::GetProperty.md)|지정된 개체와 연결된 속성의 현재 값을 검색합니다.|  
|[CHtmlView::GetReadyState](../Topic/CHtmlView::GetReadyState.md)|웹 브라우저 개체의 준비 상태를 검색합니다.|  
|[CHtmlView::GetRegisterAsBrowser](../Topic/CHtmlView::GetRegisterAsBrowser.md)|WebBrowser 컨트롤이 대상 이름 확인을 위한 최상위 브라우저로 등록되었는지 여부를 나타냅니다.|  
|[CHtmlView::GetRegisterAsDropTarget](../Topic/CHtmlView::GetRegisterAsDropTarget.md)|WebBrowser 컨트롤이 탐색을 위한 놓기 대상으로 등록되었는지 여부를 나타냅니다.|  
|[CHtmlView::GetSilent](../Topic/CHtmlView::GetSilent.md)|대화 상자를 표시할 수 있는지 여부를 나타냅니다.|  
|[CHtmlView::GetSource](../Topic/CHtmlView::GetSource.md)|웹 페이지의 HTML 소스 코드입니다.|  
|[CHtmlView::GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)|Internet Explorer의 상태 표시줄을 표시할지 여부를 나타냅니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::GetTheaterMode](../Topic/CHtmlView::GetTheaterMode.md)|WebBrowser 컨트롤이 극장 모드인지 여부를 나타냅니다.|  
|[CHtmlView::GetToolBar](../Topic/CHtmlView::GetToolBar.md)|도구 모음을 표시할지 여부를 결정하는 값을 검색합니다.|  
|[CHtmlView::GetTop](../Topic/CHtmlView::GetTop.md)|Internet Explorer 주 창에서 위쪽 가장자리의 화면 좌표를 검색합니다.|  
|[CHtmlView::GetTopLevelContainer](../Topic/CHtmlView::GetTopLevelContainer.md)|현재 개체가 WebBrowser 컨트롤의 최상위 컨테이너인지 여부를 나타내는 값을 검색합니다.|  
|[CHtmlView::GetType](../Topic/CHtmlView::GetType.md)|문서 개체의 형식 이름을 검색합니다.|  
|[CHtmlView::GetVisible](../Topic/CHtmlView::GetVisible.md)|개체를 표시할지 또는 숨길지를 나타내는 값을 검색합니다.|  
|[CHtmlView::GetWidth](../Topic/CHtmlView::GetWidth.md)|Internet Explorer 주 창의 너비를 검색합니다.|  
|[CHtmlView::GoBack](../Topic/CHtmlView::GoBack.md)|기록 목록에서 이전 항목으로 이동합니다.|  
|[CHtmlView::GoForward](../Topic/CHtmlView::GoForward.md)|기록 목록에서 다음 항목으로 이동합니다.|  
|[CHtmlView::GoHome](../Topic/CHtmlView::GoHome.md)|현재 홈페이지 또는 시작 페이지로 이동합니다.|  
|[CHtmlView::GoSearch](../Topic/CHtmlView::GoSearch.md)|현재 검색 페이지로 이동합니다.|  
|[CHtmlView::LoadFromResource](../Topic/CHtmlView::LoadFromResource.md)|WebBrowser 컨트롤에 리소스를 로드합니다.|  
|[CHtmlView::Navigate](../Topic/CHtmlView::Navigate.md)|URL로 식별된 리소스로 이동합니다.|  
|[CHtmlView::Navigate2](../Topic/CHtmlView::Navigate2.md)|URL로 식별된 리소스 또는 전체 경로로 식별된 파일로 이동합니다.|  
|[CHtmlView::OnBeforeNavigate2](../Topic/CHtmlView::OnBeforeNavigate2.md)|창 또는 프레임셋 요소에 지정된 WebBrowser에서 이동하기 전에 호출됩니다.|  
|[CHtmlView::OnCommandStateChange](../Topic/CHtmlView::OnCommandStateChange.md)|웹 브라우저 명령의 사용 상태가 변경되었음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnDocumentComplete](../Topic/CHtmlView::OnDocumentComplete.md)|문서가 `READYSTATE_COMPLETE` 상태에 도달했음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnDocWindowActivate](../Topic/CHtmlView::OnDocWindowActivate.md)|[IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281)의 Internet Explorer 또는 MSHTML 구현에서 호출되며, 컨테이너의 문서 창이 활성화 또는 비활성화될 경우 활성 현재 위치 개체에 알립니다.|  
|[CHtmlView::OnDownloadBegin](../Topic/CHtmlView::OnDownloadBegin.md)|이동 작업이 시작되었음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnDownloadComplete](../Topic/CHtmlView::OnDownloadComplete.md)|이동 작업이 중단 또는 실패한 상태로 마치면 호출됩니다.|  
|[CHtmlView::OnEnableModeless](../Topic/CHtmlView::OnEnableModeless.md)|컨테이너가 모달 대화 상자를 만들거나 삭제할 때 모덜리스 대화 상자를 사용하거나 사용하지 않도록 설정하기 위해 호출됩니다.|  
|[CHtmlView::OnFilterDataObject](../Topic/CHtmlView::OnFilterDataObject.md)|호스트가 Internet Explorer 또는 MSHTML의 데이터 개체를 바꿀 수 있도록 하기 위해 Internet Explorer 또는 MSHTML에 의해 호스트에서 호출됩니다.|  
|[CHtmlView::OnFrameWindowActivate](../Topic/CHtmlView::OnFrameWindowActivate.md)|컨테이너의 최상위 프레임 창이 활성화 또는 비활성화될 경우 개체에 알리기 위해 [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)에서 호출됩니다.|  
|[CHtmlView::OnFullScreen](../Topic/CHtmlView::OnFullScreen.md)|FullScreen 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnGetDropTarget](../Topic/CHtmlView::OnGetDropTarget.md)|호스트가 대체 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)을 제공할 수 있도록 놓기 대상으로 사용되는 경우 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnGetExternal](../Topic/CHtmlView::OnGetExternal.md)|호스트의 `IDispatch` 인터페이스를 가져오기 위해 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnGetHostInfo](../Topic/CHtmlView::OnGetHostInfo.md)|Internet Explorer 또는 MSHTML 호스트의 UI 기능을 검색합니다.|  
|[CHtmlView::OnGetOptionKeyPath](../Topic/CHtmlView::OnGetOptionKeyPath.md)|Internet Explorer 또는 MSHTML이 사용자 기본 설정을 저장하는 레지스트리 키를 반환합니다.|  
|[CHtmlView::OnHideUI](../Topic/CHtmlView::OnHideUI.md)|Internet Explorer 또는 MSHTML이 해당 메뉴 및 도구 모음을 제거하면 호출됩니다.|  
|[CHtmlView::OnMenuBar](../Topic/CHtmlView::OnMenuBar.md)|MenuBar 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnNavigateComplete2](../Topic/CHtmlView::OnNavigateComplete2.md)|창 또는 프레임셋 요소의 하이퍼링크로 이동한 후에 호출됩니다.|  
|[CHtmlView::OnNavigateError](../Topic/CHtmlView::OnNavigateError.md)|하이퍼링크로 이동이 실패할 경우 프레임워크에 의해 호출됩니다.|  
|[CHtmlView::OnNewWindow2](../Topic/CHtmlView::OnNewWindow2.md)|리소스를 표시하기 위해 새 창이 만들어지면 호출됩니다.|  
|[CHtmlView::OnProgressChange](../Topic/CHtmlView::OnProgressChange.md)|다운로드 작업 진행률이 업데이트되었음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnPropertyChange](../Topic/CHtmlView::OnPropertyChange.md)|[PutProperty](../Topic/CHtmlView::PutProperty.md) 메서드가 속성 값을 변경했음을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnQuit](../Topic/CHtmlView::OnQuit.md)|Internet Explorer 응용 프로그램을 끝낼 준비가 되었음을 응용 프로그램에 알리기 위해 호출됩니다. \(Internet Explorer에만 적용됨\)|  
|[CHtmlView::OnResizeBorder](../Topic/CHtmlView::OnResizeBorder.md)|[IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053)의 Internet Explorer 또는 MSHTML 구현에서 호출되며, 해당 테두리 공간 크기를 조정해야 함을 개체에 경고합니다.|  
|[CHtmlView::OnShowContextMenu](../Topic/CHtmlView::OnShowContextMenu.md)|상황에 맞는 메뉴를 표시하려는 경우 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnShowUI](../Topic/CHtmlView::OnShowUI.md)|Internet Explorer 또는 MSHTML이 해당 메뉴 및 도구 모음을 표시하기 전에 호출됩니다.|  
|[CHtmlView::OnStatusBar](../Topic/CHtmlView::OnStatusBar.md)|StatusBar 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnStatusTextChange](../Topic/CHtmlView::OnStatusTextChange.md)|응용 프로그램에 WebBrowser 컨트롤과 연결된 상태 표시줄의 텍스트가 변경되었음을 알리기 위해 호출됩니다.|  
|[CHtmlView::OnTheaterMode](../Topic/CHtmlView::OnTheaterMode.md)|TheaterMode 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnTitleChange](../Topic/CHtmlView::OnTitleChange.md)|WebBrowser 컨트롤의 문서 제목을 사용할 수 있게 되거나 변경할 경우 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CHtmlView::OnToolBar](../Topic/CHtmlView::OnToolBar.md)|ToolBar 속성이 변경되면 호출됩니다.|  
|[CHtmlView::OnTranslateAccelerator](../Topic/CHtmlView::OnTranslateAccelerator.md)|컨테이너의 메시지 큐에서 메뉴 바로 가기 키 메시지를 처리하기 위해 [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) 또는 [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756)가 호출될 경우 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnTranslateUrl](../Topic/CHtmlView::OnTranslateUrl.md)|호스트가 로드할 URL을 수정할 수 있도록 하기 위해 Internet Explorer 또는 MSHTML에 의해 호출됩니다.|  
|[CHtmlView::OnUpdateUI](../Topic/CHtmlView::OnUpdateUI.md)|명령 상태가 변경되었음을 호스트에 알립니다.|  
|[CHtmlView::OnVisible](../Topic/CHtmlView::OnVisible.md)|WebBrowser 컨트롤의 창을 표시하거나 숨기면 호출됩니다.|  
|[CHtmlView::PutProperty](../Topic/CHtmlView::PutProperty.md)|지정된 개체와 연결된 속성의 값을 설정합니다.|  
|[CHtmlView::QueryFormsCommand](../Topic/CHtmlView::QueryFormsCommand.md)|사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.|  
|[CHtmlView::QueryStatusWB](../Topic/CHtmlView::QueryStatusWB.md)|WebBrowser 컨트롤에 의해 처리되는 명령의 상태를 쿼리합니다.|  
|[CHtmlView::Refresh](../Topic/CHtmlView::Refresh.md)|현재 파일을 다시 로드합니다.|  
|[CHtmlView::Refresh2](../Topic/CHtmlView::Refresh2.md)|현재 파일을 다시 로드하고 필요에 따라 `pragma:nocache` 헤더가 전송되지 않도록 합니다.|  
|[CHtmlView::SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)|Internet Explorer 개체의 주소 표시줄을 표시하거나 숨깁니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)|컨트롤이 전체 화면 모드 또는 표준 창 모드로 작동 중인지를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetHeight](../Topic/CHtmlView::SetHeight.md)|Internet Explorer 주 창의 높이를 설정합니다.|  
|[CHtmlView::SetLeft](../Topic/CHtmlView::SetLeft.md)|Internet Explorer 주 창의 가로 위치를 설정합니다.|  
|[CHtmlView::SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)|컨트롤의 메뉴 모음을 표시할지 여부를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetOffline](../Topic/CHtmlView::SetOffline.md)|컨트롤이 오프라인 상태인지 여부를 결정할 값을 설정합니다.|  
|[CHtmlView::SetRegisterAsBrowser](../Topic/CHtmlView::SetRegisterAsBrowser.md)|WebBrowser 컨트롤이 대상 이름 확인을 위한 최상위 브라우저로 등록되었는지 여부를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetRegisterAsDropTarget](../Topic/CHtmlView::SetRegisterAsDropTarget.md)|WebBrowser 컨트롤이 탐색을 위한 놓기 대상으로 등록되었는지 여부를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetSilent](../Topic/CHtmlView::SetSilent.md)|컨트롤이 대화 상자를 표시할지 여부를 결정할 값을 설정합니다.|  
|[CHtmlView::SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)|Internet Explorer의 상태 표시줄을 표시할지 여부를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetTheaterMode](../Topic/CHtmlView::SetTheaterMode.md)|WebBrowser 컨트롤이 극장 모드인지 여부를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetToolBar](../Topic/CHtmlView::SetToolBar.md)|컨트롤의 도구 모음을 표시할지 여부를 결정할 값을 설정합니다. WebBrowser 컨트롤은 무시됩니다. Internet Explorer에만 해당합니다.|  
|[CHtmlView::SetTop](../Topic/CHtmlView::SetTop.md)|Internet Explorer 주 창의 세로 위치를 설정합니다.|  
|[CHtmlView::SetVisible](../Topic/CHtmlView::SetVisible.md)|개체를 표시할지 또는 숨길지를 나타내는 값을 설정합니다.|  
|[CHtmlView::SetWidth](../Topic/CHtmlView::SetWidth.md)|Internet Explorer 주 창의 너비를 설정합니다.|  
|[CHtmlView::Stop](../Topic/CHtmlView::Stop.md)|파일 열기를 중지합니다.|  
  
## 설명  
 WebBrowser 컨트롤은 사용자가 로컬 파일 시스템과 네트워크의 폴더뿐 아니라 World Wide Web에서 사이트를 찾을 수 있는 창입니다. WebBrowser 컨트롤은 하이퍼링크와 URL\(Uniform Resource Locator\) 탐색을 지원하고 기록 목록을 유지 관리합니다.  
  
## MFC 응용 프로그램에서 CHtmlView 클래스 사용  
 표준 MFC 프레임워크 응용 프로그램\(SDI 또는 MDI 기반\)에서 뷰 개체는 일반적으로 특수한 클래스 집합에서 파생됩니다. 이러한 클래스는 모두 `CView`에서 파생되며, `CView`에서 제공하는 것 이상의 특수 기능을 제공합니다.  
  
 응용 프로그램의 뷰 클래스가 `CHtmlView`를 기반으로 하는 경우 뷰에 WebBrowser 컨트롤이 제공됩니다. 이렇게 하면 실제로 응용 프로그램이 웹 브라우저가 됩니다. 웹 브라우저 스타일 응용 프로그램을 만드는 기본 방법은 MFC 응용 프로그램 마법사를 사용하고 `CHtmlView`를 뷰 클래스로 지정하는 것입니다. MFC 응용 프로그램 내에서 WebBrowser 컨트롤을 구현 및 사용하는 방법에 대한 자세한 내용은 [웹 브라우저 스타일 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)를 참조하세요.  
  
> [!NOTE]
>  WebBrowser ActiveX 컨트롤\(및 따라서 `CHtmlView`\)은 Internet Explorer 4.0 이상이 설치된 Windows NT 버전 4.0 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.  
  
 `CHtmlView`는 웹\(및\/또는 HTML 문서\)에 액세스하는 응용 프로그램용으로 작성되었습니다. 다음 `CHtmlView` 멤버 함수는 Internet Explorer 응용 프로그램에만 적용됩니다. 해당 함수는 WebBrowser 컨트롤에서 성공하지만 아무런 가시적 효과가 없습니다.  
  
-   [GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)  
  
-   [GetFullName](../Topic/CHtmlView::GetFullName.md)  
  
-   [GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)  
  
-   [SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)  
  
-   [SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)  
  
-   [SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)  
  
-   [SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)  
  
-   [SetToolBar](../Topic/CHtmlView::SetToolBar.md)  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## 요구 사항  
 **헤더:** afxhtml.h  
  
## 참고 항목  
 [MFC 샘플 MFCIE](../../top/visual-cpp-samples.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx)