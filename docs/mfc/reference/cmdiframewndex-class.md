---
title: "CMDIFrameWndEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWndEx.AddDockSite
- CMDIFrameWndEx
- CMDIFrameWndEx::AddDockSite
dev_langs:
- C++
helpviewer_keywords:
- CMDIFrameWndEx class
ms.assetid: dbcafcb3-9a7a-4f11-9dfe-ba57565c81d0
caps.latest.revision: 42
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b9946f59b9ed789604ac6a02d2148188831bae56
ms.lasthandoff: 02/24/2017

---
# <a name="cmdiframewndex-class"></a>CMDIFrameWndEx 클래스
기능을 확장 [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md), Windows 인터페이스 MDI (다중 문서) 프레임 창입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMDIFrameWndEx : public CMDIFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|현재 항목의 레이아웃을 다시 계산합니다.|  
|`CMDIFrameWndEx::AddDockSite`|이 메서드는 사용 되지 않습니다.|  
|[CMDIFrameWndEx::AddPane](#addpane)|창을 도킹 관리자에 등록합니다.|  
|[CMDIFrameWndEx::AdjustClientArea](#adjustclientarea)|테두리에 대 한 허용 하도록 클라이언트 영역을 줄일 수 있습니다.|  
|[CMDIFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|모든 도킹 된 창 레이아웃을 다시 계산합니다.|  
|[CMDIFrameWndEx::AreMDITabs](#aremditabs)|MDI 탭 기능 또는 MDI 탭 그룹 기능을 사용할지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::CanCovertControlBarToMDIChild](#cancovertcontrolbartomdichild)|탭된 문서 프레임 창 도킹 창 변환할 수 있는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::ControlBarToTabbedDocument](#controlbartotabbeddocument)|지정 된 도킹 창 탭된 문서를 변환합니다.|  
|[CMDIFrameWndEx::CreateDocumentWindow](#createdocumentwindow)|자식 문서 창을 만듭니다.|  
|[CMDIFrameWndEx::CreateNewWindow](#createnewwindow)|새 창을 만들기 위해 프레임 워크에 의해 호출 됩니다.|  
|`CMDIFrameWndEx::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMDIFrameWndEx::DockPane](#dockpane)|지정 된 창 프레임 창에 도킹합니다.|  
|[CMDIFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CMDIFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|수 있도록 자동 숨김 모드 창에 대 한 주 프레임 창에 지정 된 컨트롤이 도킹 된 경우.|  
|[CMDIFrameWndEx::EnableDocking](#enabledocking)|활성화 MDI 프레임 창에 속하는 창을 도킹 합니다.|  
|[CMDIFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|표시 하거나 전체 화면 모드에서 주 메뉴를 숨깁니다.|  
|[CMDIFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|프레임 창에 대 한 전체 화면 모드를 활성화 합니다.|  
|[CMDIFrameWndEx::EnableLoadDockState](#enableloaddockstate)|도킹 상태를 로드 하는 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CMDIFrameWndEx::EnableMDITabbedGroups](#enablemditabbedgroups)|MDI 탭 그룹 기능을 해제 하거나 사용 합니다.|  
|[CMDIFrameWndEx::EnableMDITabs](#enablemditabs)|MDI 탭 기능을 해제 하거나 사용 합니다. 설정, 각 MDI 자식 창에 대 한 탭 프레임 창에 표시 됩니다.|  
|[CMDIFrameWndEx::EnableMDITabsLastActiveActivation](#enablemditabslastactiveactivation)|사용자가 현재 탭을 닫을 때 마지막 활성 탭 활성화 되어야 하는지 여부를 지정 합니다.|  
|[CMDIFrameWndEx::EnablePaneMenu](#enablepanemenu)|사용 하거나 응용 프로그램 창 목록을 표시 하는 팝업 창 메뉴의 자동 생성 및 관리를 사용 하지 않도록 설정 합니다.  입니다.|  
|[CMDIFrameWndEx::EnableWindowsDialog](#enablewindowsdialog)|명령 ID를 호출 하는 메뉴 항목을 삽입 한 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자입니다.|  
|[CMDIFrameWndEx::GetActivePopup](#getactivepopup)|현재 표시된 팝업 메뉴에 대한 포인터를 반환합니다.|  
|[CMDIFrameWndEx::GetPane](#getpane)|지정 된 컨트롤 ID를 가집니다. 창에 대 한 포인터를 반환 합니다.|  
|[CMDIFrameWndEx::GetDefaultResId](#getdefaultresid)|MDI 프레임 창의 공유 리소스의 ID를 반환 합니다.|  
|[CMDIFrameWndEx::GetMDITabGroups](#getmditabgroups)|목록이 MDI 탭 창에 반환 합니다.|  
|[CMDIFrameWndEx::GetMDITabs](#getmditabs)|밑줄이 그어진된 탭된 창에 대 한 참조를 반환합니다.|  
|[CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems](#getmditabscontextmenualloweditems)|MDI 탭 그룹 기능을 사용 하는 경우 상황에 맞는 메뉴 항목을 유효한 결정 하는 플래그의 조합을 반환 합니다.|  
|[CMDIFrameWndEx::GetMenuBar](#getmenubar)|프레임 창에 연결 된 메뉴 모음 개체에 대 한 포인터를 반환 합니다.|  
|[CMDIFrameWndEx::GetRibbonBar](#getribbonbar)|프레임에 대해 리본 표시줄 컨트롤을 검색합니다.|  
|[CMDIFrameWndEx::GetTearOffBars](#gettearoffbars)|목록을 반환 [CPane](../../mfc/reference/cpane-class.md)-분리 상태에 있는 개체를 파생 합니다.|  
|`CMDIFrameWndEx::GetThisClass`|에 대 한 포인터를 얻으려면 프레임 워크에서 호출 된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMDIFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|응용 프로그램 도구 모음 단추에 대 한 도구 설명을 표시 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CMDIFrameWndEx::InsertPane](#insertpane)|지정 된 창 도킹 관리자에 등록합니다.|  
|[CMDIFrameWndEx::IsFullScreen](#isfullscreen)|프레임 창을 전체 화면 모드 인지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::IsMDITabbedGroup](#ismditabbedgroup)|MDI 탭 그룹 기능을 사용할지 결정 합니다.|  
|[CMDIFrameWndEx::IsMemberOfMDITabGroup](#ismemberofmditabgroup)|Windows MDI 탭 그룹에 있는 목록에 지정 된 탭된 창 인지 확인 합니다.|  
|[CMDIFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|프레임 창 메뉴 모음에 있는지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|도킹 사이트 근처에 지정된 된 지점 인지 확인 합니다.|  
|[CMDIFrameWndEx::IsPrintPreview](#isprintpreview)|프레임 창 인쇄 미리 보기 모드 인지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::LoadFrame](#loadframe)|리소스 정보에서 프레임 창을 만듭니다. (`CMDIFrameWnd::LoadFrame`를 재정의합니다.)|  
|[Cmdiframewndex:: Loadmdistate](#loadmdistate)|MDI 탭 그룹의 지정 된 레이아웃 및 이전에 연된 문서 목록을 로드합니다.|  
|[CMDIFrameWndEx::MDITabMoveToNextGroup](#mditabmovetonextgroup)|현재 활성 탭된 창에서 활성 탭 다음 또는 이전 탭된 그룹으로 이동 합니다.|  
|[CMDIFrameWndEx::MDITabNewGroup](#mditabnewgroup)|단일 창에 새 탭된 그룹을 만듭니다.|  
|[CMDIFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|OLE 위치에서 활성화 하는 동안 테두리 프레임 창에는 공간을 협상합니다.|  
|[CMDIFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 도킹 가능한 창에서 단추입니다.|  
|[CMDIFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 부동 미니 프레임 창의 단추를 합니다.|  
|[CMDIFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|활성 팝업 메뉴를 처리할 때 프레임 워크에 의해 호출 된 `WM_DESTROY` 메시지입니다.|  
|[CMDIFrameWndEx::OnCmdMsg](#oncmdmsg)|라우팅하고 명령 메시지를 발송 하 고 명령 사용자 인터페이스 개체를 업데이트 하려면 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|메뉴 항목과 연결된 이미지를 그릴 때 프레임워크에서 호출됩니다.|  
|[CMDIFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|프레임 워크 호출 때는 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)프로세스는 `WM_PAINT` 메시지입니다.|  
|[CMDIFrameWndEx::OnEraseMDIClientBackground](#onerasemdiclientbackground)|MDI 프레임 창 프로세스 때 프레임 워크에 의해 호출 된 `WM_ERASEBKGND` 메시지입니다.|  
|[CMDIFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|프레임 워크 호출 때는 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)프로세스 개체를 `WM_NCHITTEST` 메시지입니다.|  
|[CMDIFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|미니 프레임 창을 이동 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|응용 프로그램의 주 프레임 창 인쇄 미리 보기 모드를 설정합니다. (재정의 [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode).)|  
|[CMDIFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|빠른 사용자 지정 창이 활성화 될 때 프레임 워크에서 호출 합니다.|  
|[CMDIFrameWndEx::OnShowMDITabContextMenu](#onshowmditabcontextmenu)|상황에 맞는 메뉴 탭 중 하나에 표시 될 때 프레임 워크에서 호출 합니다. (유효만 MDI 탭 그룹에 대 한.)|  
|[CMDIFrameWndEx::OnShowPanes](#onshowpanes)|표시 하거나 숨기려면 창 프레임 워크에 의해 호출 됩니다.|  
|[CMDIFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|팝업 메뉴가 활성화될 때 프레임워크에서 호출됩니다.|  
|[CMDIFrameWndEx::OnSizeMDIClient](#onsizemdiclient)|클라이언트 MDI 창의 크기를 변경할 때에 프레임 워크에서 호출 합니다.|  
|[CMDIFrameWndEx::OnTearOffMenu](#ontearoffmenu)|분리 막대가 있는 메뉴가 활성화될 때 프레임워크에서 호출됩니다.|  
|[CMDIFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|프레임 워크는 프레임 메뉴 업데이트에 의해 호출 됩니다. (`CMDIFrameWnd::OnUpdateFrameMenu`를 재정의합니다.)|  
|[CMDIFrameWndEx::PaneFromPoint](#panefrompoint)|지정 된 위치를 포함 하는 도킹 창을 반환 합니다.|  
|`CMDIFrameWndEx::PreTranslateMessage`|클래스에서 사용 하는 [CWinApp](../../mfc/reference/cwinapp-class.md) 으로 디스패치 되기 전에 창 메시지를 변환 하는 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다.  (`CMDIFrameWnd::PreTranslateMessage`를 재정의합니다.)|  
|[CMDIFrameWndEx::RecalcLayout](#recalclayout)|프레임 창의 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다. (재정의 [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout).)|  
|[CMDIFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 등록을 취소 하 고 도킹 관리자에서 제거 합니다.|  
|[CMDIFrameWndEx::SaveMDIState](#savemdistate)|MDI 탭 그룹의 현재 레이아웃 및 이전에 연된 문서 목록을 저장합니다.|  
|[CMDIFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|인쇄 미리 보기 프레임 창을 설정입니다.|  
|[CMDIFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|더미 항목을 검색하고 지정된 사용자 정의 항목으로 대체하여 도구 모음 개체를 수정합니다.|  
|[CMDIFrameWndEx::ShowFullScreen](#showfullscreen)|전체 화면 모드로 일반 모드에서 주 프레임을 전환합니다.|  
|[CMDIFrameWndEx::ShowPane](#showpane)|표시 하거나 지정한 창을 숨깁니다.|  
|[CMDIFrameWndEx::ShowWindowsDialog](#showwindowsdialog)|만듭니다는 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 상자를 엽니다.|  
|[CMDIFrameWndEx::TabbedDocumentToControlBar](#tabbeddocumenttocontrolbar)|도킹 창에 지정 된 탭된 문서를 변환합니다.|  
|[CMDIFrameWndEx::UpdateCaption](#updatecaption)|창 프레임 캡션을 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIFrameWndEx::UpdateMDITabbedBarsIcons](#updatemditabbedbarsicons)|각 MDI 탭된 창에 대 한 아이콘을 설정합니다.|  
|[CMDIFrameWndEx::WinHelp](#winhelp)|WinHelp 응용 프로그램 또는 상황에 맞는 도움말을 시작하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::WinHelp](../../mfc/reference/cwnd-class.md#winhelp).)|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild](#m_bcancovertcontrolbartomdichild)|도킹 창 MDI 자식 창을 변환할 수 있는지 여부를 결정 합니다.|  
|[CMDIFrameWndEx::m_bDisableSetRedraw](#m_bdisablesetredraw)|MDI 자식 창에 대 한 다시 그리기 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.|  
  
## <a name="remarks"></a>주의  
 를 이용 하려면 사용자 지정 확장된 기능의 MDI 응용 프로그램에 응용 프로그램의 MDI 프레임 창 클래스를 파생 `CMDIFrameWndEx` 대신 `CMDIFrameWnd`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 파생 클래스에서 `CMDIFrameWndEx`합니다. 이 코드 조각에서 제공 되는 [DrawClient 샘플: MFC Ribbon-Based OLE 개체 그리기 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DrawClient #&1;](../../mfc/reference/codesnippet/cpp/cmdiframewndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)  
  
 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxMDIFrameWndEx.h  
  
##  <a name="a-nameactiveitemrecalclayouta--cmdiframewndexactiveitemrecalclayout"></a><a name="activeitemrecalclayout"></a>CMDIFrameWndEx::ActiveItemRecalcLayout  
 현재 항목의 레이아웃을 다시 계산합니다.  
  
```  
void ActiveItemRecalcLayout();
```  
  
##  <a name="a-nameaddpanea--cmdiframewndexaddpane"></a><a name="addpane"></a>CMDIFrameWndEx::AddPane  
 창을 도킹 관리자에 등록합니다.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 등록 하 고 창에 대 한 포인터입니다.  
  
 [in] `bTail`  
 이 창 목록의 끝에 추가할 것인지 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 창에서 성공적으로 등록 하는 경우&0;이 아닌 값을 반환 합니다. 창 도킹 관리자와 이미 등록 되어 있으면 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 각 창에 등록 해야는 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 전에 도킹 레이아웃의 일부로 걸릴 수 있습니다. 이 메서드를 사용 하 여 특정 창을 도킹 하려면 도킹 관리자에 게 알립니다. 해당 창 등록 되 면 정렬 설정 및 도킹 관리자에서 유지 관리 하는 창의 목록에서 위치에 따라 도킹 관리자 정렬 합니다.  
  
##  <a name="a-nameadjustclientareaa--cmdiframewndexadjustclientarea"></a><a name="adjustclientarea"></a>CMDIFrameWndEx::AdjustClientArea  
 테두리에 대 한 허용 하도록 클라이언트 영역을 줄일 수 있습니다.  
  
```  
virtual void AdjustClientArea();
```  
  
##  <a name="a-nameadjustdockinglayouta--cmdiframewndexadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CMDIFrameWndEx::AdjustDockingLayout  
 모든 도킹 된 창 레이아웃을 다시 계산합니다.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hdwp`  
 다중 창 위치 구조를 식별합니다. 호출 하 여이 값을 구할 수 `BeginDeferWindowPos`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 창에 도킹 하는 모든 창 레이아웃을 다시 계산 하려면이 멤버 함수를 호출 합니다.  
  
##  <a name="a-namearemditabsa--cmdiframewndexaremditabs"></a><a name="aremditabs"></a>CMDIFrameWndEx::AreMDITabs  
 MDI 탭 기능 또는 MDI 탭된 그룹 기능을 사용할지 여부를 결정 합니다.  
  
```  
BOOL AreMDITabs(int* pnMDITabsType=NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `pnMDITabsType`  
 포인터는 기능을 사용할 수를 나타내는 정수 변수입니다.  
  
-   0: 모든 기능이 사용 되지 않습니다.  
  
-   1: MDI 탭 사용 하도록 설정 합니다.  
  
-   2: MDI 탭 그룹을 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `Returns TRUE`MDI 탭 또는 MDI 탭 그룹 사용 됩니다.  
  
 `Returns FALSE`위의 기능을 사용 가능한 합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 MDI 탭 또는 MDI 탭 그룹 있는지 여부를 확인 하려면이 함수를 사용할 수 있습니다. 프레임 창의 경우. 사용 하 여 [CMDIFrameWndEx::EnableMDITabs](#enablemditabs) MDI 탭 기능을 사용 하도록 설정 하거나 해제 합니다.  
  
 사용 하 여 [CMDIFrameWndEx::EnableMDITabbedGroups](#enablemditabbedgroups) MDI 탭된 그룹 기능을 사용할지 여부를 합니다.  
  
##  <a name="a-namecancovertcontrolbartomdichilda--cmdiframewndexcancovertcontrolbartomdichild"></a><a name="cancovertcontrolbartomdichild"></a>CMDIFrameWndEx::CanCovertControlBarToMDIChild  
 탭된 문서 프레임 창 도킹 창 변환할 수 있는지 여부를 결정 하는 프레임 워크에서 호출  
  
```  
virtual BOOL CanCovertControlBarToMDIChild();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 프레임 창은 탭된 문서; 도킹 창 변환할 수 있으면 그렇지 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 파생된 클래스에서이 메서드를 재정의 하 고 반환 `TRUE` 변환 탭 문서로 도킹 창도 사용할 수 있도록 합니다. 설정할 수 있습니다 [CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild](#m_bcancovertcontrolbartomdichild) 를 `TRUE`합니다.  
  
##  <a name="a-namecontrolbartotabbeddocumenta--cmdiframewndexcontrolbartotabbeddocument"></a><a name="controlbartotabbeddocument"></a>CMDIFrameWndEx::ControlBarToTabbedDocument  
 지정 된 도킹 창 탭된 문서를 변환합니다.  
  
```  
virtual CMDIChildWndEx* ControlBarToTabbedDocument(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBar`  
 변환할 도킹 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 도킹 창이 포함 된 새 MDI 자식 창에 대 한 포인터를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 도킹 창 탭된 문서를 변환합니다. 이 메서드를 호출 하면 프레임 워크를 만들고는 [CMDIChildWndEx 클래스](../../mfc/reference/cmdichildwndex-class.md) 개체 도킹 창 도킹 관리자에서 제거 및 새 MDI 자식 창으로 도킹 창에 추가 합니다. MDI 자식 창에 전체 클라이언트 영역에 도킹 창 크기 조정  
  
##  <a name="a-namecreatedocumentwindowa--cmdiframewndexcreatedocumentwindow"></a><a name="createdocumentwindow"></a>CMDIFrameWndEx::CreateDocumentWindow  
 자식 문서 창을 만듭니다.  
  
```  
virtual CMDIChildWndEx* CreateDocumentWindow(
    LPCTSTR lpcszDocName,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpcszDocName`  
 문서 식별자가 포함 된 텍스트 문자열입니다. 일반적으로 문서 파일의 전체 경로 것입니다.  
  
 [in] `pObj`  
 사용자 정의 개체에 대 한 포인터입니다. 예를 들어 한 개발자 문서를 설명 하 고 시작 시 문서를 초기화 하는 방법을 지시 하는 응용 프로그램별 데이터 구조를 만들 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터 `CMDIChildWndEx`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 이전에 레지스트리에 저장 된 문서의 목록을 로드 하는 경우이 메서드를 호출 합니다.  
  
 레지스트리에서 로드 되는 경우 문서를 만들기 위해이 메서드를 재정의 합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `CreateDocumentWindow` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 이 예제에서는 `g_strStartViewName` "가상 문서" (예: "시작 페이지")는 디스크 파일에서 실제로 로드 되지 않는 이름일 수 있습니다. 따라서 해당 사례를 처리 하는 특별 한 처리 해야 합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&13;](../../mfc/codesnippet/cpp/cmdiframewndex-class_2.cpp)]  
  
##  <a name="a-namecreatenewwindowa--cmdiframewndexcreatenewwindow"></a><a name="createnewwindow"></a>CMDIFrameWndEx::CreateNewWindow  
 새 창을 만들기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual CMDIChildWndEx* CreateNewWindow(
    LPCTSTR lpcszDocName,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpcszDocName`  
 문서 이름입니다.  
  
 [in] `pObj`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 새 창에 대 한 포인터입니다.  
  
##  <a name="a-namedockpanea--cmdiframewndexdockpane"></a><a name="dockpane"></a>CMDIFrameWndEx::DockPane  
 지정 된 창 프레임 창에 도킹합니다.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 도킹 창에 대 한 포인터입니다.  
  
 [in] `nDockBarID`  
 프레임 창에 도킹 될 면을 지정 합니다.  
  
 [in] `lpRect`  
 사용되지 않습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정 된 도킹 된 프레임 창의 측면 중 하나에 있는 창 때 지정 된 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) 및 [CMDIFrameWndEx::EnableDocking](#enabledocking) 호출 된 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 `DockPane` 메서드를 사용하는 방법을 보여 줍니다. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&4;](../../mfc/codesnippet/cpp/cmdiframewndex-class_3.cpp)]  
  
##  <a name="a-namedockpaneleftofa--cmdiframewndexdockpaneleftof"></a><a name="dockpaneleftof"></a>CMDIFrameWndEx::DockPaneLeftOf  
 창을 다른 창의 왼쪽에 도킹합니다.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 도킹 창에 대 한 포인터입니다.  
  
 [in] `pLeftOf`  
 도킹 사이트로 사용 되는 창에 대 한 포인터입니다. 입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 작업이 성공한 경우. 그렇지 않으면 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 미리 정의 된 순서에 여러 가지 창에서 개체를 고정 하려면이 메서드를 호출 합니다. 이 메서드는 지정 된 창 도킹 `pBar` 로 지정 된 창 왼쪽에 `pLeftOf`합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 방법을 `DockPaneLeftOf` 방법을 사용는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&5;](../../mfc/codesnippet/cpp/cmdiframewndex-class_4.cpp)]  
  
##  <a name="a-nameenableautohidepanesa--cmdiframewndexenableautohidepanes"></a><a name="enableautohidepanes"></a>CMDIFrameWndEx::EnableAutoHidePanes  
 수 있도록 자동 숨김 모드 창에 대 한 지정 된 주 프레임 창 옆쪽에 컨트롤이 도킹 된 경우.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwDockStyle`  
 사용할 수 있는 주 프레임 창의 측면을 지정 합니다. 다음 플래그 중 하나 이상을 사용 합니다.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>반환 값  
 모드를 사용 하도록 자동 숨기기 창에 대 한 지정 된 주 프레임 창 옆쪽에 컨트롤이 도킹 된 경우이 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 방법을 `EnableAutoHidePanes` 방법을 사용는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&6;](../../mfc/codesnippet/cpp/cmdiframewndex-class_5.cpp)]  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameenabledockinga--cmdiframewndexenabledocking"></a><a name="enabledocking"></a>CMDIFrameWndEx::EnableDocking  
 활성화 MDI 프레임 창에 속하는 창을 도킹 합니다.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwDockStyle`  
 적용 하려는 도킹 스타일을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
 에 속한 창의 도킹을 사용 하도록 설정 하려면이 함수를 호출 하는 `CMDIFrameWndEx` 개체입니다.  
  
### <a name="example"></a>예제  
 다음 예제와 방법을 `EnableDocking` 방법을 사용는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&7;](../../mfc/codesnippet/cpp/cmdiframewndex-class_6.cpp)]  
  
##  <a name="a-nameenablefullscreenmainmenua--cmdiframewndexenablefullscreenmainmenu"></a><a name="enablefullscreenmainmenu"></a>CMDIFrameWndEx::EnableFullScreenMainMenu  
 표시 하거나 전체 화면 모드에서 주 메뉴를 숨깁니다.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnableMenu`  
 `TRUE`전체 화면 모드에서 주 메뉴를 표시 하려면 또는 `FALSE` 을 숨깁니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameenablefullscreenmodea--cmdiframewndexenablefullscreenmode"></a><a name="enablefullscreenmode"></a>CMDIFrameWndEx::EnableFullScreenMode  
 프레임 창에 대 한 전체 화면 모드를 활성화 합니다.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiFullScreenCmd`  
 ID를 설정 하거나 전체 화면 모드를 해제 하는 명령입니다.  
  
### <a name="remarks"></a>주의  
 전체 화면 모드에서는 모든 도킹 컨트롤 막대, 도구 모음과 메뉴는 숨겨져 있으며, 활성 뷰가 전체 화면을 차지 하도록 크기가 조정 됩니다. 전체 화면 모드를 사용 하도록 설정 하거나 해제 하는 명령 ID를 지정 해야 합니다. 호출할 수 있습니다 `EnableFullScreenMode` 주 프레임에서 `OnCreate` 함수입니다. 프레임 워크는 지정 된 명령 ID를 가진 하나의 단추가 있는 부동 도구 모음을 만들고 프레임 창을 전체 화면 모드로 전환 되는 경우 화면에서 주 메뉴를 유지 하려는 경우에 호출 [CMDIFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)합니다.  
  
##  <a name="a-nameenableloaddockstatea--cmdiframewndexenableloaddockstate"></a><a name="enableloaddockstate"></a>CMDIFrameWndEx::EnableLoadDockState  
 도킹 상태를 로드 하는 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableLoadDockState(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`도킹 상태 로드를 사용 하려면 `FALSE` 도킹 상태를 로드 하는 사용 하지 않으려면 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameenablemditabbedgroupsa--cmdiframewndexenablemditabbedgroups"></a><a name="enablemditabbedgroups"></a>CMDIFrameWndEx::EnableMDITabbedGroups  
 프레임 창에 대해 MDI 탭된 그룹 기능을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableMDITabbedGroups(
    BOOL bEnable,  
    const CMDITabInfo& params);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 경우 `TRUE`, MDI 탭된 그룹 기능 활성화 되는 경우 `FALSE`, MDI 탭된 그룹 기능을 비활성화 합니다.  
  
 [in] `params`  
 프레임 워크 서 MDI 클라이언트 영역에서 만든 자식 창에 적용 되는 매개 변수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 MDI 탭된 그룹 기능을 사용할지 여부를이 메서드를 사용 합니다. 이 기능을 통해 MDI 응용 프로그램 세로로 정렬 된 탭된 창으로 또는 MDI 클라이언트 영역 내에서 가로로 자식 창을 표시할 수 있습니다. 탭 창의 그룹은 분할자로 구분됩니다. 사용자는 분할자를 사용 하 여 탭된 그룹의 크기를 조정할 수 있습니다.  
  
-   사용자는 다음 작업을 수행할 수 있습니다.  
  
-   그룹 간에 개별 탭을 끕니다.  
  
-   새 그룹을 만들 창의 가장자리를 개별 탭을 끕니다.  
  
-   탭 이동 또는 바로 가기 메뉴를 사용 하 여 새 그룹을 만듭니다.  
  
-   응용 프로그램 탭된 창의 현재 레이아웃 및 현재 열려 있는 문서의 목록을 저장할 수 있습니다.  
  
 이 메서드를 호출 하는 경우 `bEnable` 로 설정 `FALSE`, `params` 는 무시 됩니다.  
  
 MDI 탭 그룹은 이미 사용 하는 경우에 다시 자식 창에 대 한 설정을 수정 하려면이 메서드를 호출할 수 있습니다. 이 메서드를 호출할 `bEnable` 로 설정 `TRUE` 의 멤버를 수정 하 고는 `CMDITabInfo` 으로 지정 된 개체는 `params` 매개 변수입니다.  
  
 탭 그룹을 MDI를 사용 하는 방법에 대 한 자세한 내용은 참조 [MDI 탭 그룹](../../mfc/mdi-tabbed-groups.md)합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `EnableMDITabbedGroups` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&8;](../../mfc/codesnippet/cpp/cmdiframewndex-class_7.cpp)]  
  
##  <a name="a-nameenablemditabsa--cmdiframewndexenablemditabs"></a><a name="enablemditabs"></a>CMDIFrameWndEx::EnableMDITabs  
 MDI 프레임 창에 대해 MDI 탭 기능을 해제 하거나 사용 합니다. 설정, 각 MDI 자식 창에 대 한 탭 프레임 창에 표시 됩니다.  
  
```  
void EnableMDITabs(
    BOOL bEnable=TRUE,  
    BOOL bIcons=TRUE,  
    CMFCTabCtrl::Location tabLocation=CMFCTabCtrl::LOCATION_BOTTOM,  
    BOOL bTabCloseButton=FALSE,  
    CMFCTabCtrl::Style style=CMFCTabCtrl::STYLE_3D_SCROLLED,  
    BOOL bTabCustomTooltips=FALSE,  
    BOOL bActiveTabCloseButton=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 탭 사용 되는지 여부를 지정 합니다.  
  
 `bIcons`  
 아이콘을 탭에 표시할지 여부를 지정 합니다.  
  
 `tabLocation`  
 탭 레이블의 위치를 지정합니다.  
  
 `bTabCloseButton`  
 탭 닫기 단추를 표시할지 여부를 지정 합니다.  
  
 `style`  
 탭의 스타일을 지정합니다. 사용 하 여 `STYLE_3D_SCROLLED` 일반 탭에 대 한 또는 `STYLE_3D_ONENOTE` Microsoft OneNote 탭 합니다.  
  
 `bTabCustomTooltips`  
 사용자 지정 도구 설명을 사용 되는지 여부를 지정 합니다.  
  
 `bActiveTabCloseButton`  
 경우 `TRUE`, **닫기** 단추 대신 탭 영역의 오른쪽 모서리에서 활성 탭에 표시 됩니다.  
  
### <a name="remarks"></a>주의  
 MDI 프레임 창에 대해 MDI 탭 기능을 사용 하지 않도록 설정 하거나 사용 하려면이 메서드를 호출 합니다. 사용 하도록 설정 하면 모든 자식 창은 탭으로 표시 됩니다.  
  
 탭 레이블의 맨 위 또는 매개 변수 설정에 따라 프레임의 아래쪽에 위치할 수 `tabLocation`합니다. 지정할 수 있습니다 `CMFCTabCtrl::LOCATION_BOTTOM` (기본 설정) 또는 `CMFCTabCtrl::LOCATION_TOP`합니다.  
  
 경우 `bTabCustomTooltips` 는 `TRUE`, `AFX_WM_ON_GET_TAB_TOOLTIP` 주 프레임 창으로 전송 됩니다. 코드는이 메시지를 처리 하 고 MDI 탭에 대 한 사용자 지정 도구와 프레임 워크를 제공 수 있습니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `EnableMDITabs` 에 사용 되는 [MDITabsDemo 샘플: MFC 탭 MDI 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MDITabsDemo #&3;](../../mfc/reference/codesnippet/cpp/cmdiframewndex-class_8.cpp)]  
  
##  <a name="a-nameenablemditabslastactiveactivationa--cmdiframewndexenablemditabslastactiveactivation"></a><a name="enablemditabslastactiveactivation"></a>CMDIFrameWndEx::EnableMDITabsLastActiveActivation  
 사용자가 현재 탭을 닫을 때 마지막 활성 탭 열 수 있는지 여부를 지정 합니다.  
  
```  
void EnableMDITabsLastActiveActivation(BOOL bLastActiveTab=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bLastActiveTab`  
 경우 `TRUE`, 마지막 활성 탭을 활성화 합니다. 경우 `FALSE`, 마지막 활성 탭의 정품 인증을 사용 하지 않도록 설정 합니다.  
  
### <a name="remarks"></a>주의  
 두 가지 방법으로 활성 탭 닫힐 때 한 탭을 엽니다.  
  
-   다음 탭을 활성화 합니다.  
  
-   이전 활성 탭을 활성화 합니다.  
  
 기본 구현에서는 첫 번째 방법은 사용합니다.  
  
 사용 하 여 `EnableMDITabsLastActiveActivation` 탭 정품 인증의 두 번째 방법은 사용할 수 있도록 합니다. 창을 열면 MDI 자식 창의 방식의 에뮬레이션 합니다.  
  
##  <a name="a-nameenablepanemenua--cmdiframewndexenablepanemenu"></a><a name="enablepanemenu"></a>CMDIFrameWndEx::EnablePaneMenu  
 사용 하거나 응용 프로그램 창 목록을 표시 하는 팝업 창 메뉴의 자동 생성 및 관리를 사용 하지 않도록 설정 합니다.  
  
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
 경우 `TRUE`, 창 메뉴의 자동 처리 사용 되는 경우 `FALSE`, 자동 처리를 사용 하지 않도록 설정 합니다.  
  
 [in] `uiCustomizeCmd`  
 명령 ID를는 **사용자 지정** 메뉴 항목입니다. 이 메뉴 항목은 일반적으로 창의 목록 끝에 추가 됩니다.  
  
 [in] `strCustomizeLabel`  
 에 대해 표시할 텍스트는 **사용자 지정** 는 메뉴 항목 (지역화).  
  
 [in] `uiViewToolbarsMenuEntryID`  
 창 메뉴를 열고 도구 모음 메뉴 항목의 ID를 지정 합니다. 이 일반적으로 **도구 모음** 의 하위 메뉴는 **보기** 메뉴.  
  
 [in] `bContextMenuShowsToolbarsOnly`  
 경우 `TRUE`, 창 메뉴에는 도구 모음 목록만 표시 됩니다. 경우 `FALSE`, 메뉴 도구 모음 및 도킹 모음 목록이 표시 됩니다.  
  
 [in] `bViewMenuShowsToolbarsOnly`  
 경우 `TRUE`, 창 메뉴에는 도구 모음 목록만 표시 됩니다. 경우 `FALSE`, 메뉴 도구 모음 및 도킹 모음 목록이 표시 됩니다.  
  
### <a name="remarks"></a>주의  
 팝업 창 메뉴 응용 프로그램의 창 목록을 표시 하 고 사용자가 표시 하거나 개별 창을 숨길 수 있습니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `EnablePaneMenu` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&9;](../../mfc/codesnippet/cpp/cmdiframewndex-class_9.cpp)]  
  
##  <a name="a-nameenablewindowsdialoga--cmdiframewndexenablewindowsdialog"></a><a name="enablewindowsdialog"></a>CMDIFrameWndEx::EnableWindowsDialog  
 명령 ID를 호출 하는 메뉴 항목을 삽입 한 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자입니다.  
  
```  
void EnableWindowsDialog(
    UINT uiMenuId,  
    LPCTSTR lpszMenuText,  
    BOOL bShowAllways=FALSE,  
    BOOL bShowHelpButton=FALSE);

 
void EnableWindowsDialog(
    UINT uiMenuId,  
    UINT uiMenuTextResId,  
    BOOL bShowAllways=FALSE,  
    BOOL bShowHelpButton=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiMenuId`  
 메뉴의 리소스 ID를 지정합니다.  
  
 [in] `lpszMenuText`  
 항목의 텍스트를 지정합니다.  
  
 [in] `bShowHelpButton`  
 표시 여부를 지정 된 **도움말** windows 관리 대화 상자에서 단추입니다.  
  
 [in] `uiMenuTextResId`  
 항목의 텍스트 문자열이 포함 된 문자열 리소스 식별자입니다.  
  
### <a name="remarks"></a>주의  
 해당 명령은 MDI 자식 창 관리 대화 상자를 호출 하 여 메뉴 항목을 삽입 하려면이 메서드를 사용 하 여 ( [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)). 지정 된 메뉴에 새 항목이 삽입 된 `uiMenuId`합니다. 호출 `EnableWindowsDialog` 처리 하는 경우는 `WM_CREATE` 메시지입니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `EnableWindowsDialog` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&10;](../../mfc/codesnippet/cpp/cmdiframewndex-class_10.cpp)]  
  
##  <a name="a-namegetactivepopupa--cmdiframewndexgetactivepopup"></a><a name="getactivepopup"></a>CMDIFrameWndEx::GetActivePopup  
 현재 표시된 팝업 메뉴에 대한 포인터를 반환합니다.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 활성 팝업 메뉴;에 대 한 포인터 `NULL` 팝업 메뉴가 나타나지 실행 중인 경우.  
  
### <a name="remarks"></a>주의  
 에 대 한 포인터를 가져오려면이 함수를 사용 여 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 현재 표시 되는 개체입니다.  
  
##  <a name="a-namegetdefaultresida--cmdiframewndexgetdefaultresid"></a><a name="getdefaultresid"></a>CMDIFrameWndEx::GetDefaultResId  
 MDI 프레임 창의 공유 리소스의 ID를 반환 합니다.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리소스 ID 값입니다. 프레임 창에 메뉴 모음에 없는 경우&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 하 여 MDI 프레임 창은 로드 될 때 지정 된 리소스 ID [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)합니다.  
  
##  <a name="a-namegetmditabgroupsa--cmdiframewndexgetmditabgroups"></a><a name="getmditabgroups"></a>CMDIFrameWndEx::GetMDITabGroups  
 목록이 MDI 탭 창에 반환 합니다.  
  
```  
const CObList& GetMDITabGroups() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 [CObList 클래스](../../mfc/reference/coblist-class.md) 탭 창 목록을 포함 하는 개체입니다. 목록을 수정 하거나 저장 하지 마십시오.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 탭 창 목록에 액세스 합니다. 변경 하거나 개별 탭 창 일부 매개 변수를 쿼리 하려는 경우 유용할 수 있습니다.  
  
##  <a name="a-namegetmditabsa--cmdiframewndexgetmditabs"></a><a name="getmditabs"></a>CMDIFrameWndEx::GetMDITabs  
 밑줄이 그어진된 탭된 창에 대 한 참조를 반환합니다.  
  
```  
CMFCTabCtrl& GetMDITabs();
```  
  
### <a name="return-value"></a>반환 값  
 밑줄이 그어진된 탭된 창에 대 한 참조입니다.  
  
##  <a name="a-namegetmditabscontextmenualloweditemsa--cmdiframewndexgetmditabscontextmenualloweditems"></a><a name="getmditabscontextmenualloweditems"></a>CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems  
 어떤 작업은 MDI 탭 그룹 기능을 사용 하는 경우를 결정 하는 플래그의 조합을 반환 합니다.  
  
```  
DWORD GetMDITabsContextMenuAllowedItems();
```  
  
### <a name="return-value"></a>반환 값  
 다음 플래그의 비트 OR 조합입니다.  
  
- `BCGP_MDI_CREATE_VERT_GROUP`-세로 탭 그룹을 만들 수 있습니다.  
  
- `BCGP_MDI_CREATE_HORZ_GROUP`-가로 탭 그룹을 만들 수 있습니다.  
  
- `BCGP_MDI_CAN_MOVE_PREV`-이전 탭 그룹에 탭을 이동할 수 있습니다.  
  
- `BCGP_MDI_CAN_MOVE_NEXT`-다음 탭 그룹에 탭을 이동할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 MDI 탭 그룹 기능을 사용 하는 경우 특정 창 탭에서 허용 하는 작업 하는 것이 알아야 합니다. 이 메서드는 현재 탭된 창의 레이아웃을 분석 하 고 될 수 있는 플래그의 조합을 만드는 데, 예를 들어, 바로 가기 메뉴를 반환 합니다.  
  
 모든 탭된 창을 세로로 맞춰 지 면 또는 하나의 탭된 창 경우 세로 탭 그룹을 만들 수 있습니다.  
  
 모든 탭된 창을 가로로 정렬 되어 또는 탭된 창이 하나만 있으면 새 가로 탭 그룹을 만들 수 있습니다.  
  
 탭된 창에 둘 이상의 탭이 있는 경우에 이전 그룹에 탭을 이동할 수 있습니다.  
  
 탭된 창에 둘 이상의 탭이 있는 경우에 다음 그룹에 탭을 이동할 수 있습니다.  
  
##  <a name="a-namegetmenubara--cmdiframewndexgetmenubar"></a><a name="getmenubar"></a>CMDIFrameWndEx::GetMenuBar  
 프레임 창에 연결 된 메뉴 모음 개체에 대 한 포인터를 반환 합니다.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 모음 개체에 대 한 포인터입니다.  
  
##  <a name="a-namegetpanea--cmdiframewndexgetpane"></a><a name="getpane"></a>CMDIFrameWndEx::GetPane  
 지정 된 컨트롤 ID를 가집니다. 창에 대 한 포인터를 반환 합니다.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 컨트롤 id입니다.  
  
### <a name="return-value"></a>반환 값  
 에 지정 된 컨트롤 ID가 있는 경우 창에 대 한 포인터입니다. 그렇지 않으면 `NULL`입니다.  
  
##  <a name="a-namegetribbonbara--cmdiframewndexgetribbonbar"></a><a name="getribbonbar"></a>CMDIFrameWndEx::GetRibbonBar  
 프레임에 대해 리본 표시줄 컨트롤을 검색합니다.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md) 프레임입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettearoffbarsa--cmdiframewndexgettearoffbars"></a><a name="gettearoffbars"></a>CMDIFrameWndEx::GetTearOffBars  
 분리 메뉴의 목록을 반환합니다.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 [CObList 클래스](../../mfc/reference/coblist-class.md) 개체에 대 한 포인터의 컬렉션을 포함 하는 `CPane`-분리 상태에 있는 개체를 파생 합니다.  
  
### <a name="remarks"></a>주의  
 `CMDIFrameWndEx`분리 메뉴의 컬렉션을 유지 합니다. 이 메서드를 사용 하 여이 목록에 대 한 참조를 검색 합니다.  
  
##  <a name="a-namegettoolbarbuttontooltiptexta--cmdiframewndexgettoolbarbuttontooltiptext"></a><a name="gettoolbarbuttontooltiptext"></a>CMDIFrameWndEx::GetToolbarButtonToolTipText  
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
  
##  <a name="a-nameinsertpanea--cmdiframewndexinsertpane"></a><a name="insertpane"></a>CMDIFrameWndEx::InsertPane  
 지정 된 창 도킹 관리자에 등록합니다.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 삽입할 창에 대 한 포인터입니다.  
  
 [in] `pTarget`  
 앞 이나 뒤에 창에서 삽입 되는 창에 대 한 포인터입니다.  
  
 [in] `bAfter`  
 경우 `TRUE`, `pControlBar` 뒤에 삽입 되어 `pTarget`합니다. 경우 `FALSE`, `pControlBar` 앞에 삽입 된 `pTarget`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 메서드를 성공적으로 등록 하는 경우 `FALSE` 창 도킹 관리자와 이미 등록 된 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 도킹 관리자에 의해 지정 된 창에 대 한 정보를 `pControlBar`합니다. 도킹 관리자는이 창 고 창 정렬 및 도킹 하는 관리자의 내부 목록에서 위치에 따라 정렬 됩니다.  
  
##  <a name="a-nameisfullscreena--cmdiframewndexisfullscreen"></a><a name="isfullscreen"></a>CMDIFrameWndEx::IsFullScreen  
 프레임 창을 전체 화면 모드 인지 여부를 결정 합니다.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 창을 전체 화면 모드에 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 호출 하 여 전체 화면 모드를 설정할 수는 [CMDIFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) 메서드.  
  
##  <a name="a-nameismditabbedgroupa--cmdiframewndexismditabbedgroup"></a><a name="ismditabbedgroup"></a>CMDIFrameWndEx::IsMDITabbedGroup  
 MDI 탭 그룹 기능을 사용할 것인지를 지정 합니다.  
  
```  
BOOL IsMDITabbedGroup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`MDI 탭 그룹 기능을 사용 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 일반 MDI 탭 또는 MDI 탭 그룹 기능을 사용할지 여부를 확인 하려면 [CMDIFrameWndEx::AreMDITabs](#aremditabs)합니다.  
  
##  <a name="a-nameismemberofmditabgroupa--cmdiframewndexismemberofmditabgroup"></a><a name="ismemberofmditabgroup"></a>CMDIFrameWndEx::IsMemberOfMDITabGroup  
 Windows MDI 탭 그룹에 있는 목록에 지정 된 탭된 창 인지 확인 합니다.  
  
```  
BOOL IsMemberOfMDITabGroup(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 탭된 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 있는 경우 지정 된 탭 MDI 탭 그룹을 형성 하는 탭 창 목록에 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameismenubaravailablea--cmdiframewndexismenubaravailable"></a><a name="ismenubaravailable"></a>CMDIFrameWndEx::IsMenuBarAvailable  
 프레임 창 메뉴 모음에 있는지 여부를 결정 합니다.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메뉴 모음 개체에 대 한 포인터 없으면 `NULL`고, 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameispointneardocksitea--cmdiframewndexispointneardocksite"></a><a name="ispointneardocksite"></a>CMDIFrameWndEx::IsPointNearDockSite  
 도킹 사이트 근처에 지정된 된 지점 인지 확인 합니다.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 화면 좌표에서 지정 된 지점입니다.  
  
 [in] `dwBarAlignment`  
 중요 한 점은 가까운 가장자리를 지정 합니다. 가능한 값은 `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, 및`CBRS_ALIGN_BOTTOM`  
  
 [in] `bOuterEdge`  
 `TRUE`도킹 사이트;의 외부 테두리 주변 포인터가 있는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 사이트; 근처 포인터가 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 요점은 도킹 사이트 근처의 민감도 도킹 관리자에서 설정 내에 없을 때입니다. 구분 기본값은 15 픽셀입니다.  
  
##  <a name="a-nameisprintpreviewa--cmdiframewndexisprintpreview"></a><a name="isprintpreview"></a>CMDIFrameWndEx::IsPrintPreview  
 프레임 창 인쇄 미리 보기 모드 인지 여부를 결정 합니다.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 창 인쇄 미리 보기 모드에 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameloadframea--cmdiframewndexloadframe"></a><a name="loadframe"></a>CMDIFrameWndEx::LoadFrame  
 리소스 정보에서 프레임 창을 만듭니다.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIDResource`  
 프레임 창에 연결 된 공유 리소스의 ID입니다.  
  
 [in] `dwDefaultStyle`  
 프레임 창 스타일입니다.  
  
 [in] `pParentWnd`  
 프레임의 부모에 대 한 포인터입니다.  
  
 [in] `pContext`  
 에 대 한 포인터는 [CCreateContext 구조](../../mfc/reference/ccreatecontext-structure.md)합니다. 이 매개 변수는 `NULL`일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면, 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameloadmdistatea--cmdiframewndexloadmdistate"></a><a name="loadmdistate"></a>Cmdiframewndex:: Loadmdistate  
 MDI 탭 그룹의 지정 된 레이아웃 및 이전에 연된 문서 목록을 로드합니다.  
  
```  
virtual BOOL LoadMDIState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`부하 성공 하는 경우 `FALSE` 로드 되지 않았거나 로드할 데이터가 없는 경우.  
  
### <a name="remarks"></a>주의  
 를 로드 하거나 MDI 탭 및 그룹의 상태 및 열려 있는 문서의 목록을 저장 하려면 다음을 수행 합니다.  
  
-   호출 [CMDIFrameWndEx::SaveMDIState](#savemdistate) 주 프레임을 닫을 때  
  
-   호출 [cmdiframewndex:: Loadmdistate](#loadmdistate) 주 프레임을 만들 때. 이 호출에 대 한 가장 좋은 위치는 주 프레임은 처음으로 표시 되기 전에입니다. 추가 `CWinAppEx::EnableLoadWindowPlacement` `(FALSE);` 전에 `pMainFrame->LoadFrame (IDR_MAINFRAME);.` 추가 `CBCGPWorkspace::ReloadWindowPlacement` `(pMainFrame);` 를 호출한 후 `LoadMDIState` 레지스트리에 저장 된 위치에 주 프레임을 표시 합니다.  
  
-   재정의 `GetDocumentName` 에 `CMDIChildWndEx`-응용 프로그램 파일로 저장 되지 않은 문서를 표시 하는 경우 클래스를 파생 합니다. 반환 된 문자열의 문서 식별자로 레지스트리에 저장 됩니다. 기본 구현을 [CMDIChildWndEx::GetDocumentName](../../mfc/reference/cmdichildwndex-class.md#getdocumentname) 에서 가져온 값을 반환 [CDocument::GetPathName](../../mfc/reference/cdocument-class.md#getpathname)합니다.  
  
-   재정의 [CMDIFrameWndEx::CreateDocumentWindow](#createdocumentwindow) 올바르게 문서를 만드는 레지스트리에서 로드 되는 경우. 첫 번째 매개 변수는 문자열입니다 `GetDocumentName` 반환 합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `LoadMDIState` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&11;](../../mfc/codesnippet/cpp/cmdiframewndex-class_11.cpp)]  
  
##  <a name="a-namemditabmovetonextgroupa--cmdiframewndexmditabmovetonextgroup"></a><a name="mditabmovetonextgroup"></a>CMDIFrameWndEx::MDITabMoveToNextGroup  
 현재 활성 탭된 창에서 활성 탭 다음 또는 이전 탭된 그룹으로 이동 합니다.  
  
```  
void MDITabMoveToNextGroup(BOOL bNext=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bNext`  
 경우 `TRUE`, 다음 탭된 그룹 탭으로 이동 합니다. 경우 `FALSE`, 이전 탭된 그룹으로 이동 합니다.  
  
##  <a name="a-namemditabnewgroupa--cmdiframewndexmditabnewgroup"></a><a name="mditabnewgroup"></a>CMDIFrameWndEx::MDITabNewGroup  
 단일 창에 새 탭된 그룹을 만듭니다.  
  
```  
void MDITabNewGroup(BOOL bVert=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bVert`  
 새 그룹 맞춤을 지정합니다. 경우 `TRUE`, 새 그룹을 세로로 정렬 됩니다. 경우 `FALSE`, 새 그룹 가로로 정렬 됩니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 새 탭 창 (새 탭된 그룹)를를 첫 번째 탭에 추가 합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `MDITabNewGroup` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&12;](../../mfc/codesnippet/cpp/cmdiframewndex-class_12.cpp)]  
  
##  <a name="a-namembcancovertcontrolbartomdichilda--cmdiframewndexmbcancovertcontrolbartomdichild"></a><a name="m_bcancovertcontrolbartomdichild"></a>CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild  
 도킹 창 MDI 자식 창을 변환할 수 있는지 여부를 지정 합니다.  
  
```  
BOOL m_bCanCovertControlBarToMDIChild;  
```  
  
### <a name="remarks"></a>주의  
 MDI 자식 창에 도킹 컨트롤 막대를 변환할 수 있는지 여부를 나타냅니다. 이 플래그는 경우 `TRUE`, 프레임 워크는 변환이 자동으로 처리, 사용자가 선택 하는 경우는 **탭 문서** 명령입니다. 플래그를 보호 하 고 명시적으로이 옵션을 설정 해야이 설정 하거나 `m_bCanCovertControlBarToMDIChild` 의 생성자에는 `CMDIFrameWndEx`-파생 클래스에서 재정의 또는 `CanConvertControlBarToMDIChild`합니다.  
  
 기본값은 `FALSE`입니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `m_bCanCovertControlBarToMDIChild` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&13;](../../mfc/codesnippet/cpp/cmdiframewndex-class_2.cpp)]  
  
##  <a name="a-namembdisablesetredrawa--cmdiframewndexmbdisablesetredraw"></a><a name="m_bdisablesetredraw"></a>CMDIFrameWndEx::m_bDisableSetRedraw  
 MDI 자식 창에 대 한 다시 그리기 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableSetRedraw;  
```  
  
### <a name="remarks"></a>주의  
 기본값은 `TRUE`입니다.  
  
 이 플래그를 설정 `FALSE` MDI 자식 폼을 다시 그릴 최적화 하려는 경우. 이 경우에 프레임 워크를 호출 합니다 `SetRedraw (FALSE)` 응용 프로그램이 활성 탭이 변경 될 때 주 프레임에 대 한 합니다.  
  
 이 플래그는 원치 않는 부작용 (예: 표시 되는 백그라운드 응용 프로그램)를 발생할 수 있습니다. 따라서 눈에 띄는 깜박임을 MDI 탭 활성화 하는 동안 발생 하는 경우에 기본값을 변경 하는 것이 좋습니다.  
  
##  <a name="a-namenegotiateborderspacea--cmdiframewndexnegotiateborderspace"></a><a name="negotiateborderspace"></a>CMDIFrameWndEx::NegotiateBorderSpace  
 OLE 위치에서 활성화 하는 동안 테두리 프레임 창에는 공간을 협상합니다.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nBorderCmd`  
 열거형에서 다음 값 중 하나가 포함 된 `CFrameWnd::BorderCmd`:  
  
- `borderGet` = 1  
  
- `borderRequest` = 2  
  
- `borderSet` = 3  
  
 [in, out] `lpRectBorder`  
 에 대 한 포인터는 [RECT 구조체](../../mfc/reference/rect-structure1.md) 또는 [CRect 클래스](../../atl-mfc-shared/reference/crect-class.md) 테두리의 좌표를 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 방법은 OLE 테두리 공간 협상의 구현에 설명 합니다.  
  
##  <a name="a-nameonclosedockingpanea--cmdiframewndexonclosedockingpane"></a><a name="onclosedockingpane"></a>CMDIFrameWndEx::OnCloseDockingPane  
 사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 도킹 가능한 창에서 단추입니다.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 닫히는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 도킹 창을 닫을 수 있습니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 도킹 창 숨기기를 처리 하려면이 메서드를 재정의 합니다. 반환할 `FALSE` 도킹 창을 숨길 하지 못하도록 하려는 경우.  
  
 기본 구현은 없으며 반환 `TRUE`합니다.  
  
##  <a name="a-nameoncloseminiframea--cmdiframewndexoncloseminiframe"></a><a name="oncloseminiframe"></a>CMDIFrameWndEx::OnCloseMiniFrame  
 사용자가 클릭할 때 프레임 워크에 의해 호출 된 **닫기** 부동 미니 프레임 창의 단추를 합니다.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 닫히는 미니 프레임 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 부동 미니 프레임 창을 닫을 수 있습니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 미니 프레임 창을 부동 숨기기를 처리 하려면이 메서드를 재정의 합니다. 반환할 `FALSE` 부동 미니 프레임 창을 숨길 하지 못하도록 하려는 경우.  
  
 기본 구현은 없으며 반환 `TRUE`합니다.  
  
##  <a name="a-nameonclosepopupmenua--cmdiframewndexonclosepopupmenu"></a><a name="onclosepopupmenu"></a>CMDIFrameWndEx::OnClosePopupMenu  
 활성 팝업 메뉴를 처리할 때 프레임 워크에 의해 호출 된 `WM_DESTROY` 메시지입니다.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPopup`  
 팝업 메뉴에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 알림을 처리 하려는 경우이 메서드를 재정의 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 해당 개체를 처리 하는 경우 MDI 프레임 창에 속하는 개체 `WM_DESTROY` 메시지입니다.  
  
##  <a name="a-nameoncmdmsga--cmdiframewndexoncmdmsg"></a><a name="oncmdmsg"></a>CMDIFrameWndEx::OnCmdMsg  
 라우팅하고 명령 메시지를 발송 하 고 명령 사용자 인터페이스 개체를 업데이트 하려면 프레임 워크에 의해 호출 됩니다.  
  
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
 명령 알림 코드를 식별합니다. 참조 [CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg) 값에 대 한 자세한 내용은 `nCode`합니다.  
  
 [in] `pExtra`  
 값에 따라 사용 `nCode`합니다. 참조 [CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg) 에 대 한 자세한 내용은 `pExtra`합니다.  
  
 [in, out] `pHandlerInfo`  
 일반적으로이 매개 변수 여야 합니다 `NULL`합니다. 그렇지 않은 경우 `NULL`, `OnCmdMsg` 채웁니다는 `pTarget` 및 `pmf` 의 멤버는 `pHandlerInfo` 명령을 디스패치 하는 대신 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지가 처리 되는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="a-nameondrawmenuimagea--cmdiframewndexondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMDIFrameWndEx::OnDrawMenuImage  
 메뉴 항목과 연결된 이미지를 그릴 때 프레임워크에서 호출됩니다.  
  
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
 메뉴 단추에 대 한 포인터입니다.  
  
 [in] `rectImage`  
 이미지의 경계 사각형입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 메서드는 이미지를 그립니다. 기본 구현은 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 가 소유 하 고 메뉴 모음에 속하는 메뉴 항목에 대 한 이미지 렌더링을 사용자 지정 하려는 경우이 메서드를 재정의 `CMDIFrameWndEx`-파생 개체입니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="a-nameondrawmenulogoa--cmdiframewndexondrawmenulogo"></a><a name="ondrawmenulogo"></a>CMDIFrameWndEx::OnDrawMenuLogo  
 프레임 워크 호출 때는 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)프로세스는 `WM_PAINT` 메시지입니다.  
  
```  
virtual void OnDrawMenuLogo(
    CDC*, 
    CMFCPopupMenu*, 
    const CRect&);
```  
  
### <a name="remarks"></a>주의  
 가 소유 하 고 메뉴 모음에 속하는 팝업 메뉴에 로고를 표시 하려면이 함수를 재정의 하는 `CMDIFrameWndEx`-파생 개체입니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="a-nameonerasemdiclientbackgrounda--cmdiframewndexonerasemdiclientbackground"></a><a name="onerasemdiclientbackground"></a>CMDIFrameWndEx::OnEraseMDIClientBackground  
 MDI 프레임 창 프로세스 때 프레임 워크에 의해 호출 된 `WM_ERASEBKGND` 메시지입니다.  
  
```  
virtual BOOL OnEraseMDIClientBackground(CDC*);
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`응용 프로그램 메시지를 처리 하 고 백그라운드를 지웁니다.  
  
### <a name="remarks"></a>주의  
 처리 하려는 경우이 멤버 함수를 재정의 `WM_ERASEBKGND` 메시지는 `CMDIFrameWndEx`-클래스를 파생 합니다.  
  
##  <a name="a-nameonmenubuttontoolhittesta--cmdiframewndexonmenubuttontoolhittest"></a><a name="onmenubuttontoolhittest"></a>CMDIFrameWndEx::OnMenuButtonToolHitTest  
 프레임 워크 호출 때는 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)프로세스 개체를 `WM_NCHITTEST` 메시지입니다.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 도구 모음 단추입니다.  
  
 [out] `pTI`  
 에 대 한 포인터는 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`응용 프로그램은 작성 하는 경우는 `pTI` 매개 변수입니다. 기본 구현은 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 도구 설명에 특정 메뉴 항목에 대 한 정보를 제공 하려는 경우이 메서드를 재정의 합니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="a-nameonmoveminiframea--cmdiframewndexonmoveminiframe"></a><a name="onmoveminiframe"></a>CMDIFrameWndEx::OnMoveMiniFrame  
 미니 프레임 창을 이동 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrame`  
 미니 프레임 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면, 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameonsetpreviewmodea--cmdiframewndexonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CMDIFrameWndEx::OnSetPreviewMode  
 응용 프로그램의 주 프레임 창 인쇄 미리 보기 모드를 설정합니다.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bPreview`  
 경우 `TRUE`, 인쇄 미리 보기 모드를 설정 합니다. 경우 `FALSE`, 미리 보기 모드로 취소 합니다.  
  
 [in] `pState`  
 에 대 한 포인터는 `CPrintPreviewState` 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 재정의 [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode)합니다.  
  
##  <a name="a-nameonshowcustomizepanea--cmdiframewndexonshowcustomizepane"></a><a name="onshowcustomizepane"></a>CMDIFrameWndEx::OnShowCustomizePane  
 빠른 사용자 지정 창이 활성화 될 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPane`  
 빠른 사용자 지정 창에 대 한 포인터입니다.  
  
 [in] `uiToolbarID`  
 사용자 지정 하려면 도구 모음의 컨트롤 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 항상 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 빠른 사용자 지정 창은 사용자가 클릭할 때 열리는 메뉴 **사용자 지정** 도구 모음에 있습니다.  
  
 빠른 사용자 지정 창에서 변경할 수 있도록 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-nameonshowmditabcontextmenua--cmdiframewndexonshowmditabcontextmenu"></a><a name="onshowmditabcontextmenu"></a>CMDIFrameWndEx::OnShowMDITabContextMenu  
 탭 중 하나는 바로 가기 메뉴가 표시 되기 전에 프레임 워크에서 호출 합니다. 만 MDI 탭 그룹에 대해 유효 합니다.  
  
```  
virtual BOOL OnShowMDITabContextMenu(
    CPoint point,  
    DWORD dwAllowedItems,  
    BOOL bTabDrop);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 화면 좌표에서 메뉴의 위치입니다.  
  
 [in] `dwAllowedItems`  
 작업을 현재 탭에 대 한 허용 되는지 나타내는 플래그의 비트 OR 조합 합니다.  
  
- `BCGP_MDI_CREATE_VERT_GROUP`-세로 탭 그룹을 만들 수 있습니다.  
  
- `BCGP_MDI_CREATE_HORZ_GROUP`-가로 탭 그룹을 만들 수 있습니다.  
  
- `BCGP_MDI_CAN_MOVE_PREV`-이전 탭 그룹에 탭을 이동할 수 있습니다.  
  
- `BCGP_MDI_CAN_MOVE_NEXT`-다음 탭 그룹에 탭을 이동할 수 있습니다.  
  
- `BCGP_MDI_CAN_BE_DOCKED`-탭된 문서 (문서 탭된에 대 한 관련) 도킹 된 상태로 전환 합니다.  
  
 [in] `bTabDrop`  
 `TRUE`다른 탭된 그룹에 있는 탭을 끌어서 결과로 메뉴를 표시 합니다. `FALSE`현재 활성 탭에서 바로 가기 메뉴의 메뉴를 표시 합니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드를 재정의 하는 [CBCGPMDIFrameWnd](../../mfc/reference/cmdiframewndex-class.md)-클래스를 파생 합니다.  
  
### <a name="remarks"></a>주의  
 처리 되지 않으면 `OnShowMDITabContextMenu`, 바로 가기 메뉴에 표시 되지 것입니다. 이 함수에서 생성 되는 **MFC 응용 프로그램 마법사** MDI 탭 그룹 기능을 설정 하면 됩니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `OnShowMDITabContextMenu` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&14;](../../mfc/codesnippet/cpp/cmdiframewndex-class_13.cpp)]  
  
##  <a name="a-nameonshowpanesa--cmdiframewndexonshowpanes"></a><a name="onshowpanes"></a>CMDIFrameWndEx::OnShowPanes  
 표시 하거나 숨기려면 창 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 `TRUE`창을 표시 하려면 `FALSE` 을 숨기려면 창입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드를 호출 하 여 창의 상태가 변경 되 면 `FALSE` 창으로 지정 된 상태에 이미 있는 경우 `bShow`합니다. 예를 들어, 창 숨겨져 있는 경우 및 `bShow` 는 `FALSE`, 반환 값은 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 최상위 프레임 창에서 도구 모음을 제거합니다.  
  
 경우 [CDockingManager::m_bHideDockingBarsInContainerMode](../../mfc/reference/cdockingmanager-class.md#m_bhidedockingbarsincontainermode) 는 `TRUE` (기본값) 이면 모든 도킹 창에 표시 되지 것입니다.  
  
##  <a name="a-nameonshowpopupmenua--cmdiframewndexonshowpopupmenu"></a><a name="onshowpopupmenu"></a>CMDIFrameWndEx::OnShowPopupMenu  
 팝업 메뉴를 열었을 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu*);
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`팝업 메뉴가 표시 될 경우. 그렇지 않으면 `FALSE`입니다. 기본 구현은 `TRUE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 팝업 메뉴 활성화 시에 특별 한 처리를 구현 하려는 경우이 메서드를 재정의 합니다. 예를 들어 색 메뉴 단추에 일반 메뉴 항목을 변경 하려는 경우 분리 막대 설정 등에입니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="a-nameonsizemdiclienta--cmdiframewndexonsizemdiclient"></a><a name="onsizemdiclient"></a>CMDIFrameWndEx::OnSizeMDIClient  
 클라이언트 MDI 창의 크기를 변경할 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnSizeMDIClient(
    const CRect& rectOld,  
    const CRect& rectNew);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectOld`  
 MDI 클라이언트 창의 현재 크기입니다.  
  
 [in] `rectNew`  
 MDI 클라이언트 창의 새 크기입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameontearoffmenua--cmdiframewndexontearoffmenu"></a><a name="ontearoffmenu"></a>CMDIFrameWndEx::OnTearOffMenu  
 분리 막대가 있는 메뉴가 활성화될 때 프레임워크에서 호출됩니다.  
  
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
 `TRUE`활성화 되어야 하 고 분리 모음을 사용 하 여 팝업 메뉴를 허용 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 분리 표시줄에 대 한 특별 한 설치 프로그램을 구현 하려는 경우이 함수를 재정의 합니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="a-nameonupdateframemenua--cmdiframewndexonupdateframemenu"></a><a name="onupdateframemenu"></a>CMDIFrameWndEx::OnUpdateFrameMenu  
 프레임 워크는 프레임 메뉴 업데이트에 의해 호출 됩니다.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenuAlt`  
 메뉴에 대 한 핸들입니다.  
  
##  <a name="a-namepanefrompointa--cmdiframewndexpanefrompoint"></a><a name="panefrompoint"></a>CMDIFrameWndEx::PaneFromPoint  
 지정 된 위치를 포함 하는 도킹 창을 반환 합니다.  
  
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
 시점 (화면 좌표)입니다.  
  
 [in] `nSensitivity`  
 확인 된 각 창의 창 사각형 모든 방향으로이 값으로 확대 됩니다.  
  
 [in] `bExactBar`  
 경우 `TRUE`, `nSensitivity` 매개 변수가 무시 됩니다.  
  
 [in] `pRTCBarType`  
 비- `NULL`, 메서드는 지정 된 형식의 창만를 반복 합니다.  
  
 [out] `dwAlignment`  
 창을 발견 되 면이 매개 변수는 창 중 어느 쪽에 가장 가까운 지정 된 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 도킹 창에 대 한 포인터 또는 `NULL` 없는 컨트롤에 의해 지정 된 점이 포함 되 면 `point`합니다.  
  
### <a name="remarks"></a>주의  
 호출의 리디렉션는 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md)합니다. 참조 [CDockingManager::ControlBarFromPoint](../../mfc/reference/cdockingmanager-class.md#panefrompoint) 에 대 한 자세한 내용은 합니다.  
  
##  <a name="a-namerecalclayouta--cmdiframewndexrecalclayout"></a><a name="recalclayout"></a>CMDIFrameWndEx::RecalcLayout  
 프레임 창의 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bNotify`  
 프레임 창에 대 한 현재 위치에서 항목의 레이아웃 변경의 알림을 받을지 여부를 결정 합니다. 경우 `TRUE`, 알림을 받는 하 고, 그렇지 않으면 항목을 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 재정의 [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)합니다.  
  
##  <a name="a-nameremovepanefromdockmanagera--cmdiframewndexremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CMDIFrameWndEx::RemovePaneFromDockManager  
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
 제거할 창에 대 한 포인터입니다.  
  
 [in] `bDestroy`  
 `TRUE`제거 창에서 제거 합니다. `FALSE`삭제할 하지 않습니다.  
  
 [in] `bAdjustLayout`  
 `TRUE`즉시 도킹 레이아웃을 조정 합니다. 경우 `FALSE`만 다시 그리기 이벤트가 발생할 때 다른 이유로 조정 하면 발생 합니다 (사용자 창의 크기를 조정, 등 주 프레임을 끌어 놓습니다.).  
  
 [in] `bAutoHide`  
 `TRUE`창 자동 숨기기 창의 목록에서 제거 `FALSE`창에서 일반 창의 목록에서 제거  
  
 [in] `pBarReplacement`  
 제거 창을 대체 하는 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 각 창을 도킹 레이아웃에 참여 하는 도킹 관리자를 등록 해야 합니다. 사용 하 여 [CMDIFrameWndEx::AddPane](#addpane) 또는 [CMDIFrameWndEx::InsertPane](#insertpane) 창을 등록할 수 있습니다.  
  
 프레임 창의 도킹 레이아웃의 일부가 더 이상이 되 면이 메서드를 사용 합니다.  
  
##  <a name="a-namesavemdistatea--cmdiframewndexsavemdistate"></a><a name="savemdistate"></a>CMDIFrameWndEx::SaveMDIState  
 MDI 탭 그룹의 현재 레이아웃 및 이전에 연된 문서 목록을 저장합니다.  
  
```  
virtual BOOL SaveMDIState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`저장 성공 하는 경우 `FALSE` 경우 저장 하지 못했습니다.  
  
### <a name="remarks"></a>주의  
 를 로드 하거나 MDI 탭 및 그룹의 상태 및 열려 있는 문서의 목록을 저장 하려면 다음을 수행 합니다.  
  
-   호출 `SaveMDIState` 주 프레임을 닫을 때  
  
-   호출 [cmdiframewndex:: Loadmdistate](#loadmdistate) 주 프레임을 만들 때. 이 호출에 대 한 권장 위치가 전에 주 프레임은 처음으로 표시 됩니다.  
  
-   호출 `CWinAppEx::EnableLoadWindowPlacement(FALSE);` 하기 전에`pMainFrame->LoadFrame (IDR_MAINFRAME);`  
  
-   호출 `CWinAppEx::ReloadWindowPlacement``(pMainFrame)` 후 `LoadMDIState` 레지스트리에 저장 된 위치에 주 프레임을 표시 합니다.  
  
-   재정의 `GetDocumentName` 에 `CMDIChildWndEx`-응용 프로그램 파일로 저장 되지 않은 문서를 표시 하는 경우 클래스를 파생 합니다. 문서 식별자로 반환 되는 문자열 레지스트리에 저장 됩니다. 자세한 내용은 참조 [CMDIChildWndEx::GetDocumentName](../../mfc/reference/cmdichildwndex-class.md#getdocumentname)합니다.  
  
-   재정의 [CMDIFrameWndEx::CreateDocumentWindow](#createdocumentwindow) 올바르게 문서를 만드는 레지스트리에서 로드 될 때입니다. 매개 변수를 `CreateDocumentWindow` 문자열은는 `GetDocumentName` 이전 반환 합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `SaveMDIState` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&15;](../../mfc/codesnippet/cpp/cmdiframewndex-class_14.cpp)]  
  
##  <a name="a-namesetprintpreviewframea--cmdiframewndexsetprintpreviewframe"></a><a name="setprintpreviewframe"></a>CMDIFrameWndEx::SetPrintPreviewFrame  
 인쇄 미리 보기 프레임 창을 설정입니다.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 인쇄 미리 보기 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetuptoolbarmenua--cmdiframewndexsetuptoolbarmenu"></a><a name="setuptoolbarmenu"></a>CMDIFrameWndEx::SetupToolbarMenu  
 사용자 지정 항목과 더미 항목을 대체 하 여 도구 모음 개체를 수정 합니다.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `menu`  
 에 대 한 참조는 [CMenu 클래스](../../mfc/reference/cmenu-class.md) 개체를 수정할 수 있습니다.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 첫 번째 사용자 지정 명령을 지정합니다.  
  
 [in] `uiViewUserToolbarCmdLast`  
 마지막 사용자 지정 명령을 지정합니다.  
  
##  <a name="a-nameshowfullscreena--cmdiframewndexshowfullscreen"></a><a name="showfullscreen"></a>CMDIFrameWndEx::ShowFullScreen  
 전체 화면 모드로 일반 모드에서 주 프레임을 전환합니다.  
  
```  
void ShowFullScreen();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameshowpanea--cmdiframewndexshowpane"></a><a name="showpane"></a>CMDIFrameWndEx::ShowPane  
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
 창에 표시 하거나 숨길 수에 대 한 포인터입니다.  
  
 [in] `bShow`  
 `TRUE`창을 표시 하려면 창입니다. `FALSE`창을 숨기려면 합니다.  
  
 [in] `bDelay`  
 `TRUE`도킹 레이아웃의 다시 계산을 지연 합니다. `FALSE`도킹 레이아웃을 즉시 다시 계산 합니다.  
  
 [in] `bActivate`  
 `TRUE`창을 표시 하려면 활성으로 해야 합니다. `FALSE`창에서 비활성으로 표시 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 창 표시 / 숨기기를 호출 합니다. 사용 하지 않는 `ShowWindow` 창을 도킹 합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `ShowPane` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&16;](../../mfc/codesnippet/cpp/cmdiframewndex-class_15.cpp)]  
  
##  <a name="a-nameshowwindowsdialoga--cmdiframewndexshowwindowsdialog"></a><a name="showwindowsdialog"></a>CMDIFrameWndEx::ShowWindowsDialog  
 만듭니다는 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 상자를 엽니다.  
  
```  
void ShowWindowsDialog();
```  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `ShowWindowsDialog` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&18;](../../mfc/codesnippet/cpp/cmdiframewndex-class_16.cpp)]  
  
##  <a name="a-nametabbeddocumenttocontrolbara--cmdiframewndextabbeddocumenttocontrolbar"></a><a name="tabbeddocumenttocontrolbar"></a>CMDIFrameWndEx::TabbedDocumentToControlBar  
 도킹 창에 지정 된 탭된 문서를 변환합니다.  
  
```  
virtual BOOL TabbedDocumentToControlBar(CMDIChildWndEx* pMDIChildWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMDIChildWnd`  
 도킹 창이 포함 된 MDI 자식 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공적으로 수행 하는 경우 `FALSE` 실패 합니다.  
  
### <a name="remarks"></a>주의  
 도킹 창에 탭된 문서를 변환 하려면이 메서드를 사용 합니다. 탭된 문서를 사용 하 여 만든 것 이어야 [CMDIFrameWndEx::ControlBarToTabbedDocument](#controlbartotabbeddocument)합니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `TabbedDocumentToControlBar` 에 사용 되는 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&19;](../../mfc/codesnippet/cpp/cmdiframewndex-class_17.cpp)]  
  
##  <a name="a-nameupdatecaptiona--cmdiframewndexupdatecaption"></a><a name="updatecaption"></a>CMDIFrameWndEx::UpdateCaption  
 창 프레임 캡션을 업데이트 하는 프레임 워크에서 호출 됩니다.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameupdatemditabbedbarsiconsa--cmdiframewndexupdatemditabbedbarsicons"></a><a name="updatemditabbedbarsicons"></a>CMDIFrameWndEx::UpdateMDITabbedBarsIcons  
 각 MDI 탭된 창에 대 한 아이콘을 설정합니다.  
  
```  
void UpdateMDITabbedBarsIcons();
```  
  
##  <a name="a-namewinhelpa--cmdiframewndexwinhelp"></a><a name="winhelp"></a>CMDIFrameWndEx::WinHelp  
 WinHelp 응용 프로그램 또는 상황에 맞는 도움말을 시작하기 위해 프레임워크에서 호출됩니다.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwData`  
 `nCmd`에 지정된 도움말의 형식에 필요한 대로 데이터를 지정합니다.  
  
 [in] `nCmd`  
 요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 `dwData` 매개 변수에 영향을 주는 방식에 대해서는 Windows SDK의 [WinHelp 함수](http://msdn.microsoft.com/library/windows/desktop/bb762267) (영문)를 참조하세요.  
  
### <a name="remarks"></a>주의  
 이 메서드를 재정의 [CWnd::WinHelp](../../mfc/reference/cwnd-class.md#winhelp)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWndEx 클래스](../../mfc/reference/cmdichildwndex-class.md)

