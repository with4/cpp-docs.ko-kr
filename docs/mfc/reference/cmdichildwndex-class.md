---
title: CMDIChildWndEx 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWndEx [MFC], ActivateTopLevelFrame
- CMDIChildWndEx [MFC], AddPane
- CMDIChildWndEx [MFC], AddTabbedPane
- CMDIChildWndEx [MFC], AdjustDockingLayout
- CMDIChildWndEx [MFC], CanShowOnMDITabs
- CMDIChildWndEx [MFC], CanShowOnTaskBarTabs
- CMDIChildWndEx [MFC], CanShowOnWindowsList
- CMDIChildWndEx [MFC], DockPane
- CMDIChildWndEx [MFC], DockPaneLeftOf
- CMDIChildWndEx [MFC], EnableAutoHidePanes
- CMDIChildWndEx [MFC], EnableDocking
- CMDIChildWndEx [MFC], EnableTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetDockingManager
- CMDIChildWndEx [MFC], GetDocumentName
- CMDIChildWndEx [MFC], GetFrameIcon
- CMDIChildWndEx [MFC], GetFrameText
- CMDIChildWndEx [MFC], GetPane
- CMDIChildWndEx [MFC], GetRelatedTabGroup
- CMDIChildWndEx [MFC], GetTabbedPane
- CMDIChildWndEx [MFC], GetTabProxyWnd
- CMDIChildWndEx [MFC], GetTaskbarPreviewWnd
- CMDIChildWndEx [MFC], GetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetToolbarButtonToolTipText
- CMDIChildWndEx [MFC], InsertPane
- CMDIChildWndEx [MFC], InvalidateIconicBitmaps
- CMDIChildWndEx [MFC], IsPointNearDockSite
- CMDIChildWndEx [MFC], IsReadOnly
- CMDIChildWndEx [MFC], IsRegisteredWithTaskbarTabs
- CMDIChildWndEx [MFC], IsTabbedPane
- CMDIChildWndEx [MFC], IsTaskbarTabsSupportEnabled
- CMDIChildWndEx [MFC], IsTaskbarThumbnailClipRectEnabled
- CMDIChildWndEx [MFC], m_dwDefaultTaskbarTabPropertyFlags
- CMDIChildWndEx [MFC], OnGetIconicLivePreviewBitmap
- CMDIChildWndEx [MFC], OnGetIconicThumbnail
- CMDIChildWndEx [MFC], OnMoveMiniFrame
- CMDIChildWndEx [MFC], OnPressTaskbarThmbnailCloseButton
- CMDIChildWndEx [MFC], OnSetPreviewMode
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailMouseActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailStretch
- CMDIChildWndEx [MFC], OnUpdateFrameTitle
- CMDIChildWndEx [MFC], PaneFromPoint
- CMDIChildWndEx [MFC], RecalcLayout
- CMDIChildWndEx [MFC], RegisterTaskbarTab
- CMDIChildWndEx [MFC], RemovePaneFromDockManager
- CMDIChildWndEx [MFC], SetRelatedTabGroup
- CMDIChildWndEx [MFC], SetTaskbarTabActive
- CMDIChildWndEx [MFC], SetTaskbarTabOrder
- CMDIChildWndEx [MFC], SetTaskbarTabProperties
- CMDIChildWndEx [MFC], SetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], ShowPane
- CMDIChildWndEx [MFC], UnregisterTaskbarTab
- CMDIChildWndEx [MFC], UpdateTaskbarTabIcon
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 906e956bae9bce14c83d938218f51dfea9288b96
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041892"
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx 클래스
`CMDIChildWndEx` 클래스 다중 문서 MDI (인터페이스) 자식 창 Windows의 기능을 제공 합니다. 기능을 확장 [CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)합니다. MDI 응용 프로그램에서 특정 MFC 클래스를 사용하면 프레임워크에 이 클래스가 필요합니다.  
 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  

  
## <a name="syntax"></a>구문  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|작업 표시줄 탭에서 응용 프로그램을 활성화 해야 하는 경우 최상위 수준 프레임을 활성화 하기 위해 프레임 워크에서 내부적으로 호출 합니다.|  
|`CMDIChildWndEx::AddDockSite`|이 메서드는 사용 되지 않거나 구현 합니다.|  
|[CMDIChildWndEx::AddPane](#addpane)|창을 추가합니다.|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|탭된 창에 추가합니다.|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|도킹 레이아웃을 조정합니다.|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Windows 7 작업 표시줄 탭에 MDI 자식이 표시 될 수 있는지 여부 프레임 워크에 지시 합니다.|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|반환 `TRUE` MDI 자식 창 이름에 표시할 수 있습니다는 [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자. 그렇지 않으면 `FALSE`를 반환합니다.|  
|`CMDIChildWndEx::CreateObject`|이 클래스 형식의 동적 인스턴스를 만드는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::DockPane](#dockpane)|창을 도킹합니다.|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|수 있도록 자동 숨기기 모드를 창에 대 한 지정 된 창 측면에 도킹 된 경우.|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|주 프레임에 사용 하면 자식 창의 도킹 합니다.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분의 자동 선택을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|MDI 자식 창에 표시 되는 문서의 이름을 반환 합니다.|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|MDI 자식 창 아이콘을 검색 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|MDI 자식 창에 대 한 텍스트를 검색 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::GetPane](#getpane)|지정 된 컨트롤 id 창을 찾습니다.|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|탭 된 문서로 변환 하는 포함 된 도킹 창에 대 한 포인터를 반환 합니다.|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|반환은 프록시 창 Windows 7 작업 표시줄 탭에 실제로 등록을 탭 합니다.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Windows 7 작업 표시줄 탭 축소판 그림에 표시 될 자식 창 (일반적으로 뷰 또는 분할자 창)을 가져와야 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분을 선택 해야 할 때 프레임 워크에서 호출 됩니다.|  
|`CMDIChildWndEx::GetThisClass`|에 대 한 포인터를 가져올 수 프레임 워크에서 호출 된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|도구 모음 단추에 대 한 도구 설명을 검색 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::InsertPane](#insertpane)|지정 된 창 고 도킹 관리자에 등록합니다.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|MDI 자식으로 나타낸 아이콘 비트맵을 무효화합니다.|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|지정된 된 지점 근처 도킹 사이트 인지 확인 합니다.|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|반환 `TRUE` 문서가 있는 경우 자식 창에 표시 되는 읽기 전용입니다. 그렇지 않으면 `FALSE`를 반환합니다.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|MDI 자식 Windows 7 작업 표시줄 탭이 포함 된 성공적으로 등록 된 경우 TRUE를 반환 합니다.|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|반환 `TRUE` MDI 자식 창을 도킹 창을 포함 하는 경우. 그렇지 않으면 `FALSE`를 반환합니다.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|MDI 자식 Windows 7 작업 표시줄 탭에 표시할 수 있는지 여부를 알려 줍니다.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분의 자동 선택을 사용 되는지 여부를 알려 줍니다.|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Windows 7 작업 표시줄 탭이 포함 된 탭 (MDI 자식)를 등록 하는 경우 SetTaskbarTabProperties 메서드에 프레임 워크에 의해 전달 되는 플래그의 조합입니다. 기본 파악 하는 STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE 합니다.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|MDI 자식의 실시간 미리 보기에 대 한 비트맵을 가져와야 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|아이콘 축소판 그림의 MDI 자식에 대 한 비트맵을 가져와야 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|작업 표시줄 탭 미리 보기에서 닫기 단추를 누를 때 프레임 워크에서 호출...|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|입력 또는 인쇄 미리 보기 모드를 종료 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|작업 표시줄 탭 축소판 그림 WM_ACTIVATE 메시지를 처리 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|작업 표시줄 탭 축소판 그림 WM_MOUSEACTIVATE 메시지를 처리 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|Windows 7 작업 표시줄 탭 축소판 미리 보기의 MDI 자식에 대 한 비트맵을 스트레치 하는 데 필요한 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|프레임 제목 업데이트 하기 위해 프레임 워크에서 호출 됩니다. (`CMDIChildWnd::OnUpdateFrameTitle`를 재정의합니다.)|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|지정된 된 점을 포함 하는 창을 반환 합니다.|  
|`CMDIChildWndEx::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) Windows 함수로 디스패치되기 전에 [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|창 레이아웃을 다시 계산 합니다.|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Windows 7 작업 표시줄 탭 MDI 자식에 등록합니다.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 도킹 관리자에서 제거 합니다.|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|해당 Windows 7 작업 표시줄 탭을 활성화합니다.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Windows 7 작업 표시줄 탭에 지정 된 창 하기 전에 MDI 자식을 삽입합니다.|  
|[Cmdichildwndex:: Settaskbartabproperties](#settaskbartabproperties)|Windows 7 작업 표시줄 탭에 대한 속성을 설정합니다.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분을 선택 하 여 클리핑 사각형을 설정 하기 위해 프레임 워크에서 내부적으로 호출 합니다.|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Windows 7 작업 표시줄 탭에서 MDI 자식을 제거합니다.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Windows 7 작업 표시줄 탭 아이콘을 업데이트합니다.|  
  
## <a name="remarks"></a>설명  
 를 사용 하려면 확장 된 도킹 기능의 MDI 응용 프로그램의에서 응용 프로그램의 MDI 자식 창 클래스를 파생 `CMDIChildWndEx` 대신 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서 클래스를 파생 `CMDIChildWndEx`합니다. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxMDIChildWndEx.h  
  
##  <a name="addpane"></a>  CMDIChildWndEx::AddPane  
 창을 추가합니다.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pControlBar*  
 창에 대 한 포인터입니다.  
  
 [in] *bTail*  
 `TRUE` 고 도킹 관리자;에 대 한 창에서 창의 목록 끝에 추가 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창 고 도킹 관리자;에 성공적으로 등록 된 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="addtabbedpane"></a>  CMDIChildWndEx::AddTabbedPane  
 탭된 창에 추가합니다.  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pControlBar*  
 창에 대 한 포인터입니다.  
  
##  <a name="adjustdockinglayout"></a>  CMDIChildWndEx::AdjustDockingLayout  
 도킹 레이아웃을 조정합니다.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *hdwp*  
 지연 된 창 위치 구조에 대 한 핸들입니다.  
  
##  <a name="canshowonmditabs"></a>  CMDIChildWndEx::CanShowOnMDITabs  

  
```  
virtual BOOL CanShowOnMDITabs();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="canshowonwindowslist"></a>  CMDIChildWndEx::CanShowOnWindowsList  
 MDI 자식 창 이름에 표시할 수 있는지 여부를 지정 된 [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자.  
  
```  
virtual BOOL CanShowOnWindowsList();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창에 표시 될 수는 **Windows** 대화 상자, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 파생된 클래스에서이 메서드를 재정의 하 고 반환 `FALSE` 창에 표시 되지 않아야 하는 경우는 **Windows** 대화 상자. 이 함수를 호출 `CMFCWindowsManagerDialog`합니다.  
  
##  <a name="dockpane"></a>  CMDIChildWndEx::DockPane  
 창을 도킹합니다.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pBar*  
 창에 대 한 포인터입니다.  
  
 [in] *nDockBarID*  
 ID는 창입니다.  
  
 [in] *lpRect*  
 사각형에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 *lpRect* 매개 변수는 사용 되지 않습니다.  
  
##  <a name="dockpaneleftof"></a>  CMDIChildWndEx::DockPaneLeftOf  
 창을 다른 창의 왼쪽에 도킹합니다.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>매개 변수  
 *pBar*  
 도킹 될 수 있는 창에 대 한 포인터입니다.  
  
 *pLeftOf*  
 참조 지점으로 사용 되는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 성공할 경우 `FALSE` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 지정 된 창 *pBar* 로 지정 된 창 왼쪽에 도킹 *pLeftOf*합니다.  
  
 미리 정의 된 순서로 여러 창을 도킹 하려면이 메서드를 호출 합니다.  
  
##  <a name="enableautohidepanes"></a>  CMDIChildWndEx::EnableAutoHidePanes  
 수 있도록 자동 숨기기 모드를 창에 대 한 지정 된 창 측면에 도킹 된 경우.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *dwDockStyle*  
 사용 하도록 설정 된 주 프레임 창의 측면을 지정 합니다. 플래그 중 하나 이상을 사용 합니다.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면; 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="enabledocking"></a>  CMDIChildWndEx::EnableDocking  
 주 프레임에 사용 하면 자식 창의 도킹 합니다.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *dwDockStyle*  
 사용할 수 있도록 도킹 맞춤을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 주 프레임에 대 한 도킹 맞춤을 사용 하도록 설정 하려면이 메서드를 호출 합니다. CBRS_ALIGN_ 플래그의 조합에 전달할 수 있습니다 (자세한 내용은 참조 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
##  <a name="getdockingmanager"></a>  CMDIChildWndEx::GetDockingManager  

  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdocumentname"></a>  CMDIChildWndEx::GetDocumentName  
 MDI 자식 창에 표시 되는 문서의 이름을 반환 합니다.  
  
```  
virtual LPCTSTR GetDocumentName(CObject** pObj);
```  
  
### <a name="return-value"></a>반환 값  
 문서의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 문서가 있는 MDI 자식 창이 표시 됩니다. 일반적으로 창에서 로드 되거나 파일에 저장 되는 데이터에 표시 됩니다. 따라서 문서 이름이 파일의 이름입니다. 기본 구현은 `GetDocumentName` 에서 가져온 문자열을 반환 `CDocument::GetPathName`합니다.  
  
 파일에서 로드 되지 않는 문서 창에 표시 됩니다, 파생된 클래스에서이 메서드를 재정의 하 고 고유한 문서 식별자를 반환 합니다.  
  
 `GetDocumentName` 모든 열린된 문서 상태를 저장할 때 프레임 워크에서 호출 됩니다. 반환 된 문자열의 레지스트리에 기록 됩니다.  
  
 문서 이름은 레지스트리에서 읽을 이며에 전달 되는 프레임 워크는 상태를 복원할 때 나중에 [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)합니다. 이 메서드를 재정의 한 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-파생 클래스 또는이 이름을 가진 문서를 열 만들고이 이름을 가진 파일을 읽어올 합니다. 문서 파일을 기반으로 하지 않는 경우에 자체 문서 식별자에 따라 문서를 만듭니다. 저장 하 고 문서를 복원 하려는 경우에 위에 제시한 작업을 수행 해야 합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 `GetDocumentName` 메서드를 사용하는 방법을 보여 줍니다. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>  CMDIChildWndEx::GetFrameIcon  
 MDI 자식 창 아이콘을 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>반환 값  
 창 아이콘에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 MDI 자식 프레임 창에 포함 된 MDI 탭에 표시할 아이콘 결정 하기 위해 프레임 워크에서 호출 됩니다.  
  
 기본적으로이 메서드는 창 아이콘을 반환합니다. 재정의 `GetFrameIcon` 에 `CMDIChildWndEx`-이 동작을 사용자 지정 하려면 클래스를 파생 합니다.  
  
##  <a name="getframetext"></a>  CMDIChildWndEx::GetFrameText  
 MDI 자식 창에 대 한 텍스트를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프레임 창 텍스트를 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 MDI 자식 프레임 창에 포함 된 MDI 탭에 표시할 텍스트를 결정 하는 프레임 워크에서 호출 됩니다.  
  
 기본적으로이 메서드는 창 텍스트를 반환합니다. 재정의 `GetFrameText` 에 `CMDIChildWndEx`-이 동작을 사용자 지정 하려면 클래스를 파생 합니다.  
  
##  <a name="getpane"></a>  CMDIChildWndEx::GetPane  
 지정 된 컨트롤 id 창을 찾습니다.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nID*  
 찾을 창의 컨트롤 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 창에 대 한 포인터를 하는 경우, 그렇지 않으면 찾을 `NULL`합니다.  
  
##  <a name="getrelatedtabgroup"></a>  CMDIChildWndEx::GetRelatedTabGroup  

  
```  
CMFCTabCtrl* GetRelatedTabGroup();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettabbedpane"></a>  CMDIChildWndEx::GetTabbedPane  
 탭 문서 MDI 그룹의 일부인 도킹 창에 대 한 포인터를 반환 합니다.  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 MDI 그룹의 일부인 도킹 창에 대 한 포인터는 문서를 탭 합니다.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>  CMDIChildWndEx::GetToolbarButtonToolTipText  
 도구 모음 단추에 대 한 도구 설명을 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도구 설명 표시 되었습니다. 기본 구현은 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 도구 모음 단추에 대 한 사용자 지정 도구 설명을 표시 하려면이 메서드를 재정의 합니다.  
  
##  <a name="insertpane"></a>  CMDIChildWndEx::InsertPane  
 지정 된 창 고 도킹 관리자에 등록합니다.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pControlBar*  
 삽입할 창에 대 한 포인터입니다.  
  
 [in] *pTarget*  
 인접 한 창에 대 한 포인터입니다.  
  
 [in] *후에는*  
 경우 `TRUE`, *pControlBar* 뒤에 삽입 되어 *pTarget*합니다. 경우 `FALSE`, *pControlBar* 앞에 삽입 된 *pTarget*합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 `FALSE` 그렇지 않은 경우.  
  
##  <a name="ispointneardocksite"></a>  CMDIChildWndEx::IsPointNearDockSite  
 지정된 된 지점 근처 도킹 사이트 인지 확인 합니다.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 지정 된 지점입니다.  
  
 [in] *dwBarAlignment*  
 중요 한 점은 가까운 가장자리를 지정 합니다. 가능한 값은 `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, 및 `CBRS_ALIGN_BOTTOM`  
  
 [in] *bOuterEdge*  
 `TRUE` 도킹 사이트;의 외부 테두리 주변 포인터가 있는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 사이트; 근처 포인터가 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 점은 도킹 사이트 근처의 민감도 고 도킹 관리자에 설정 내에 없을 때입니다. 기본 민감도 15 픽셀입니다.  
  
##  <a name="isreadonly"></a>  CMDIChildWndEx::IsReadOnly  
 자식 창에 표시 되는 문서 읽기 전용인 지 여부를 지정 합니다.  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 문서가 읽기 전용입니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 사용 되지 않도록 읽기 전용으로 문서를 저장 합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 재정의 `IsReadOnly` 메서드. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>  CMDIChildWndEx::IsTabbedPane  
 MDI 자식 창을 도킹 창에 포함 되는지 여부를 지정 합니다.  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` MDI 자식 창을 포함 된 창을 탭 된 문서로; 변환 된 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="onmoveminiframe"></a>  CMDIChildWndEx::OnMoveMiniFrame  
 미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pFrame*  
 미니 프레임 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면, 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="onsetpreviewmode"></a>  CMDIChildWndEx::OnSetPreviewMode  
 입력 또는 인쇄 미리 보기 모드를 종료 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bPreview*  
 경우 `TRUE`, 인쇄 미리 보기 모드로 전환 합니다. 경우 `FALSE`, 인쇄 미리 보기 모드를 종료 합니다.  
  
 [in] *pState*  
 인쇄 미리 보기 상태 구조체에 대 한 포인터입니다.  
  
##  <a name="onupdateframetitle"></a>  CMDIChildWndEx::OnUpdateFrameTitle  
 프레임 제목 업데이트 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bAddToTitle*  
 경우 `TRUE`, 제목에 문서 이름을 추가 합니다.  
  
##  <a name="panefrompoint"></a>  CMDIChildWndEx::PaneFromPoint  
 지정된 된 점을 포함 하는 창을 반환 합니다.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 화면 좌표를 확인 하는 지점을 지정 합니다.  
  
 [in] *nSensitivity*  
 검색 영역이 양만큼 늘립니다. 창이 지정된 된 점을 증가 된 영역에 해당 하는 경우 검색 조건을 충족 합니다.  
  
 [in] *bExactBar*  
 `TRUE` 무시 하려면는 *nSensitivity* 매개 변수, 그렇지 않으면 `FALSE`합니다.  
  
 [in] *pRTCBarType*  
 그렇지 않으면 `NULL`, 메서드가 지정 된 형식의 창만 검색 합니다.  
  
 [in] *dwAlignment*  
 창이 지정된 된 지점에서 발견 되 면이 매개 변수에 지정된 된 지점에 가장 가까운 했던 창 옆쪽에 포함 합니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CBasePane`-파생 된 지정된 된 점을 포함 하는 개체 또는 `NULL` 없는 창을 찾을 수 없으면입니다.  
  
### <a name="remarks"></a>설명  
 런타임 클래스 및 표시 여부와 같은 지정 된 조건에 따라 지정된 된 점이 있는 창에 포함 되는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
 함수 반환 하 고 창을 발견 하는 경우 *dwAlignment* 맞춤을 지정 된 위치를 포함 합니다. 예를 들어, 지점 창의 위쪽에 가장 가까운 되었으면 *dwAlignment* 로 설정 된 `CBRS_ALIGN_TOP`합니다.  
  
##  <a name="recalclayout"></a>  CMDIChildWndEx::RecalcLayout  
 창 레이아웃을 다시 계산 합니다.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bNotify*  
 경우 `TRUE`, 창에 대 한 활성 내부 항목 레이아웃 변경 알림을 수신 합니다.  
  
##  <a name="removepanefromdockmanager"></a>  CMDIChildWndEx::RemovePaneFromDockManager  
 창을 도킹 관리자에서 제거 합니다.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pControlBar*  
 제거 하 고 창에 대 한 포인터입니다.  
  
 [in] *bDestroy*  
 경우 `TRUE`, 제거 창 소멸 됩니다.  
  
 [in] *bAdjustLayout*  
 경우 `TRUE`를 즉시 도킹 레이아웃을 조정 합니다.  
  
 [in] *bAutoHide*  
 경우 `TRUE`, 도킹 레이아웃에는 자동 숨기기 막대의 목록 관련이 있습니다. 경우 `FALSE`, 도킹 레이아웃에는 일반 창의 목록 관련이 있습니다.  
  
 [in] *pBarReplacement*  
 제거 창을 대체 하는 창에 대 한 포인터입니다.  
  
##  <a name="setrelatedtabgroup"></a>  CMDIChildWndEx::SetRelatedTabGroup  

  
```  
void SetRelatedTabGroup(CMFCTabCtrl* p);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *p*  
  
### <a name="remarks"></a>설명  
  
##  <a name="showpane"></a>  CMDIChildWndEx::ShowPane  

  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pBar*  
 [in] *bShow*  
 [in] *bDelay*  
 [in] *bActivate*  
  
### <a name="remarks"></a>설명  
  
##  <a name="updatetaskbartabicon"></a>  CMDIChildWndEx::UpdateTaskbarTabIcon  
 Windows 7 작업 표시줄 탭 아이콘을 업데이트합니다.  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 *hIcon*  
 Windows 7 작업 표시줄 탭에 표시할 아이콘에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="unregistertaskbartab"></a>  CMDIChildWndEx::UnregisterTaskbarTab  
 Windows 7 작업 표시줄 탭에서 MDI 자식을 제거합니다.  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bCheckRegisteredMDIChildCount*  
 이 함수를 MDI 자식 폼 MDI 탭이 포함 된 등록의 수를 확인 해야 하는지 여부를 지정 합니다. 이 숫자가 0 이면이 함수는 응용 프로그램의 작업 표시줄의 미리 보기에서 클리핑 사각형을 제거 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="settaskbarthumbnailcliprect"></a>  CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분을 선택 하 여 클리핑 사각형을 설정 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>매개 변수  
 *rect*  
 새 클리핑 사각형을 지정합니다. 사각형이 비어 있거나 null 인 경우 클리핑 제거 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="settaskbartabproperties"></a>  Cmdichildwndex:: Settaskbartabproperties  
 Windows 7 작업 표시줄 탭에 대한 속성을 설정합니다.  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwFlags*  
 STPFLAG 값의 조합입니다. 자세한 내용은 참조 [ITaskbarList4::SetTabProperties](http://msdn.microsoft.com/library/dd562049\(vs.85\).aspx)합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="settaskbartaborder"></a>  CMDIChildWndEx::SetTaskbarTabOrder  
 Windows 7 작업 표시줄 탭에 지정된 된 창 하기 전에 MDI 자식을 삽입합니다.  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndBefore*  
 MDI 자식 창에 있는 축소판 그림이 왼쪽에 삽입 되는 포인터입니다. 이 창을 통해 이미 등록 되어 있어야 `RegisterTaskbarTab`합니다. 이 값이 `NULL`, 새 미리 보기는 목록 끝에 추가 됩니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="settaskbartabactive"></a>  CMDIChildWndEx::SetTaskbarTabActive  
 해당 Windows 7 작업 표시줄 탭을 활성화합니다.  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="registertaskbartab"></a>  CMDIChildWndEx::RegisterTaskbarTab  
 Windows 7 작업 표시줄 탭 MDI 자식에 등록합니다.  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndBefore*  
 MDI 자식 창에 있는 축소판 그림이 왼쪽에 삽입 되는 포인터입니다. 이 창을 통해 이미 등록 되어 있어야 `RegisterTaskbarTab`합니다. 이 값이 `NULL`, 새 미리 보기는 목록 끝에 추가 됩니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="ontaskbartabthumbnailstretch"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 Windows 7 작업 표시줄 탭 축소판 미리 보기의 MDI 자식에 대 한 비트맵을 스트레치 하는 데 필요한 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 *hBmpDst*  
 대상 비트맵에 대 한 핸들입니다.  
  
 *rectDst*  
 대상 사각형을 지정합니다.  
  
 *hBmpSrc*  
 소스 비트맵에 대 한 핸들입니다.  
  
 *rectSrc*  
 소스 사각형을 지정합니다.  
  
### <a name="remarks"></a>설명  
 Requirementher 또는 그 그 그 그 그 그 그 **:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 작업 표시줄 탭 축소판 그림 WM_MOUSEACTIVATE 메시지를 처리할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDesktopWnd*  
 활성화 되 고 창의 최상위 부모 창에 대 한 포인터를 지정 합니다. 포인터는 임시적 이며 저장 되어야 합니다.  
  
 *nHitTest*  
 적중 테스트 지역 번호를 지정합니다. 적중 횟수 테스트에는 커서의 위치를 결정 하는 테스트가입니다.  
  
 *message*  
 마우스 메시지 번호를 지정합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 관련된 MDI 자식 프레임을 활성화합니다.  
  
##  <a name="ontaskbartabthumbnailactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 작업 표시줄 탭 축소판 그림 WM_ACTIVATE 메시지를 처리할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>매개 변수  
 *nState*  
 지정 여부는 `CWnd` 활성화 또는 비활성화 되는 합니다.  
  
 *pWndOther*  
 에 대 한 포인터는 `CWnd` 활성화 되거나 비활성화 되 고 있습니다. 포인터 수 `NULL`, 임시 수도 있습니다.  
  
 *bMinimized*  
 최소화 된 상태를 지정 된 `CWnd` 활성화 되거나 비활성화 되 고 있습니다. 값이 `TRUE` 창을 최소화 됨을 나타냅니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 관련된 MDI 자식 프레임을 활성화합니다.  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>  CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 사용자가 작업 표시줄 탭 축소판 그림의 닫기 단추를 누를 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="ongeticonicthumbnail"></a>  CMDIChildWndEx::OnGetIconicThumbnail  
 MDI 자식의 아이콘 미리 보기에 대 한 비트맵을 가져와야 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 *nWidth*  
 필요한 비트맵의 너비를 지정합니다.  
  
 *nHeight*  
 필요한 비트맵의 높이 지정합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="ongeticoniclivepreviewbitmap"></a>  CMDIChildWndEx::OnGetIconicLivePreviewBitmap  
 MDI 자식의 실시간 미리 보기에 대 한 비트맵을 가져와야 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>매개 변수  
 *bIsMDIChildActive*  
 이 매개 변수는 `TRUE` 비트맵 MDI 자식에 대 한 요청 되는 현재 활성화 되어 있고 주 창 하지 최소화 됩니다. 기본이 경우 처리는 주 창의 스냅숏을 만듭니다.  
  
 *ptLocation*  
 Main (최상위 수준)에서 비트맵의 위치를 지정 합니다. 창 클라이언트 좌표입니다. 이 지점 호출 수신자에 의해 제공 되어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 처리 되 면 핸들을 반환 유효한 32bpp 비트맵, 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 파생된 클래스에서이 메서드를 재정의 하 고 MDI 자식의 실시간 미리 보기에 대 한 유효한 32bpp 비트맵을 반환 합니다. 이 메서드는 MDI 자식 Windows 7 작업 표시줄 탭에 표시 될 때만 호출 됩니다. 반환 하는 경우 `NULL`, MFC 기본 처리기를 호출 하 고 사용 하 여 비트맵을 가져옵니다 `PrintClient` 또는 `PrintWindow`합니다.  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>  CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 플래그의 조합으로 프레임 워크에 의해 전달 되는 `SetTaskbarTabProperties` 메서드, Windows 7 작업 표시줄 탭이 포함 된 탭 (MDI 자식)를 등록 하는 경우.  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>설명  
 기본 파악 하는 STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE 합니다.  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>  CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분의 자동 선택을 사용 되는지 여부를 알려 줍니다.  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 표시 하려면 창의 클라이언트 영역의 일부를 자동으로 선택 활성화 되지 않았으면 경우 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="istaskbartabssupportenabled"></a>  CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 MDI 자식 Windows 7 작업 표시줄 탭에 표시할 수 있는지 여부를 알려 줍니다.  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` Windows 7 작업 표시줄 탭;에 MDI 자식 표시할 수 있는 경우 `FALSE` 경우 MDI 자식 Windows 7 작업 표시줄 탭에 나타날 수 없습니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="isregisteredwithtaskbartabs"></a>  CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 반환 `TRUE` 경우 Windows 7 작업 표시줄 탭이 포함 된 MDI 자식 등록 되었습니다.  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` MDI 자식 Windows 7 작업 표시줄 탭;에 등록 되어 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="invalidateiconicbitmaps"></a>  CMDIChildWndEx::InvalidateIconicBitmaps  
 MDI 자식에 대 한 아이콘 비트맵 표현이 무효화합니다.  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `FALSE` Windows 7 작업 표시줄 지원이 비활성화 되어 있거나 MDI 자식 등록 되지 않은 Windows 7 작업 표시줄 탭이 있습니다; 그렇지 않으면 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>설명  
 라이브 콘텐츠 또는 MDI 자식의 크기 변경 될 때 호출 되어야 합니다.  
  
##  <a name="gettaskbarthumbnailcliprect"></a>  CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분을 선택 해야 할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows 좌표에서 사각형입니다. 이 사각형은 최상위 수준 프레임의 클라이언트 영역에 매핑됩니다. 사각형을 클리핑 사각형을 지우려면 비어 있어야 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettaskbarpreviewwnd"></a>  CMDIChildWndEx::GetTaskbarPreviewWnd  
 Windows 7 작업 표시줄 탭 미리 보기에 표시할 자식 창 (일반적으로 뷰 또는 분할자 창)을 가져와야 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 유효한 포인터를 반환 해야는 `CWnd` 이 MDI 자식으로 관련 된 개체, Windows 7 작업 표시줄 탭에 있는 미리 보기 표시 되어야 합니다. 기본 구현은 반환이 MDI 자식으로 AFX_IDW_PANE_FIRST 컨트롤 ID의 자식 창 (일반적으로 `CView`-파생 클래스).  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettabproxywnd"></a>  CMDIChildWndEx::GetTabProxyWnd  
 등록 된 Windows 7 작업 표시줄 탭 탭 프록시 창을 반환 합니다.  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CMDITabProxyWnd` 개체에 등록 된 Windows 7 작업 표시줄 탭입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>  CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 작업 표시줄에서 해당 창 축소판 그림으로 표시 하려면 창의 클라이언트 영역 부분의 자동 선택을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bEnable*  
 사용 여부를 지정 ( `TRUE`)를 사용 하지 않도록 설정 하거나 ( `FALSE`) 표시 하려면 창의 클라이언트 영역의 일부를 자동으로 선택 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="canshowontaskbartabs"></a>  CMDIChildWndEx::CanShowOnTaskBarTabs  
 Windows 7 작업 표시줄 탭에 MDI 자식이 표시 될 수 있는지 여부 프레임 워크에 지시 합니다.  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 이면 Windows 7 작업 표시줄의 미리 보기에 MDI 자식 콘텐츠를 표시할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 파생된 클래스에서이 메서드를 재정의 하 고 반환 `FALSE` Windows 7 작업 표시줄 탭에 MDI 자식이 모양을 비활성화할 수 있습니다.  
  
##  <a name="activatetoplevelframe"></a>  CMDIChildWndEx::ActivateTopLevelFrame  
 응용 프로그램에서 작업 표시줄 탭에 활성화 될 때 최상위 수준 프레임을 활성화 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void ActivateTopLevelFrame();
```  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)
