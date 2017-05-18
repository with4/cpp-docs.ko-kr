---
title: "CFrameWndEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx::ActiveItemRecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::AddPane
- AFXFRAMEWNDEX/CFrameWndEx::AdjustDockingLayout
- AFXFRAMEWNDEX/CFrameWndEx::DelayUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::DockPane
- AFXFRAMEWNDEX/CFrameWndEx::DockPaneLeftOf
- AFXFRAMEWNDEX/CFrameWndEx::EnableAutoHidePanes
- AFXFRAMEWNDEX/CFrameWndEx::EnableDocking
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMainMenu
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMode
- AFXFRAMEWNDEX/CFrameWndEx::EnableLoadDockState
- AFXFRAMEWNDEX/CFrameWndEx::EnablePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::GetActivePopup
- AFXFRAMEWNDEX/CFrameWndEx::GetDefaultResId
- AFXFRAMEWNDEX/CFrameWndEx::GetDockingManager
- AFXFRAMEWNDEX/CFrameWndEx::GetMenuBar
- AFXFRAMEWNDEX/CFrameWndEx::GetPane
- AFXFRAMEWNDEX/CFrameWndEx::GetRibbonBar
- AFXFRAMEWNDEX/CFrameWndEx::GetTearOffBars
- AFXFRAMEWNDEX/CFrameWndEx::GetToolbarButtonToolTipText
- AFXFRAMEWNDEX/CFrameWndEx::InsertPane
- AFXFRAMEWNDEX/CFrameWndEx::IsFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::IsMenuBarAvailable
- AFXFRAMEWNDEX/CFrameWndEx::IsPointNearDockSite
- AFXFRAMEWNDEX/CFrameWndEx::IsPrintPreview
- AFXFRAMEWNDEX/CFrameWndEx::LoadFrame
- AFXFRAMEWNDEX/CFrameWndEx::NegotiateBorderSpace
- AFXFRAMEWNDEX/CFrameWndEx::OnActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnActivateApp
- AFXFRAMEWNDEX/CFrameWndEx::OnChangeVisualManager
- AFXFRAMEWNDEX/CFrameWndEx::OnClose
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseDockingPane
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnClosePopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnCmdMsg
- AFXFRAMEWNDEX/CFrameWndEx::OnContextHelp
- AFXFRAMEWNDEX/CFrameWndEx::OnCreate
- AFXFRAMEWNDEX/CFrameWndEx::OnDestroy
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuImage
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuLogo
- AFXFRAMEWNDEX/CFrameWndEx::OnDWMCompositionChanged
- AFXFRAMEWNDEX/CFrameWndEx::OnExitSizeMove
- AFXFRAMEWNDEX/CFrameWndEx::OnGetMinMaxInfo
- AFXFRAMEWNDEX/CFrameWndEx::OnIdleUpdateCmdUI
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonDown
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonUp
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuButtonToolHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuChar
- AFXFRAMEWNDEX/CFrameWndEx::OnMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnMoveMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnNcActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnNcCalcSize
- AFXFRAMEWNDEX/CFrameWndEx::OnNcHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnNcMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnNcPaint
- AFXFRAMEWNDEX/CFrameWndEx::OnPaneCheck
- AFXFRAMEWNDEX/CFrameWndEx::OnPostPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnPowerBroadcast
- AFXFRAMEWNDEX/CFrameWndEx::OnSetMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSetPreviewMode
- AFXFRAMEWNDEX/CFrameWndEx::OnSetText
- AFXFRAMEWNDEX/CFrameWndEx::OnShowCustomizePane
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPanes
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSize
- AFXFRAMEWNDEX/CFrameWndEx::OnSizing
- AFXFRAMEWNDEX/CFrameWndEx::OnSysColorChange
- AFXFRAMEWNDEX/CFrameWndEx::OnTearOffMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarContextMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarCreateNew
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarDelete
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameTitle
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdatePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnWindowPosChanged
- AFXFRAMEWNDEX/CFrameWndEx::PaneFromPoint
- AFXFRAMEWNDEX/CFrameWndEx::PreTranslateMessage
- AFXFRAMEWNDEX/CFrameWndEx::RecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::RemovePaneFromDockManager
- AFXFRAMEWNDEX/CFrameWndEx::SetDockState
- AFXFRAMEWNDEX/CFrameWndEx::SetPrintPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::SetupToolbarMenu
- AFXFRAMEWNDEX/CFrameWndEx::ShowFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::ShowPane
- AFXFRAMEWNDEX/CFrameWndEx::UpdateCaption
- AFXFRAMEWNDEX/CFrameWndEx::WinHelp
dev_langs:
- C++
helpviewer_keywords:
- CFrameWndEx class
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b2106c3067a0164395eddab0e8b156728697d5bb
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cframewndex-class"></a>CFrameWndEx 클래스
겹쳐진 Windows SDI(단일 문서 인터페이스) 또는 팝업 프레임 창의 기능을 구현하고 창 관리를 위한 멤버를 제공합니다. 확장 된 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|레이아웃 OLE 클라이언트 항목 및 프레임의 클라이언트 영역을 조정합니다.|  
|`CFrameWndEx::AddDockSite`|이 메서드는 사용 되지 않습니다.|  
|[CFrameWndEx::AddPane](#addpane)|관리자는 도킹 컨트롤 막대에 등록합니다.|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|프레임 창에 도킹 된 모든 창 레이아웃을 다시 계산 합니다.|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|프레임 메뉴를 설정 하 고 명령 처리 유휴 상태일 때 업데이트 합니다.|  
|[CFrameWndEx::DockPane](#dockpane)|지정 된 창 프레임 창에 도킹합니다.|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|주 프레임 창의 지정 된 측면에 도킹 된 될 때 창에 대해 자동 숨김 모드를 지원 합니다.|  
|[CFrameWndEx::EnableDocking](#enabledocking)|프레임 창에 속하는 창을 도킹 수 있습니다.|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|표시 하거나 전체 화면 모드에서 주 메뉴를 숨깁니다.|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|프레임 창에 대 한 전체 화면 모드를 활성화 합니다.|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|도킹 상태를 로드 하는 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|창 메뉴의 자동 처리를 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|현재 표시 된 팝업 메뉴에 대 한 포인터를 반환합니다.|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|프레임 워크는 프레임 창 로드 될 때 지정 된 리소스 ID를 반환 합니다.|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|검색 된 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 프레임 창에 대 한 개체입니다.|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|프레임 창에 연결된 메뉴 모음 개체에 대한 포인터를 반환합니다.|  
|[CFrameWndEx::GetPane](#getpane)|지정 된 ID를 가집니다. 창에 대 한 포인터를 반환 합니다.|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|프레임에 대해 리본 표시줄 컨트롤을 검색합니다.|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|분리 상태에 있는 창 개체의 목록을 반환합니다.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|응용 프로그램 도구 모음 단추에 대 한 도구 설명을 표시 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::InsertPane](#insertpane)|창을 도킹 관리자에 등록합니다.|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|프레임 창을 전체 화면 모드 인지 여부를 결정 합니다.|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|메뉴 모음 개체에 대 한 포인터 유효한 지 여부를 결정 합니다.|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|지점 맞춤 영역에 있는지 여부를 나타냅니다.|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|프레임 창 인쇄 미리 보기 모드 인지 여부를 나타냅니다.|  
|[CFrameWndEx::LoadFrame](#loadframe)|이 메서드는 프레임 창을 만들고 해당 리소스를 로드 하는 생성 후 호출 됩니다.|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|구현 OLE 클라이언트 테두리 협상 합니다.|  
|[CFrameWndEx::OnActivate](#onactivate)|프레임 워크는 사용자 입력 하거나 프레임에서 전환 되 면이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|응용 프로그램 선택 되거나 선택이 취소 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|프레임에 대 한 변경 비주얼 관리자에 대 한 변경 해야 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnClose](#onclose)|프레임 워크는 프레임을 닫아도이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 도킹 창에 단추입니다.|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 부동 미니 프레임 창에 단추입니다.|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|디스패치 메시지 명령합니다.|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|프레임 워크 호출 컨텍스트를 표시 하려면 관련 도움말.|  
|[CFrameWndEx::OnCreate](#oncreate)|프레임을 만든 후에 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnDestroy](#ondestroy)|프레임 소멸 되 면 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|응용 프로그램 메뉴 항목과 연결 된 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|프레임 워크 호출 때는 `CMFCPopupMenu` 프로세스 개체를 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지입니다.|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|데스크톱 창 관리자 (DWM) 컴퍼지션 활성화 또는 비활성화 되었으므로 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|프레임 이동 하거나 크기 조정 중지 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|프레임 창 차원 제한을 설정 하는 크기가 조정 될 때 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|명령 처리 유휴 상태일 때 프레임 디스플레이 업데이트 하려면 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|프레임 워크는 사용자가 왼쪽된 마우스 단추를 누르면이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|마우스 왼쪽된 단추를 놓을 때이 메서드를 호출 하는 프레임 워크입니다.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|프레임 워크 호출 때는 `CMFCToolBarButton` 프로세스 개체를 `WM_NCHITTEST` 메시지입니다.|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|메뉴가 표시 되 고 사용자 명령에 해당 하지 않는 키를 누를 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|프레임 워크는 포인터를 이동 하면이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|창 창 이동 하면 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|프레임의 클라이언트 이외의 영역에서는 활성 상태의 변화를 나타내기 위해 그려야 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|클라이언트 영역 위치와 크기를 계산 해야 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|포인터를 이동할 때 또는 마우스 단추를 누르거나 놓을 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|비클라이언트 영역에서 포인터를 이동 하면 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|비클라이언트 영역을 칠할 해야 하는 경우 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|창의 표시 유형을 제어 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|사용자가 인쇄 미리 보기 모드를 변경 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|전원 관리 이벤트가 발생할 때 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|프레임 창 메뉴를 대체 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|프레임에 대 한 인쇄 미리 보기 모드를 설정 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnSetText](#onsettext)|창의 텍스트를 설정 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|빠른 사용자 지정 하는 경우에 프레임 워크에서 호출 창이 활성화 됩니다.|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|표시 하거나 숨기려면 창 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|팝업 메뉴를 사용 하는 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::OnSize](#onsize)|프레임 워크는 프레임의 크기 변경 된 후이 메서드를 호출합니다.|  
|[CFrameWndEx::OnSizing](#onsizing)|프레임 워크는 사용자는 프레임의 크기를 조정 하는 경우이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|시스템 색이 변경 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|표시줄이 있는 분리 메뉴를 사용 하는 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|도구 모음 상황에 맞는 메뉴를 작성 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|프레임 워크에는 새 도구 모음을 만들도록이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|도구 모음에서 삭제 되는 프레임 워크에서 호출 합니다.|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|프레임 메뉴를 설정 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|프레임 워크는 프레임 창의 제목 표시줄을 업데이트 하려면이 메서드를 호출 합니다.|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|창 메뉴를 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|프레임 크기, 위치, 또는 z 창 관리 방법에 대 한 호출으로 인해 변경 된 경우에 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|지정 된 위치를 포함 하는 도킹 창을 반환 합니다.|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|디스패치 되기 전에 특정 창 메시지를 처리 합니다.|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|프레임 및 해당 자식 창의 레이아웃을 조정합니다.|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 등록을 취소 하 고 도킹 관리자의 내부 목록에서 제거 합니다.|  
|[CFrameWndEx::SetDockState](#setdockstate)|레지스트리에 저장 된 도킹 상태를 도킹 레이아웃을 복원 합니다.|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|인쇄 미리 보기 프레임 창을 설정입니다.|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|도구 모음 메뉴에 사용자 지정 명령을 삽입 합니다.|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|주 프레임 전체 화면 모드와 일반 모드 사이 전환합니다.|  
|[CFrameWndEx::ShowPane](#showpane)|표시 하거나 지정한 창을 숨깁니다.|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|창 프레임 캡션을 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[CFrameWndEx::WinHelp](#winhelp)|중 하나를 호출 하는 `WinHelp` 응용 프로그램이 나 컨텍스트 관련 도움말입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 클래스에서 상속 하는 방법을 `CFrameWndEx` 클래스입니다. 이 예제는 서브 클래스에 메서드 서명 및 재정의 하는 방법을 보여 줍니다.는 `OnShowPopupMenu` 메서드. 이 코드 조각은의 일부인는 [워드 패드 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_WordPad #&3;](../../mfc/reference/codesnippet/cpp/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad #&4;](../../mfc/reference/codesnippet/cpp/cframewndex-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxframewndex.h  
  
##  <a name="activeitemrecalclayout"></a>CFrameWndEx::ActiveItemRecalcLayout  
 레이아웃 OLE 클라이언트 항목 및 프레임의 클라이언트 영역을 조정합니다.  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="addpane"></a>CFrameWndEx::AddPane  
 관리자는 도킹 컨트롤 막대에 등록합니다.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 등록 하는 컨트롤 막대 창입니다.  
  
 [in] `bTail`  
 `TRUE`컨트롤 막대 창 목록 끝에 추가 하려는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`컨트롤 막대 성공적으로 등록 되었습니다. `FALSE` 그렇지 않은 경우.  
  
##  <a name="adjustdockinglayout"></a>CFrameWndEx::AdjustDockingLayout  
 프레임 창에 도킹 된 모든 창 레이아웃을 다시 계산 합니다.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `hdwp`  
 여러 개의 창의 위치를 포함 하는 구조에 대 한 핸들입니다. 입니다.  
  
### <a name="remarks"></a>주의  
 Hdwp 구조에 의해 초기화 됩니다는 [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) 메서드.  
  
##  <a name="delayupdateframemenu"></a>CFrameWndEx::DelayUpdateFrameMenu  
 프레임 메뉴를 설정 하 고 명령 처리 유휴 상태일 때 업데이트 합니다.  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenuAlt`  
 대체를 메뉴에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="dockpane"></a>CFrameWndEx::DockPane  
 지정 된 창 프레임 창에 도킹합니다.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 도킹 컨트롤 막대에 대 한 포인터입니다.  
  
 [in] `nDockBarID`  
 프레임 창에 도킹 측면의 ID입니다.  
  
 [in] `lpRect`  
 창의 화면 위치와 크기를 지정 하는 상수 Rect 구조체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `nDockBarID` 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="dockpaneleftof"></a>CFrameWndEx::DockPaneLeftOf  
 지정한 창을 다른 창 왼쪽에 도킹합니다.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 도킹 창 개체에 대 한 포인터입니다.  
  
 [in] `pLeftOf`  
 로 지정 된 창 도킹 하는 왼쪽 창에 대 한 포인터 `pBar`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 `pBar` 성공적으로 도킹 합니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 메서드는 지정 된 도구 모음에서 `pBar` 매개 변수 및 도킹 하 여 지정 된 왼쪽 도구 모음에서 `pLeftOf` 매개 변수입니다.  
  
##  <a name="enableautohidepanes"></a>CFrameWndEx::EnableAutoHidePanes  
 수 있도록 자동 숨김 모드는 창에 대 한 주 프레임 창의 지정된 된 측면에 도킹 되는 경우입니다.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwDockStyle`  
 창을 도킹를 주 프레임 창의 측면을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 막대를 창에 지정 된 프레임 창 왼쪽에 도킹 성공적으로 `dwDockStyle`, `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 `dwDockStyle`다음 값 중 하나일 수 있습니다.  
  
-   CBRS_ALIGN_TOP: 컨트롤 막대를를 프레임 창의 클라이언트 영역 위쪽에 도킹 될 수 있습니다.  
  
-   CBRS_ALIGN_BOTTOM: 컨트롤 막대를 프레임 창의 클라이언트 영역 아래쪽에 도킹 될 수 있습니다.  
  
-   CBRS_ALIGN_LEFT: 컨트롤 막대를를 왼쪽 프레임 창의 클라이언트 영역에 도킹할 수 있습니다.  
  
-   CBRS_ALIGN_RIGHT: 컨트롤 막대를 프레임 창의 클라이언트 영역 오른쪽에 도킹 될 수 있습니다.  
  
##  <a name="enabledocking"></a>CFrameWndEx::EnableDocking  
 프레임 창의 창 도킹 수 있습니다.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwDockStyle`  
 창 모음을 도킹 주 프레임 창의 측면을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 막대 창 성공적으로 지정된 된 측면에 도킹 될 수 있습니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 `dwDockStyle` 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="enablefullscreenmainmenu"></a>CFrameWndEx::EnableFullScreenMainMenu  
 표시 하거나 전체 화면 모드에서 주 메뉴를 숨깁니다.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnableMenu`  
 `TRUE`전체 화면 모드에서 주 메뉴를 표시 하려면 `FALSE` 그렇지 않은 경우.  
  
##  <a name="enablefullscreenmode"></a>CFrameWndEx::EnableFullScreenMode  
 프레임 창에 대 한 전체 화면 모드를 활성화 합니다.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiFullScreenCmd`  
 전체 화면 모드 사용 여부를 설정 하는 명령 ID입니다.  
  
### <a name="remarks"></a>주의  
 전체 화면 모드에서는 모든 도킹 컨트롤 막대, 도구 모음과 메뉴는 숨겨져 있으며, 활성 뷰가 전체 화면을 차지 하도록 크기가 조정 됩니다.  
  
 전체 화면 모드를 사용 하도록 설정 하면 전체 화면 모드를 사용할지 여부를 지정 하는 명령 ID를 지정 해야 합니다. 호출할 수 있습니다 `EnableFullScreenMode` 주 프레임에서 `OnCreate` 함수입니다. 프레임 워크는 지정 된 명령 ID를 가진 하나의 단추가 있는 부동 도구 모음을 만들고 프레임 창을 전체 화면 모드로 전환 되는 경우  
  
 화면에서 주 메뉴를 유지 하려는 경우에 호출 [CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)합니다.  
  
##  <a name="enableloaddockstate"></a>CFrameWndEx::EnableLoadDockState  
 도킹 상태를 로드 하는 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`도킹 상태 로드를 사용 하려면 `FALSE` 도킹 상태를 로드 하는 사용 하지 않으려면 합니다.  
  
##  <a name="enablepanemenu"></a>CFrameWndEx::EnablePaneMenu  
 창 메뉴의 자동 처리를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly=FALSE,  
    BOOL bViewMenuShowsToolbarsOnly=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`팝업 메뉴; 막대 컨트롤의 자동 처리를 사용 하도록 설정 하려면 `FALSE` 에 팝업 메뉴 표시줄 컨트롤의 자동 처리를 사용 하지 않도록 설정 합니다.  
  
 [in] `uiCustomizeCmd`  
 명령 ID는 **사용자 지정** 메뉴 항목입니다.  
  
 [in] `strCustomizeLabel`  
 에 대해 표시할 레이블을 **사용자 지정** 메뉴 항목  
  
 [in] `uiViewToolbarsMenuEntryID`  
 컨트롤 막대에서 팝업 메뉴를 열고 도구 모음 메뉴 항목의 ID입니다.  
  
 [in] `bContextMenuShowsToolbarsOnly`  
 경우 `TRUE`, 상황에 맞는 메뉴 표시줄 컨트롤 도구 모음에만 목록이 표시 됩니다. 경우 `FALSE`, 메뉴 도구 모음 및 도킹 막대 목록이 표시 됩니다.  
  
 [in] `bViewMenuShowsToolbarsOnly`  
 경우 `TRUE`, 컨트롤 모음 메뉴에 있는 도구 모음 목록이 표시 됩니다. 경우 `FALSE`, 메뉴 도구 모음 및 도킹 막대 목록이 표시 됩니다.  
  
##  <a name="getactivepopup"></a>CFrameWndEx::GetActivePopup  
 현재 표시 된 팝업 메뉴에 대 한 포인터를 반환합니다.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 표시 된 팝업 메뉴;에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
##  <a name="getdefaultresid"></a>CFrameWndEx::GetDefaultResId  
 프레임 워크는 프레임 창 로드 될 때 지정 된 리소스 ID를 반환 합니다.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용자는 프레임 워크는 프레임 창을 로드 하는 경우 지정 된 리소스 ID 값입니다. 프레임 창 메뉴 모음을 사용 하지 않은 경우&0;입니다.  
  
##  <a name="getdockingmanager"></a>CFrameWndEx::GetDockingManager  
 검색 된 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 프레임 창에 대 한 개체입니다.  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 프레임 창에서 만들고 사용 하는 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 자식 창을 도킹을 관리 하는 개체입니다.  
  
##  <a name="getmenubar"></a>CFrameWndEx::GetMenuBar  
 프레임 창에 연결된 메뉴 모음 개체에 대한 포인터를 반환합니다.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프레임 창에 연결 하는 메뉴 모음 개체에 대 한 포인터입니다.  
  
##  <a name="getpane"></a>CFrameWndEx::GetPane  
 지정 된 ID를 가집니다. 창에 대 한 포인터를 반환 합니다.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 컨트롤 id입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 id의 창에 대 한 포인터 `NULL`이러한 창 없는 있으면 됩니다.  
  
##  <a name="getribbonbar"></a>CFrameWndEx::GetRibbonBar  
 프레임에 대해 리본 표시줄 컨트롤을 검색합니다.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md) 프레임입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="gettearoffbars"></a>CFrameWndEx::GetTearOffBars  
 분리 상태에 있는 창 개체의 목록을 반환합니다.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조 `CObList` 분리 상태에 있는 창 개체에 대 한 포인터 컬렉션을 포함 하는 개체입니다.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CFrameWndEx::GetToolbarButtonToolTipText  
 응용 프로그램 도구 모음 단추에 대 한 도구 설명을 표시 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 도구 모음 단추에 대 한 포인터입니다.  
  
 [in] `strTTText`  
 단추에 대해 표시할 도구 설명 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도구 설명 표시 된 경우 합니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 도구 모음 단추에 대 한 도구 설명을 표시 하려면이 메서드를 재정의 합니다.  
  
##  <a name="insertpane"></a>CFrameWndEx::InsertPane  
 컨트롤 막대 목록에 창을 삽입하고 도킹 관리자에 등록합니다.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControlBar`  
 컨트롤 막대 목록에 삽입하고 도킹 관리자에 등록할 컨트롤 막대에 대한 포인터입니다.  
  
 `pTarget`  
 앞이나 뒤에 창을 삽입할 컨트롤 막대에 대한 포인터입니다.  
  
 `bAfter`  
`pTarget` 뒤에 `pControlBar`를 삽입하려는 경우  `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대를 성공적으로 삽입 및 등록한 경우 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 각 컨트롤 막대를 사용 하 여 등록 해야는 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 도킹 레이아웃 참여 하도록 합니다.  
  
##  <a name="isfullscreen"></a>CFrameWndEx::IsFullScreen  
 프레임 창을 전체 화면 모드 인지 여부를 결정 합니다.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 창을 전체 화면 모드에 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 호출 하 여 전체 화면 모드를 설정할 수는 [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) 메서드.  
  
##  <a name="ismenubaravailable"></a>CFrameWndEx::IsMenuBarAvailable  
 메뉴 모음 개체에 대 한 포인터 유효한 지 여부를 결정 합니다.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 창에는 메뉴 모음입니다. 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="ispointneardocksite"></a>CFrameWndEx::IsPointNearDockSite  
 지점 맞춤 영역에 있는지 여부를 결정 합니다.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 포인터의 위치입니다.  
  
 [out] `dwBarAlignment`  
 여기서는 지점 정렬 됩니다. 가능한 값에 대 한 설명 섹션의 표를 참조 하십시오.  
  
 [out] `bOuterEdge`  
 `TRUE`중요 한 점은 프레임 테두리; 가까이 위치 하는 경우 `FALSE` 지점 클라이언트 영역에 있는 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지점은 맞춤 영역;에 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 다음 표에서 사용할 수 있는 값은 `dwBarAlignment` 매개 변수입니다.  
  
 `CBRS_ALIGN_TOP`  
 위쪽에 정렬 합니다.  
  
 `CBRS_ALIGN_RIGHT`  
 오른쪽에 맞춥니다.  
  
 `CBRS_ALIGN_BOTTOM`  
 아래쪽에 정렬 합니다.  
  
 `CBRS_ALIGN_LEFT`  
 왼쪽에 맞춥니다.  
  
##  <a name="isprintpreview"></a>CFrameWndEx::IsPrintPreview  
 프레임 창 인쇄 미리 보기 모드 인지 여부를 결정 합니다.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 창 인쇄 미리 보기 모드에 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="loadframe"></a>CFrameWndEx::LoadFrame  
 이 메서드는 프레임 창을 만들고 해당 리소스를 로드 하는 생성 후 호출 됩니다.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIDResource`  
 프레임의 모든 리소스를 로드 하는 데 사용 되는 리소스 ID입니다.  
  
 [in] `dwDefaultStyle`  
 기본 프레임 창 스타일입니다.  
  
 [in] `pParentWnd`  
 프레임의 부모 창에 대 한 포인터입니다.  
  
 [in] `pContext`  
 에 대 한 포인터는 [CCreateContext 구조](../../mfc/reference/ccreatecontext-structure.md) 프레임 워크에서 응용 프로그램을 만드는 동안 사용 되는 클래스입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공했으면 `TRUE`이고, 실패했으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="negotiateborderspace"></a>CFrameWndEx::NegotiateBorderSpace  
 구현 OLE 클라이언트 테두리 협상 합니다.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nBorderCmd`  
 테두리 협상 명령입니다. 가능한 값에 대 한 설명 섹션을 참조 합니다.  
  
 [in, out] `lpRectBorder`  
 테두리의 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 레이아웃을 다시 계산 해야 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 다음 표에서 사용할 수 있는 값은 `nBorderCmd` 매개 변수입니다.  
  
 `borderGet`  
 사용 가능한 OLE 클라이언트 공간을 가져옵니다.  
  
 `borderRequest`  
 OLE 클라이언트 공간을 요청 합니다.  
  
 `borderSet`  
 OLE 클라이언트 공간을 설정 합니다.  
  
##  <a name="onactivate"></a>CFrameWndEx::OnActivate  
 프레임 워크는 사용자 입력 하거나 프레임에서 전환 되 면이 메서드를 호출 합니다.  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nState`  
 인지 프레임 활성 또는 비활성입니다. 가능한 값에 대 한 설명 섹션의 표를 참조 하십시오.  
  
 [in] `pWndOther`  
 현재와 함께 사용자 입력을 전환 하는 다른 창에 대 한 포인터입니다.  
  
 [in] `bMinimized`  
 프레임의 최소화 된 상태입니다. `TRUE`프레임 최소화 되 고, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 다음 표에서 사용할 수 있는 값은 `nState` 매개 변수입니다.  
  
 `WA_ACTIVE`  
 프레임은 마우스 클릭 아닌 방법으로 선택 됩니다.  
  
 `WA_CLICKACTIVE`  
 프레임은 마우스 클릭으로 선택 됩니다.  
  
 `WA_INACTIVE`  
 프레임을 선택 하지 않았습니다.  
  
##  <a name="onactivateapp"></a>CFrameWndEx::OnActivateApp  
 응용 프로그램 선택 되거나 선택이 취소 될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActive`  
 `TRUE`응용 프로그램을 선택 합니다. `FALSE` 응용 프로그램을 선택 하지 않은 경우.  
  
 [in] `dwThreadID`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onchangevisualmanager"></a>CFrameWndEx::OnChangeVisualManager  
 프레임에 대 한 변경 비주얼 관리자에 대 한 변경 해야 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
afx_msg LRESULT OnChangeVisualManager(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wParam`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lParam`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onclose"></a>CFrameWndEx::OnClose  
 프레임 워크는 프레임을 닫아도이 메서드를 호출 합니다.  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>주의  
 인쇄 미리 보기;를 닫으려면 Windows 메시지를 보낼 프레임 인쇄 미리 보기 모드에 있으면 그렇지 않으면 프레임 OLE 클라이언트를 호스팅하는 경우 클라이언트 비활성화 됩니다.  
  
##  <a name="onclosedockingpane"></a>CFrameWndEx::OnCloseDockingPane  
 사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 도킹 창에 단추입니다.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 도킹 모음을 닫을 수 있습니다. `FALSE`그렇지 않은 경우  
  
### <a name="remarks"></a>주의  
 기본 구현 되지 않습니다. 도킹 모음 숨기기를 처리 하려면이 메서드를 재정의 합니다.  
  
##  <a name="oncloseminiframe"></a>CFrameWndEx::OnCloseMiniFrame  
 사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 부동 미니 프레임 창에 단추입니다.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`부동 경우 미니 프레임 창을 닫을 수 있습니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행하지 않습니다. 부동 미니 프레임 창 숨기 처리 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="onclosepopupmenu"></a>CFrameWndEx::OnClosePopupMenu  
 활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMenuPopup`  
 팝업 메뉴에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크를 닫도록 되었을 때 WM_DESTROY 메시지를 보냅니다. 알림을 처리 하려는 경우이 메서드를 재정의 `CMFCPopupMenu` 프레임 창에 속하는 개체 때는 `CMFCPopupMenu` 개체 처리는 `WM_DESTROY` 창이 되 고 닫혀 있는 경우 프레임 워크에서 보낸 메시지입니다.  
  
##  <a name="oncmdmsg"></a>CFrameWndEx::OnCmdMsg  
 디스패치 메시지 명령합니다.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 명령 ID입니다.  
  
 [in] `nCode`  
 명령 메시지 범주입니다.  
  
 [in, out] `pExtra`  
 명령 개체에 대 한 포인터입니다.  
  
 [in, out] `pHandlerInfo`  
 명령 처리기 구조에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`명령 메시지가 처리 되는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="oncontexthelp"></a>CFrameWndEx::OnContextHelp  
 상황에 맞는 관련 도움말을 표시 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="oncreate"></a>CFrameWndEx::OnCreate  
 프레임을 만든 후에 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpCreateStruct`  
 에 대 한 포인터는 [CREATESTRUCT 구조체](../../mfc/reference/createstruct-structure.md) 새로운 프레임입니다.  
  
### <a name="return-value"></a>반환 값  
 계속 프레임 만들기;&0; 프레임을 삭제 하려면-1입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="ondestroy"></a>CFrameWndEx::OnDestroy  
 프레임 소멸 되 면 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>주의  
 액셀러레이터 키 테이블 및 모든 창을 소멸 됩니다.  
  
##  <a name="ondrawmenuimage"></a>CFrameWndEx::OnDrawMenuImage  
 응용 프로그램 메뉴 항목과 연결 된 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `pMenuButton`  
 이미지를 렌더링 되 고 메뉴 단추에 대 한 포인터입니다.  
  
 [in] `rectImage`  
 에 대 한 포인터는 `Rect` 화면 위치와 이미지의 크기를 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 워크 성공적으로 이미지를 렌더링 하는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 가 소유 하 고 메뉴 모음에 속하는 메뉴 항목에 대 한 이미지 렌더링을 사용자 지정 하려는 경우이 메서드를 재정의 하는 `CFrameWndEx` 파생 개체입니다.  
  
##  <a name="ondrawmenulogo"></a>CFrameWndEx::OnDrawMenuLogo  
 프레임 워크에서 호출 하면는 `CMFCPopupMenu` WM_PAINT 메시지를 처리 하는 개체입니다.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `pMenu`  
 메뉴 항목에 대 한 포인터입니다.  
  
 [in] `rectLogo`  
 상수에 대 한 참조 `CRect` 메뉴 로고의 크기와 화면 위치를 지정 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 가 소유 하 고 메뉴 모음에 속하는 팝업 메뉴에 로고를 표시 하려는 경우이 함수를 재정의 `CFrameWndEx` 파생 개체입니다.  
  
##  <a name="ondwmcompositionchanged"></a>CFrameWndEx::OnDWMCompositionChanged  
 데스크톱 창 관리자 (DWM) 컴퍼지션 활성화 또는 비활성화 되었으므로 때 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg LRESULT OnDWMCompositionChanged(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wp`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lp`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onexitsizemove"></a>CFrameWndEx::OnExitSizeMove  
 프레임 이동 하거나 크기 조정 중지 될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
LRESULT OnExitSizeMove(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wp`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lp`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="ongetminmaxinfo"></a>CFrameWndEx::OnGetMinMaxInfo  
 프레임 창 차원 제한을 설정 하는 크기가 조정 될 때 프레임 워크에서 호출 합니다.  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpMMI`  
 에 대 한 포인터는 [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605) 구조입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onidleupdatecmdui"></a>CFrameWndEx::OnIdleUpdateCmdUI  
 명령 처리 유휴 상태일 때 프레임 디스플레이 업데이트 하려면 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg LRESULT OnIdleUpdateCmdUI(
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wParam`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lParam`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onlbuttondown"></a>CFrameWndEx::OnLButtonDown  
 프레임 워크는 사용자가 왼쪽된 마우스 단추를 누르면이 메서드를 호출 합니다.  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlags`  
 사용자 보조키를 눌렀는지 여부를 나타냅니다. 가능한 값 매개 변수 참조에 대 한 `wParam` 에서 [WM_LBUTTONDOWN 알림](http://msdn.microsoft.com/library/windows/desktop/ms645607)합니다.  
  
 [in] `point`  
 X 및 포인터의 y 좌표, 상대 창의 왼쪽 위 모퉁이를 지정합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onlbuttonup"></a>CFrameWndEx::OnLButtonUp  
 마우스 왼쪽된 단추를 놓을 때이 메서드를 호출 하는 프레임 워크입니다.  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlags`  
 사용자 보조키를 눌렀는지 여부를 나타냅니다. 가능한 값 매개 변수 참조에 대 한 `wParam` 에서 [WM_LBUTTONUP 알림](http://msdn.microsoft.com/library/windows/desktop/ms645608)합니다.  
  
 [in] `point`  
 X 및 포인터의 y 좌표, 상대 창의 왼쪽 위 모퉁이를 지정합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onmenubuttontoolhittest"></a>CFrameWndEx::OnMenuButtonToolHitTest  
 프레임 워크 호출 때는 `CMFCToolBarButton` 프로세스 개체를 `WM_NCHITTEST` 메시지입니다.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 도구 모음 단추에 대 한 포인터입니다.  
  
 [out] `pTI`  
 도구 정보 구조에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`응용 프로그램은 작성 하는 경우는 `pTI` 매개 변수입니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 특정 메뉴 항목에 대 한 도구 설명 정보를 제공 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="onmenuchar"></a>CFrameWndEx::OnMenuChar  
 메뉴가 표시 되 고 사용자 명령에 해당 하지 않는 키를 누를 때 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nChar`  
 누른된 키의 문자 코드입니다.  
  
 [in] `nFlags`  
 포함는 `MF_POPUP` 플래그 메뉴가 있는 경우 표시 되는 하위 메뉴; 포함는 `MF_SYSMENU` 표시 되는 메뉴 컨트롤 메뉴는 플래그를 지정 합니다.  
  
 [in] `pMenu`  
 메뉴에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 상위 word에는 다음 값 중 하나 여야 합니다.  
  
 `0`  
 프레임 워크 키 입력을 무시 해야 합니다.  
  
 `1`  
 프레임 워크의 메뉴를 닫아야 합니다.  
  
 `2`  
 프레임 워크는 메뉴에 표시 되는 항목 중 하나를 선택 해야 합니다. 하위 단어를 선택 하는 명령의 ID를 포함 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onmousemove"></a>CFrameWndEx::OnMouseMove  
 프레임 워크는 포인터를 이동 하면이 메서드를 호출 합니다.  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlags`  
 사용자 보조키를 눌렀는지 여부를 나타냅니다. 가능한 값 매개 변수 참조에 대 한 `wParam` 에서 [WM_MOUSEMOVE 알림](http://msdn.microsoft.com/library/windows/desktop/ms645616)합니다.  
  
 [in] `point`  
 X 및 y 지정 창의 왼쪽 위 모퉁이 기준으로 포인터의 좌표입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onmoveminiframe"></a>CFrameWndEx::OnMoveMiniFrame  
 창 창 이동 하면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrame`  
 에 대 한 포인터는 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md) 창입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 창을 도킹 되어 있지 않으면; 하는 경우 `FALSE` 창 창이 도킹 된 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onncactivate"></a>CFrameWndEx::OnNcActivate  
 프레임의 클라이언트 이외의 영역에서는 활성 상태의 변화를 나타내기 위해 그려야 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActive`  
 `TRUE`활성; 프레임을 그리려면 `FALSE` 비활성 프레임을 그리려면 합니다.  
  
### <a name="return-value"></a>반환 값  
 기본 처리 합니다; 계속 하려면 0이 아닌 비클라이언트 영역 비활성화 되지 않도록 하려면 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onnccalcsize"></a>CFrameWndEx::OnNcCalcSize  
 클라이언트 영역 위치와 크기를 계산 해야 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bCalcValidRects`  
 `TRUE`응용 프로그램을 유효한 클라이언트 영역; 해야 지정 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
 [in] `lpncsp`  
 에 대 한 포인터는 `NCCALCSIZE_PARAMS` 프레임 차원 변경 내용이 포함 된 구조입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onnchittest"></a>CFrameWndEx::OnNcHitTest  
 포인터를 이동할 때 또는 마우스 단추를 누르거나 놓을 때 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 화면 좌표에서 포인터의 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 포인터는 열거 값을 누릅니다. 가능한 값 목록은 참조 하십시오. [WM_NCHITTEST 알림을](http://msdn.microsoft.com/library/windows/desktop/ms645618)합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onncmousemove"></a>CFrameWndEx::OnNcMouseMove  
 비클라이언트 영역에서 포인터를 이동 하면 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHitTest`  
 포인터는 열거 값을 누릅니다. 가능한 값 목록은 참조 하십시오. [WM_NCHITTEST 알림을](http://msdn.microsoft.com/library/windows/desktop/ms645618)합니다.  
  
 [in] `point`  
 화면 좌표에서 포인터의 위치입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onncpaint"></a>CFrameWndEx::OnNcPaint  
 비클라이언트 영역을 칠할 해야 하는 경우 프레임 워크에서 호출 합니다.  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="onpanecheck"></a>CFrameWndEx::OnPaneCheck  
 창의 표시 유형을 제어 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 컨트롤 ID는 창입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`명령이 처리 되는 경우 `FALSE` 명령 처리를 계속 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onpostpreviewframe"></a>CFrameWndEx::OnPostPreviewFrame  
 사용자는 인쇄 미리 보기 모드를 변경할 때 프레임 워크에서 호출 합니다.  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wParam`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lParam`  
 `TRUE`인쇄 미리 보기 모드에는 프레임의 경우 `FALSE` 때 인쇄 미리 보기 모드를 해제 합니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onpowerbroadcast"></a>CFrameWndEx::OnPowerBroadcast  
 전원 관리 이벤트가 발생할 때 프레임 워크에서 호출 합니다.  
  
```  
afx_msg LRESULT OnPowerBroadcast(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wp`  
 전원 관리 이벤트입니다. 가능한 값 목록은 참조 하십시오. [WM_POWERBROADCAST 메시지](http://msdn.microsoft.com/library/windows/desktop/aa373247)합니다.  
  
 [in] `lp`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 기본 창 프로시저로 호출에서 비롯 됩니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsetmenu"></a>CFrameWndEx::OnSetMenu  
 프레임 창 메뉴를 대체 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wp`  
 새 프레임 창 메뉴에 대 한 핸들입니다.  
  
 [in] `lp`  
 새 창 메뉴에 대 한 핸들입니다.  
  
 [in] `hmenu`  
 새 프레임 창 메뉴에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 `LRESULT`기본 창 프로시저로 호출의 결과가입니다.  
  
 `BOOL``TRUE` 이벤트를 처리 하 고, 그렇지 않으면 하면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsetpreviewmode"></a>CFrameWndEx::OnSetPreviewMode  
 프레임에 대 한 인쇄 미리 보기 모드를 설정 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bPreview`  
 `TRUE`인쇄 미리 보기를 사용 하도록 설정 하려면 `FALSE` 에 인쇄 미리 보기를 사용 하지 않도록 설정 합니다.  
  
 [in] `pState`  
 에 대 한 포인터는 `CPrintPreviewState` 상태 구조 프레임입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsettext"></a>CFrameWndEx::OnSetText  
 창의 텍스트를 설정 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg LRESULT OnSetText(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wParam`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lParam`  
 창에 대 한 텍스트에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값에 대 한 호출에서 [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572)합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onshowcustomizepane"></a>CFrameWndEx::OnShowCustomizePane  
 표시 될 때 프레임 워크에서 호출 된 `QuickCustomizePane`합니다.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPane`  
 빠른에 대 한 포인터 창을 사용자 지정 합니다.  
  
 [in] `uiToolbarID`  
 사용자 지정 도구 모음 컨트롤 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 항상 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>주의  
 빠른 사용자 지정 도구 모음의 단추를 사용자 지정 클릭 하면 표시 되는 팝업 메뉴가 메뉴 인지  
  
##  <a name="onshowpanes"></a>CFrameWndEx::OnShowPanes  
 표시 하거나 숨기려면 창 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 `TRUE`응용 프로그램 표시 되는 창입니다. `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 항상 반환 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 창을 보여 줍니다 경우 `bShow` 는 `TRUE` 는 창이 숨겨집니다 및 때나 `bShow` 는 `FALSE` 는 창이 표시 됩니다.  
  
 기본 구현은 경우 창을 숨깁니다 `bShow` 는 `TRUE` 는 창이 표시 됩니다. 또는 `bShow` 는 `FALSE` 및는 창이 숨겨집니다.  
  
 프레임 워크를 표시 하거나 숨깁니다 창 때 사용자 지정 코드를 실행 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onshowpopupmenu"></a>CFrameWndEx::OnShowPopupMenu  
 팝업 메뉴를 표시 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenu`  
 팝업 메뉴에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`팝업 메뉴가 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 팝업 메뉴를 표시 하는 경우 사용자 지정 코드를 실행 하려면 파생된 클래스에서이 메서드를 재정의 합니다. 예를 들어, 팝업 메뉴의 명령의 배경색을 변경 하려면이 메서드를 재정의 합니다.  
  
##  <a name="onsize"></a>CFrameWndEx::OnSize  
 프레임의 크기 변경 된 후 프레임 워크에서 호출합니다.  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nType`  
 크기 조정의 형식입니다. 가능한 값 매개 변수 참조에 대 한 `wParam` 에서 [WM_SIZE 알림을](http://msdn.microsoft.com/library/windows/desktop/ms632646)합니다.  
  
 [in] `cx`  
 픽셀에서 프레임의 새 너비입니다.  
  
 [in] `cy`  
 픽셀에서 프레임의 새 높이입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsizing"></a>CFrameWndEx::OnSizing  
 사용자가 프레임 크기 조정에 프레임 워크에서 호출 합니다.  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `fwSide`  
 이동 된 프레임의 가장자리입니다. 매개 변수 참조 `wParam` 에서 [WM_SIZING 알림](http://msdn.microsoft.com/library/windows/desktop/ms632647)합니다.  
  
 [in, out] `pRect`  
 에 대 한 포인터는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 또는 [RECT](../../mfc/reference/rect-structure1.md) 프레임의 좌표를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsyscolorchange"></a>CFrameWndEx::OnSysColorChange  
 시스템 색이 변경 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="ontearoffmenu"></a>CFrameWndEx::OnTearOffMenu  
 응용 프로그램 표시줄이 있는 분리 메뉴를 표시 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPopup`  
 팝업 메뉴에 대 한 포인터입니다.  
  
 [in] `pBar`  
 분리 모음에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`분리 막대를 사용 하 여 팝업 메뉴를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 컨트롤 막대를 표시 하는 경우 사용자 지정 코드를 실행 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
 기본 구현은 없으며 반환 `TRUE`합니다.  
  
##  <a name="ontoolbarcontextmenu"></a>CFrameWndEx::OnToolbarContextMenu  
 프레임 워크 빌드 도구 모음 팝업 메뉴에 의해 호출 됩니다.  
  
```  
afx_msg LRESULT OnToolbarContextMenu(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wp`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lp`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="ontoolbarcreatenew"></a>CFrameWndEx::OnToolbarCreateNew  
 프레임 워크에는 새 도구 모음을 만들도록이 메서드를 호출 합니다.  
  
```  
afx_msg LRESULT OnToolbarCreateNew(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wp`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lp`  
 도구 모음에서의 제목 표시줄에 대 한 텍스트에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 새 도구 모음;에 대 한 포인터 또는 `NULL` 도구 모음을 만들지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="ontoolbardelete"></a>CFrameWndEx::OnToolbarDelete  
 도구 모음에서 삭제 되는 프레임 워크에서 호출 합니다.  
  
```  
afx_msg LRESULT OnToolbarDelete(
    WPARAM, 
    LPARAM lp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in]  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `lp`  
 도구 모음에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도구 모음에서 삭제 되었으면 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onupdateframemenu"></a>CFrameWndEx::OnUpdateFrameMenu  
 프레임 메뉴를 설정 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenuAlt`  
 다른 메뉴에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onupdateframetitle"></a>CFrameWndEx::OnUpdateFrameTitle  
 프레임 워크는 프레임 창의 제목 표시줄을 업데이트 하려면이 메서드를 호출 합니다.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAddToTitle`  
 `TRUE`프레임 창 제목 표시줄;를 현재 문서 제목을 추가 하려면 그렇지 않은 경우`FALSE.`  
  
### <a name="remarks"></a>주의  
  
##  <a name="onupdatepanemenu"></a>CFrameWndEx::OnUpdatePaneMenu  
 창 메뉴를 업데이트 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pCmdUI`  
 창 사용자 인터페이스 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onwindowposchanged"></a>CFrameWndEx::OnWindowPosChanged  
 프레임 크기, 위치, 또는 z 창 관리 방법에 대 한 호출으로 인해 변경 된 경우에 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpwndpos`  
 에 대 한 포인터는 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) 새 크기와 위치를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="panefrompoint"></a>CFrameWndEx::PaneFromPoint  
 지정된 된 지점에 대 한 각 창을 검색합니다.  
  
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
 [in] `point`  
 체크 포인트의 화면 좌표입니다.  
  
 [in] `nSensitivity`  
 지점에 대 한 검색 하는 경우이 값으로 각 컨트롤 막대의 경계 사각형을 확장 합니다.  
  
 [in] `bExactBar`  
 `TRUE`무시 하려면는 `nSensitivity` 매개 변수 이거나, `FALSE`합니다.  
  
 [in] `pRTCBarType`  
 그렇지 않은 경우 `NULL`, 메서드는 지정 된 형식의 컨트롤 막대만 검색 합니다.  
  
 [out] `dwAlignment`  
 성공 하면이 매개 변수는 지정된 된 지점에 가장 가까운 컨트롤 막대의 측면을 포함 합니다. 그렇지 않으면이 매개 변수는 초기화 되지 않았습니다.  
  
### <a name="return-value"></a>반환 값  
 포함 하는 컨트롤 막대에 대 한 포인터는 `point`; `NULL` 컨트롤이 발견 되는 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 모든 컨트롤 막대에 대 한 응용 프로그램에서 검색 한 `point`합니다.  
  
 사용 하 여 `nSensitivity` 검색 영역의 크기를 늘려야 합니다. 사용 하 여 `pRTCBarType` 메서드를 검색 하는 컨트롤 막대의 형식을 제한 합니다.  
  
##  <a name="pretranslatemessage"></a>CFrameWndEx::PreTranslateMessage  
 디스패치 되기 전에 특정 창 메시지를 처리 합니다.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMsg`  
 에 대 한 포인터는 [MSG](../../mfc/reference/msg-structure1.md) 처리할 메시지를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 메시지 처리 하 고 발송 되어야 합니다. 메시지가 처리 되지 않은 고 디스패치해야 하는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="recalclayout"></a>CFrameWndEx::RecalcLayout  
 프레임 및 해당 자식 창의 레이아웃을 조정합니다.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bNotify`  
 레이아웃 변경에 대 한 OLE 클라이언트 항목을 알릴지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 컨트롤 막대 표시 되거나 숨겨진 경우 또는 프레임 창의 크기가 변경 될 때 호출 됩니다.  
  
##  <a name="removepanefromdockmanager"></a>CFrameWndEx::RemovePaneFromDockManager  
 창을 등록을 취소 하 고 도킹 관리자에서 제거 합니다.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 제거할 컨트롤 모음 창에 대 한 포인터입니다.  
  
 [in] `bDestroy`  
 `TRUE`컨트롤 막대,를 제거한 후 삭제 하려면 `FALSE` 그렇지 않은 경우.  
  
 [in] `bAdjustLayout`  
 `TRUE`도킹 레이아웃을 조정 하려면 `FALSE` 그렇지 않은 경우.  
  
 [in] `bAutoHide`  
 `TRUE`컨트롤 막대; 자동 숨김 모드로 `FALSE` 그렇지 않은 경우.  
  
 [in] `pBarReplacement`  
 제거 창을 대체 하는 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 프레임 창의 도킹 레이아웃에서 컨트롤 막대를 제거 하려면이 메서드를 사용 합니다.  
  
 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 컨트롤 막대의 레이아웃을 처리 합니다. 도킹 관리자를 사용 하 여 등록 해야 각 컨트롤 막대는 [CFrameWndEx::AddPane](#addpane) 메서드 또는 [CFrameWndEx::InsertPane](#insertpane) 메서드.  
  
##  <a name="setdockstate"></a>CFrameWndEx::SetDockState  
 레지스트리에 저장 된 도킹 상태를 도킹 레이아웃을 복원 합니다.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>매개 변수  
 `state`  
 도킹 상태입니다. 이 매개 변수는 무시됩니다.  
  
##  <a name="setprintpreviewframe"></a>CFrameWndEx::SetPrintPreviewFrame  
 인쇄 미리 보기 프레임 창을 설정입니다.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 인쇄 미리 보기 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setuptoolbarmenu"></a>CFrameWndEx::SetupToolbarMenu  
 도구 모음 메뉴에 사용자 지정 명령을 삽입 합니다.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `menu`  
 A `CMenu` 개체를 수정할 수 있습니다.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 첫 번째 사용자 정의 명령입니다.  
  
 [in] `uiViewUserToolbarCmdLast`  
 마지막 사용자 정의 명령입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 목록에 사용자 지정 명령을 저장합니다. 사용 하 여 `uiViewUserToolbarCmdFirst` 및 `uiViewUserToolbarCmdList` 삽입할 수 있는 명령에 대 한 인덱스를 지정할 수 있습니다.  
  
##  <a name="showfullscreen"></a>CFrameWndEx::ShowFullScreen  
 주 프레임 전체 화면 모드와 일반 모드 사이 전환합니다.  
  
```  
void ShowFullScreen();
```  
  
##  <a name="showpane"></a>CFrameWndEx::ShowPane  
 표시 하거나 지정한 창을 숨깁니다.  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 컨트롤 막대 표시 하거나 숨길 수에 대 한 포인터입니다.  
  
 [in] `bShow`  
 경우 `TRUE`, 응용 프로그램은 컨트롤 막대를 표시 합니다. 그렇지 않으면 응용 프로그램은 컨트롤 막대를 숨깁니다.  
  
 [in] `bDelay`  
 경우 `TRUE`, 프레임 워크 호출 될 때까지 도킹 레이아웃의 조정 지연 [CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)합니다. 도킹 레이아웃을 즉시 다시 계산 그렇지 않은 경우.  
  
 [in] `bActivate`  
 경우 `TRUE`, 컨트롤 막대를 활성화 합니다. 그렇지 않으면 비활성 상태에서 컨트롤 막대를 표시 합니다.  
  
##  <a name="updatecaption"></a>CFrameWndEx::UpdateCaption  
 창 프레임 캡션을 업데이트 하는 프레임 워크에서 호출 됩니다.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="winhelp"></a>CFrameWndEx::WinHelp  
 WinHelp 응용 프로그램 또는 상황에 맞는 호출 관련 도움말입니다.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwData`  
 데이터에 의존 하는 `nCmd` 매개 변수입니다. 가능한 값 목록은 참조 하십시오. [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267)합니다.  
  
 `nCmd`  
 도움말 명령입니다. 가능한 값 목록은 참조 하십시오. [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267)합니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)

