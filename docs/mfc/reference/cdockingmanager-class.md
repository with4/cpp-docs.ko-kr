---
title: CDockingManager 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5dad441d2aa997a3e32d53f07683877442100a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377683"
---
# <a name="cdockingmanager-class"></a>CDockingManager 클래스
주 프레임 창에서 도킹 레이아웃을 제어하는 핵심 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|가 도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|모음에 대 한 핸들 추가 숨겨진된 MDI 표시줄 창과 탭의 목록에는 창입니다.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|미니 프레임의 목록에는 프레임을 추가합니다.|  
|[CDockingManager::AddPane](#addpane)|창을 도킹 관리자에 등록합니다.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|다시 계산 하 고 프레임 창에서 모든 창 레이아웃을 조정 합니다.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|로 인해는 `WM_NCCALCSIZE` 모든 창에 보내야 하는 메시지 및 `CPaneFrameWnd` windows 합니다.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|사각형의 맞춤을 조정합니다.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|도킹 창을 자동 숨기기 모드에서 크기를 조정 걸리는 전체 너비 또는 높이의 프레임의 클라이언트 영역으로 둘러싸인 도킹 사이트 되도록 합니다.|  
|[CDockingManager::AutoHidePane](#autohidepane)|자동 숨기기 도구 모음을 만듭니다.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|지정된 된 맞춤 맨 위에 있는 도킹 된 막대를 제공 합니다.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|형태의 도킹 창 및 도구 모음 메뉴에 추가합니다.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹 된 창의 예상된 사각형을 계산합니다.|  
|[CDockingManager::Create](#create)|도킹 관리자를 만듭니다.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|지정된 된 지점 및 도킹 상태를 포함 하는 창을 확인 합니다.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|레지스트리에서 도킹 레이아웃의 로드를 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CDockingManager::DockPane](#dockpane)|창을 다른 창 또는 프레임 창에 도킹합니다.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|주 프레임 창의 도킹을 사용 하도록 설정 하 고 도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.|  
|[CDockingManager::EnableDocking](#enabledocking)|가 도킹 창을 만들고를 주 프레임 창의 도킹을 사용 하도록 설정 합니다.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|모든 도킹 창 캡션에 팝업 메뉴를 열고 하는 추가 단추가 표시 됩니다.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|사용자가 마우스 오른쪽 단추를 클릭 하 고 라이브러리 WM_CONTEXTMENU 메시지를 처리 하는 경우 응용 프로그램 도구 모음 및 도킹 창 목록을 특별 한 상황에 맞는 메뉴를 표시 하도록 라이브러리를 알려 줍니다.|  
|[CDockingManager::FindDockSite](#finddocksite)|막대를 검색 하는 지정된 된 위치에는 창 지정 된 맞춤 합니다.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|막대를 반환 합니다. 창 대상 표시줄 창 id를 포함 합니다.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|지정 된 컨트롤 id 창을 찾습니다.|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|가상 사각형에 현재 있는 모든 도구 모음 위치를 커밋합니다.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|지정된 된 점을 포함 하는 프레임을 반환 합니다.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|클라이언트 영역의 경계를 포함 하는 사각형을 가져옵니다.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|현재 도킹 모드를 반환합니다.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|부모 창 프레임에 대 한 포인터를 가져옵니다.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|창을 활성화 된 맞춤을 반환 합니다.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|미니 컴퓨터의 목록을 가져옵니다.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|프레임의 외부 가장자리를 포함 하는 사각형을 가져옵니다.|  
|[CDockingManager::GetPaneList](#getpanelist)|창 고 도킹 관리자에 속해 있는 목록을 반환 합니다. 모든 부동 창 포함 됩니다.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|스마트 도킹 관리자에 대 한 포인터를 검색합니다.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|스마트 도킹 관리자에 대 한 포인터를 검색합니다.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|고 도킹 관리자에 대 한 스마트 도킹 매개 변수를 반환 합니다.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|스마트 도킹 표식을 표시 하는 데 사용 되는 테마를 반환 하는 정적 메서드.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|자동 숨기기 모드에 있는 창을 숨깁니다.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|가 도킹 창을 만들고 컨트롤 막대 목록에 삽입 합니다.|  
|[CDockingManager::InsertPane](#insertpane)|컨트롤 막대 목록에는 제어판을 삽입합니다.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|팝업 메뉴가 알림의 모든 창에 표시 되는지 여부를 지정 합니다.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|모든 창 레이아웃을 조정 하는 경우를 결정 합니다.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|OLE 컨테이너 모드 하 고 도킹 관리자 인지 여부를 지정 합니다.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|지정된 된 지점 근처 도킹 사이트 인지 확인 합니다.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|인쇄 미리 보기 모드가 설정 된 경우를 결정 합니다.|  
|[CDockingManager::LoadState](#loadstate)|레지스트리에서 도킹 관리자의 상태를 로드합니다.|  
|[CDockingManager::LockUpdate](#lockupdate)|지정된 된 창을 잠급니다.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|프레임 창이 활성화 또는 비활성화 될 때 프레임 워크에서 호출 됩니다.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|창의 목록에 있는 메뉴를 빌드할 때 프레임 워크에서 호출 됩니다.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|지정된 된 점을 포함 하는 창을 반환 합니다.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|선택 또는 지정된 된 명령에 대 한 확인란의 선택을 취소 하 고 표시 된 창 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다.|  
|[CDockingManager::RecalcLayout](#recalclayout)|컨트롤의 목록에 있는 컨트롤의 내부 레이아웃을 다시 계산합니다.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|빈 창 컨테이너를 해제합니다.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|지정 된 숨겨진 창 막대를 제거 합니다.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|미니 프레임의 목록에서 지정된 된 프레임을 제거 합니다.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 등록을 취소 하 고 도킹 관리자에 있는 목록에서 제거 합니다.|  
|[CDockingManager::ReplacePane](#replacepane)|한 창을 다른 창으로 대체합니다.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|미니 프레임 목록에서 프레임을 다시 정렬 합니다.|  
|[CDockingManager::SaveState](#savestate)|레지스트리에 도킹 관리자의 상태를 저장합니다.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|모든 미니 프레임에 지정된 된 메시지를 보냅니다.|  
|[CDockingManager::Serialize](#serialize)|보관 하 고 도킹 관리자를 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|크기, 너비 및 높이 컨트롤 막대와 지정 된 창에 설정합니다.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|도킹 모드를 설정합니다.|  
|[CDockingManager::SetDockState](#setdockstate)|컨트롤 막대, 미니 프레임 및 자동 숨기기 막대의 도킹 상태를 설정합니다.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|인쇄 미리 보기에 표시 되는 막대의 인쇄 미리 보기 모드를 설정 합니다.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|스마트 도킹의 동작을 정의 하는 매개 변수를 설정 합니다.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|표시 하거나 미니 프레임 창을 숨깁니다.|  
|[CDockingManager::ShowPanes](#showpanes)|표시 하거나 제어 및 자동 숨기기 막대의 창을 숨깁니다.|  
|[CDockingManager::StartSDocking](#startsdocking)|스마트 도킹 관리자의 맞춤에 따라 지정 된 창의 스마트 도킹을 시작 합니다.|  
|[CDockingManager::StopSDocking](#stopsdocking)|중지 스마트 도킹 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|OLE 컨테이너 모드의 창을 도킹 관리자에 숨기도록 있는지 여부를 지정 합니다.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|전역 도킹 모드를 지정합니다.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|도킹 민감도 지정합니다.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|도킹 창을 즉시 도킹 모드에 도킹 된 전에 시간을 밀리초 단위로 지정 합니다.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|주 프레임 창에는 도구 모음 도킹 전에 시간을 밀리초 단위로 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 주 프레임 창을 만들고 자동으로이 클래스를 초기화 합니다.  
  
 도킹 관리자 개체를 도킹 레이아웃에 있는 모든 창 목록 및 모든 목록을 보유 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 주 프레임 창에 속한 창에 있습니다.  
  
 `CDockingManager` 창을 찾는 데 사용할 수 있는 일부 서비스를 구현 하는 클래스 또는 `CPaneFrameWnd` 창. 일반적으로 호출 하지 않으면 이러한 서비스를 직접 주 프레임 창 개체에 래핑되고 합니다. 자세한 내용은 참조 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)합니다.  
  
## <a name="customization-tips"></a>사용자 지정 팁  
 다음 팁에 적용 `CDockingManager` 개체:  
  
- [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 이러한 도킹 모드를 지원 합니다.  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     이러한 도킹 모드에 의해 정의 됩니다 [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) 호출 하 여 설정 하 고 [CDockingManager::SetDockingMode](#setdockingmode)합니다.  
  
-   부동화 되지 않음, 크기 조정이 불가능 창을 만들려는 경우에 호출 된 [CDockingManager::AddPane](#addpane) 메서드. 이 메서드는 창에서 창 레이아웃을 담당 하 고 도킹 관리자에 등록 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 다양 한 메서드를 사용 하는 방법을 보여 줍니다는 `CDockingManager` 구성 하는 클래스는 `CDockingManager` 개체입니다. 이 예제에서는 모든 도킹 창 캡션에 팝업 메뉴를 열고 추가 단추를 표시 하는 방법과 개체의 도킹 모드를 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>  CDockingManager::AddDockSite  
 가 도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `info`  
 포함 된 정보 구조체에 대 한 참조 도킹 창 맞춤 합니다.  
  
 [out] `ppDockBar`  
 새 도킹 창에 대 한 포인터에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 창을 성공적으로 만들어진 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar  
 모음에 대 한 핸들 추가 숨겨진된 MDI 표시줄 창과 탭의 목록에는 창입니다.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 에 대 한 포인터를 막대로 창  
  
##  <a name="addpane"></a>  CDockingManager::AddPane  
 창을 도킹 관리자에 등록합니다.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pWnd`  
 창 고 도킹 관리자에 추가 하려면를 지정 합니다.  
  
 [in] `bTail`  
 `TRUE` 고 도킹 관리자;에 대 한 창에서 창의 목록 끝에 추가 하려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bAutoHide`  
 내부 전용입니다. 항상 기본값을 사용 하 여 `FALSE`합니다.  
  
 [in] `bInsertForOuterEdge`  
 내부 전용입니다. 항상 기본값을 사용 하 여 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창 고 도킹 관리자;에 성공적으로 등록 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 부동화 되지 않음, 크기 조정이 불가능 창 고 도킹 관리자에 등록 하려면이 메서드를 호출 합니다. 등록 하는 경우 수행 하지는 창이 올바르게 표시 되지 않을 고 도킹 관리자를 배치 되 면 합니다.  
  
##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout  
 다시 계산 하 고 프레임 창에서 모든 창 레이아웃을 조정 합니다.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hdwp`  
 지연 된 창 위치 구조를 지정합니다. 자세한 내용은 [Windows 데이터 형식](http://msdn.microsoft.com/library/windows/desktop/aa383751)을 참조하세요.  
  
### <a name="remarks"></a>설명  
  
##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame  
 미니 프레임의 목록에는 프레임을 추가합니다.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 프레임에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 미니 프레임 목록에 없는 프레임과; 성공적으로 추가 하는 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames  
 로 인해는 `WM_NCCALCSIZE` 모든 창에 보내야 하는 메시지 및 `CPaneFrameWnd` windows 합니다.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="adjustrecttoclientarea"></a>  CDockingManager::AdjustRectToClientArea  
 사각형의 맞춤을 조정합니다.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectResult`  
 에 대 한 참조는 `CRect` 개체  
  
 [in] `dwAlignment`  
 맞춤은 `CRect` 개체  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 하는 경우의 맞춤은 `CRect` 개체 조정 되었습니다. `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 `dwAlignment` 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane  
 도킹 창을 자동 숨기기 모드에서 크기를 조정 걸리는 전체 너비 또는 높이의 프레임의 클라이언트 영역으로 둘러싸인 도킹 사이트 되도록 합니다.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDefaultSlider`  
 도킹 슬라이더 창입니다.  
  
 [in] `bIsVisible`  
 `TRUE` 도킹 창에 표시 되 면 `FALSE` 그렇지 않은 경우.  
  
##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane  
 자동 숨기기 도구 모음을 만듭니다.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 막대에 대 한 포인터 창.  
  
 [in] `pCurrAutoHideToolBar`  
 자동 숨기기 도구 모음에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `NULL` 자동 도구 모음을 숨기는 경우 만들어진 개체가 아닙니다. 그렇지 않으면 새 도구 모음에 대 한 포인터입니다.  
  
##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop  
 지정된 된 맞춤 맨 위에 있는 도킹 된 막대를 제공 합니다.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 다른 창의 위쪽에 도킹 막대의 맞춤입니다.  
  
 [in] `bExcludeDockedBars`  
 `TRUE` 도킹 된 막대 위에 표시;에서 제외 하려면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu  
 형태의 도킹 창 및 도구 모음 메뉴에 추가합니다.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `menu`  
 도킹 창 및 도구 모음을 이름을 추가 하려면 메뉴입니다.  
  
 [in] `bToolbarsOnly`  
 `TRUE` 도구 모음 이름만; 메뉴에 추가 하려면 `FALSE` 그렇지 않은 경우.  
  
##  <a name="calcexpecteddockedrect"></a>  CDockingManager::CalcExpectedDockedRect  
 도킹 된 창의 예상된 사각형을 계산합니다.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 도킹 창에 대 한 포인터입니다.  
  
 [in] `ptMouse`  
 마우스 위치입니다.  
  
 [out] `rectResult`  
 계산 된 사각형입니다.  
  
 [in] `bDrawTab`  
 `TRUE` 탭; 그리려면 그렇지 않으면 `FALSE`합니다.  
  
 [out] `ppTargetBar`  
 대상 창에 대 한 포인터에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자로 지정 된 지점에 창을 끌 경우는 창이 차지 하는 사각형을 계산 `ptMouse` 있습니다 도킹 하 고 있습니다.  
  
##  <a name="create"></a>  CDockingManager::Create  
 도킹 관리자를 만듭니다.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 고 도킹 관리자의 부모 프레임에 대 한 포인터입니다. 이 값이 아니어야 `NULL`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 항상 합니다.  
  
##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus  
 지정된 된 지점 및 도킹 상태를 포함 하는 창을 확인 합니다.  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pt`  
 위치를 확인 하는 창입니다.  
  
 [in] `nSensitivity`  
 확인 된 각 창에 창 사각형을 높이기 위해 값입니다. 창을 지정 된 점이이 증가 된 지역의 경우 검색 조건을 충족 합니다.  
  
 [in] `dwEnabledAlignment`  
 도킹 창의 맞춤입니다.  
  
 [out] `ppTargetBar`  
 대상 창에 대 한 포인터에 대 한 포인터입니다.  
  
 [in] `pBarToIgnore`  
 메서드를 무시 하는 창입니다.  
  
 [in] `pBarToDock`  
 도킹 된 창입니다.  
  
### <a name="return-value"></a>반환 값  
 도킹 상태입니다.  
  
### <a name="remarks"></a>설명  
 도킹 상태는 다음 값 중 하나일 수 있습니다.  
  
|AFX_CS_STATUS 값|의미|  
|---------------------------|-------------|  
|CS_NOTHING|도킹 사이트를 통해는 포인터가 아닙니다. 따라서 창에서 유지 부동 합니다.|  
|CS_DOCK_IMMEDIATELY|직접 실행 모드에서 도킹 사이트 위에 포인터를 (DT_IMMEDIATE 스타일 사용), 하므로 창에서 즉시 도킹 해야 합니다.|  
|CS_DELAY_DOCK|포인터가 다른 도킹 창 또는 주 프레임 가장자리 가장 도킹 사이트 끝났습니다.|  
|CS_DELAY_DOCK_TO_TAB|포인터를 창에 탭된 창에서 도킹 될 도킹 사이트 끝났습니다. 나는 탭된 창의 탭 영역을 다른 도킹 창의 캡션을 통해 마우스를 가져갈 때 발생 합니다.|  
  
##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState  
 레지스트리에서 도킹 레이아웃의 로드를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDisable`  
 `TRUE` 레지스트리에서; 도킹 레이아웃의 로드를 사용 하지 않도록 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램 상태를 로드 하는 경우 현재 레이아웃 도킹 창 및 도구 모음을 유지 해야 하는 경우이 메서드를 호출 합니다.  
  
##  <a name="dockpane"></a>  CDockingManager::DockPane  
 창을 다른 창 또는 프레임 창에 도킹합니다.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 에 대 한 포인터를 막대로 창에 도킹 합니다.  
  
 [in] `nDockBarID`  
 도킹 막대의 id입니다.  
  
 [in] `lpRect`  
 대상 사각형입니다.  
  
##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf  
 창을 다른 창의 왼쪽에 도킹합니다.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBarToDock`  
 왼쪽에 도킹 창에 대 한 포인터 `pTargetBar`합니다.  
  
 [in] `pTargetBar`  
 대상 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창에서 성공적으로; 도킹 된 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes  
 주 프레임 창의 도킹을 사용 하도록 설정 하 고 도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwStyle`  
 도킹 맞춤입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 창을 성공적으로 만들어진 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="enabledocking"></a>  CDockingManager::EnableDocking  
 가 도킹 창을 만들고를 주 프레임 창의 도킹을 사용 하도록 설정 합니다.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwStyle`  
 도킹 맞춤입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 창을 성공적으로 만들어진 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu  
 모든 도킹 창 캡션에 팝업 메뉴를 열고 하는 추가 단추가 표시 됩니다.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE` 도킹 사이트 메뉴;를 사용 하도록 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 도킹 사이트 메뉴에 있는 창의 도킹 상태를 변경 하는 데 다음 옵션이 표시 됩니다.  
  
- `Floating` -창을 부동합니다.  
  
- `Docking` -주 프레임 창에서 마지막 도킹 위치 위치의 창 도킹  
  
- `AutoHide` -창 자동 숨기기 모드로 전환  
  
- `Hide` -창을 숨깁니다.  
  
 이 메뉴는 기본적으로 표시 되지 않습니다.  
  
##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu  
 사용자가 마우스 오른쪽 단추를 클릭 하 고 라이브러리 WM_CONTEXTMENU 메시지를 처리 하는 경우 응용 프로그램 도구 모음 및 도킹 창 목록을 특별 한 상황에 맞는 메뉴를 표시 하도록 라이브러리를 알려 줍니다.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 경우 `TRUE`, 라이브러리 자동 상황에 맞는 메뉴;에 대 한 지원을 했으면 `FALSE` 라이브러리 자동 상황에 맞는 메뉴에 대 한 지원을 해제 합니다.  
  
 [in] `uiCustomizeCmd`  
 에 대 한 명령 id는 **사용자 지정** 메뉴 항목입니다.  
  
 [in] `strCustomizeText`  
 텍스트는 **사용자 지정** 항목입니다.  
  
 [in] `bToolbarsOnly`  
 경우 `TRUE`, 메뉴 경우 응용 프로그램 도구 모음; 목록만 표시 `FALSE`, 라이브러리는 응용 프로그램 도킹 창이이 목록에 추가 합니다.  
  
##  <a name="finddocksite"></a>  CDockingManager::FindDockSite  
 막대를 검색 하는 지정된 된 위치에는 창 지정 된 맞춤 합니다.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 막대의 맞춤 창.  
  
 [in] `bOuter`  
 경우 `TRUE`, 컨트롤 막대 목록에 헤드 위치에서 가로 막대를 검색 합니다. 그렇지 않은 경우 컨트롤 막대의 목록에서 비상 위치에서 가로 막대를 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 맞춤; 있는 도킹 창 `NULL` 그렇지 않은 경우.  
  
##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID  
 지정 된 컨트롤 id 창을 찾습니다.  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uBarID`  
 찾을 창의 컨트롤 ID를 지정 합니다.  
  
 [in] `bSearchMiniFrames`  
 `TRUE` 검색에 모든 부동 창을 포함 합니다. `FALSE` 도킹 된 창에만 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 [CBasePane](../../mfc/reference/cbasepane-class.md) 지정 된 컨트롤 ID를 가진 개체를 또는 `NULL` 지정한 창을 찾을 수 없는 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane  
 막대를 반환 합니다. 창 대상 표시줄 창 id를 포함 합니다.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTargetBar`  
 대상 표시줄 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 막대 대상 표시줄 창의; id가 있는 창 `NULL` 창 막대 없는 등가 있는 경우.  
  
##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects  
 가상 사각형에 현재 있는 모든 도구 모음 위치를 커밋합니다.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>설명  
 응용 프로그램 기억 원래 위치에서 사용자는 도구 모음을 끌어가 *가상 사각형*합니다. 도크 사이트의 전체 도구 모음을 이동 하면 도구 모음 다른 도구 모음을 이동할 수도 있습니다. 다른 도구 모음의 원래 위치로 해당 가상 사각형에 저장 됩니다.  
  
##  <a name="framefrompoint"></a>  CDockingManager::FrameFromPoint  
 지정된 된 점을 포함 하는 프레임을 반환 합니다.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pt`  
 화면 좌표를 확인 하는 지점을 지정 합니다.  
  
 [in] `pFrameToExclude`  
 제외할 프레임에 대 한 포인터입니다.  
  
 [in] `bFloatMultiOnly`  
 `TRUE` 인스턴스 프레임을 제외 하려면 `CMultiPaneFrameWnd`; `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 점을;가 포함 된 프레임 `NULL` 그렇지 않은 경우.  
  
##  <a name="getclientareabounds"></a>  CDockingManager::GetClientAreaBounds  
 클라이언트 영역의 경계를 포함 하는 사각형을 가져옵니다.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rcClient`  
 클라이언트 영역의 경계를 포함 하는 사각형에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 클라이언트 영역의 경계를 포함 하는 사각형입니다.  
  
##  <a name="getdockingmode"></a>  CDockingManager::GetDockingMode  
 현재 도킹 모드를 반환합니다.  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>반환 값  
 현재 도킹 모드를 나타내는 열거자 값입니다. 다음 값 중 하나일 수 있습니다.  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>설명  
 도킹 모드를 설정 하려면 호출 [CDockingManager::SetDockingMode](#setdockingmode)합니다.  
  
##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd  
 부모 창 프레임에 대 한 포인터를 가져옵니다.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 부모 창 프레임에 대 한 포인터입니다.  
  
##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment  
 창을 활성화 된 맞춤을 반환 합니다.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>반환 값  
 비트 조합 `CBRS_ALIGN_` 플래그 또는 자동 숨기기 창을 사용할 수 없는 경우 0입니다. 자세한 내용은 참조 [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)합니다.  
  
### <a name="remarks"></a>설명  
 메서드 자동 숨기기 컨트롤 막대에 대 한 활성화 된 맞춤을 반환합니다. 자동 숨기기 막대를 사용 하도록 설정 하려면 호출 [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)합니다.  
  
##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames  
 미니 컴퓨터의 목록을 가져옵니다.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>반환 값  
 미니 고 도킹 관리자에 속하는 컨트롤 막대를 포함 하는 컴퓨터의 목록.  
  
##  <a name="getouteredgebounds"></a>  CDockingManager::GetOuterEdgeBounds  
 프레임의 외부 가장자리를 포함 하는 사각형을 가져옵니다.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프레임의 외부 가장자리를 포함 하는 사각형입니다.  
  
##  <a name="getpanelist"></a>  CDockingManager::GetPaneList  
 창 고 도킹 관리자에 속해 있는 목록을 반환 합니다. 모든 부동 창 포함 됩니다.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `lstBars`  
 현재 도킹 관리자의 모든 창에 포함 되어 있습니다.  
  
 [in] `bIncludeAutohide`  
 `TRUE` 자동 숨기기 모드;에 있는 창 포함 하려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `pRTCFilter`  
 그렇지 않으면 `NULL`, 반환된 된 목록에 지정된 된 런타임 클래스의만 창이 있습니다.  
  
 [in] `bIncludeTabs`  
 `TRUE` 탭이 있습니다; 포함 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 메서드가 반환에 대 한 포인터가 고 도킹 관리자에는 모든 탭된 창이 있는 경우 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md) 개체 탭을 명시적으로 열거 해야 합니다.  
  
 사용 하 여 `pRTCFilter` 창의 특정 클래스를 가져올 수 있습니다. 예를 들어이 값을 적절 하 게 설정 하 여 도구 모음만 얻을 수 있습니다.  
  
##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager  
 스마트 도킹 관리자에 대 한 포인터를 검색합니다.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [스마트 도킹 관리자](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534)합니다.  
  
##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent  
 스마트 도킹 관리자에 대 한 포인터를 검색합니다.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>반환 값  
 스마트 도킹 관리자에 대 한 포인터입니다.  
  
##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams  
 고 도킹 관리자에 대 한 스마트 도킹 매개 변수를 반환 합니다.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>반환 값  
 현재 도킹 관리자에 대 한 스마트 도킹 매개 변수를 포함 하는 클래스입니다. 자세한 내용은 참조 [CSmartDockingInfo 클래스](../../mfc/reference/csmartdockinginfo-class.md)합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="hideautohidepanes"></a>  CDockingManager::HideAutoHidePanes  
 자동 숨기기 모드에 있는 창을 숨깁니다.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBarToExclude`  
 숨기기에서 제외할 막대에 대 한 포인터입니다.  
  
 [in] `bImmediately`  
 `TRUE` 즉시; 창을 숨기려면 `FALSE` autohide 효과 함께 창을 숨기려면 합니다.  
  
##  <a name="insertdocksite"></a>  CDockingManager::InsertDockSite  
 가 도킹 창을 만들고 컨트롤 막대 목록에 삽입 합니다.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `info`  
 도킹 창에 대 한 맞춤 정보를 포함 하는 구조입니다.  
  
 [in] `dwAlignToInsertAfter`  
 도킹 창의 맞춤입니다.  
  
 [out] `ppDockBar`  
 도킹 창에 대 한 포인터에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 창을 성공적으로 만들어진 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="insertpane"></a>  CDockingManager::InsertPane  
 컨트롤 막대 목록에는 제어판을 삽입합니다.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 제어 창에 대 한 포인터입니다.  
  
 [in] `pTarget`  
 대상 창에 대 한 포인터입니다.  
  
 [in] `bAfter`  
 `TRUE` 대상 창; 위치 뒤의 창에 삽입 하려면 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 제어 창 컨트롤 막대; 목록에 성공적으로 추가 되는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 제어 창 컨트롤 막대 목록에 이미 있으면 또는 대상 창 컨트롤 막대 목록에 존재 하지 않는 경우이 메서드는 false를 반환 합니다.  
  
##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu  
 팝업 메뉴가 알림의 모든 창에 표시 되는지 여부를 지정 합니다.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 사이트 메뉴 모든 도킹 창; 알림의에 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여 도킹 사이트 메뉴를 사용 하도록 설정할 수 [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)합니다.  
  
##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout  
 모든 창 레이아웃을 조정 하는 경우를 결정 합니다.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 모든 창 레이아웃 조정 됩니다. `FALSE` 그렇지 않은 경우.  
  
##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode  
 OLE 컨테이너 모드 하 고 도킹 관리자 인지 여부를 지정 합니다.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 고 도킹 관리자 OLE 컨테이너; 모드인 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 OLE 컨테이너 모드에서 모든 도킹 창 및 응용 프로그램 도구 모음이 숨겨져 있습니다. 창이 숨겨집니다이 모드로 설정한 경우 [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) 를 `TRUE`합니다.  
  
##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite  
 지정된 된 지점 근처 도킹 사이트 인지 확인 합니다.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 지정 된 지점입니다.  
  
 [out] `dwBarAlignment`  
 중요 한 점은 가까운 가장자리를 지정 합니다. 가능한 값은 `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP` 및 `CBRS_ALIGN_BOTTOM`입니다.  
  
 [out] `bOuterEdge`  
 `TRUE` 도킹 사이트;의 외부 테두리 주변 포인터가 있는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 사이트; 근처 포인터가 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid  
 인쇄 미리 보기 모드가 설정 된 경우를 결정 합니다.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 인쇄 미리 보기 모드가 설정 된; 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="loadstate"></a>  CDockingManager::LoadState  
 레지스트리에서 도킹 관리자의 상태를 로드합니다.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `uiID`  
 고 도킹 관리자의 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 관리자 상태를 성공적으로 로드 한 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="lockupdate"></a>  CDockingManager::LockUpdate  
 지정된 된 창을 잠급니다.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bLock`  
 `TRUE` 창이; 잠긴 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 창이 잠기면 이동할 수 없습니다 및 다시 그릴 수 없습니다.  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode  
 OLE 컨테이너 모드의 창을 도킹 관리자에 숨기도록 있는지 여부를 지정 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>설명  
 이 값을 설정 `FALSE` 모든 창에 표시 되는 주 프레임 도킹 유지 하려는 경우 응용 프로그램 모드인 경우 OLE 컨테이너입니다. 기본적으로이 값은 `TRUE`합니다.  
  
##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal  
 전역 도킹 모드를 지정합니다.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>설명  
 기본적으로 각 도킹 창을 도킹이 모드를 사용 합니다. 이 필드를 설정할 수 있는 값에 대 한 자세한 내용은 참조 [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)합니다.  
  
##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity  
 도킹 민감도 지정합니다.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>설명  
 도킹 민감도 얼마나 가까운지를 부동 정의 도킹 상태를 변경 하는 프레임 워크 전에 창 도킹 창, 도킹 사이트 또는 다른 창을 높일 수 있습니다.  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock  
 도킹 창을 즉시 도킹 모드에 도킹 된 전에 시간을 밀리초 단위로 지정 합니다.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>설명  
 창을 도킹 되기 전에 프레임 워크는 지정 된 기간을 대기 합니다. 이렇게 하면에서 실수로 사용자가 끌고 여전히 동안 위치에 도킹 되 고 창을 않습니다.  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock  
 주 프레임 창에는 도구 모음 도킹 전에 시간을 밀리초 단위로 지정 합니다.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>설명  
 도구 모음 도킹 되기 전에 프레임 워크는 지정 된 기간을 대기 합니다. 이렇게 하면 도구 모음을에서 실수로 사용자가 끌고 여전히 동안 위치에 도킹 되지 않습니다.  
  
##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame  
 프레임 창이 활성화 또는 비활성화 될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActivate`  
 경우 `TRUE`, 프레임 창이 활성화 될 경우 `FALSE`, 프레임 창이 비활성화 됩니다.  
  
##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu  
 활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>설명  
 현재 기본 창을 닫으려면 할 때 프레임 워크에서 WM_DESTROY 메시지를 보냅니다. 알림을 처리 하는이 메서드를 재정의 `CMFCPopupMenu` 프레임 창에 속하는 개체는 경우는 `CMFCPopupMenu` 프로세스 개체는 `WM_DESTROY` 메시지입니다.  
  
##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame  
 미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrame`  
 미니 프레임 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면; 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu  
 창의 목록에 있는 메뉴를 빌드할 때 프레임 워크에서 호출 됩니다.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 메뉴 위치를 지정합니다.  
  
##  <a name="panefrompoint"></a>  CDockingManager::PaneFromPoint  
 지정된 된 점을 포함 하는 창을 반환 합니다.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 화면 좌표를 확인 하는 지점을 지정 합니다.  
  
 [in] `nSensitivity`  
 확인 된 각 창에 창 사각형을 확장할 값입니다. 창을 지정 된 지점이 높여서이 지역에 있으면 검색 조건을 충족 합니다.  
  
 [in] `bExactBar`  
 `TRUE` 무시 하려면는 `nSensitivity` 매개 변수, 그렇지 않으면 `FALSE`합니다.  
  
 [in] `pRTCBarType`  
 그렇지 않으면 `NULL`, 메서드가 지정 된 형식의 창만 검색 합니다.  
  
 [in] `bCheckVisibility`  
 `TRUE` 표시 창;을 확인 하려면 그렇지 않으면 `FALSE`합니다.  
  
 [out] `dwAlignment`  
 창이 지정된 된 지점에서 발견 되 면이 매개 변수에 지정된 된 지점에 가장 가까운 했던 창 옆쪽에 포함 합니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
 [in] `pBarToIgnore`  
 그렇지 않으면 `NULL`,이 매개 변수로 지정 된 창을 무시 합니다.  
  
### <a name="return-value"></a>반환 값  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-파생 된 지정된 된 점을 포함 하는 개체 또는 `NULL` 없는 창을 찾을 수 없으면입니다.  
  
### <a name="remarks"></a>설명  
 함수 반환 하 고 창을 발견 하는 경우 `dwAlignment` 맞춤을 지정 된 위치를 포함 합니다. 예를 들어, 지점 창의 위쪽에 가장 가까운 되었으면 `dwAlignment` 로 설정 된 `CBRS_ALIGN_TOP`합니다.  
  
##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand  
 선택 또는 지정된 된 명령에 대 한 확인란의 선택을 취소 하 고 표시 된 창 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 메뉴의 컨트롤 막대의 id입니다.  
  
 [in] `nCode`  
 명령 알림 코드입니다.  
  
 [in] `pExtra`  
 void에 대 한 포인터에 대 한 포인터로 캐스팅할은 `CCmdUI` 경우 `nCode` CN_UPDATE_COMMAND_UI 됩니다.  
  
 [in] `pHandlerInfo`  
 정보 구조체에 대 한 포인터입니다. 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 경우 `pEXtra` NULL이 아닌 및 `nCode` CN_UPDATE_COMMAND_UI, 같음 또는 지정 된 컨트롤 막대 있는 경우 `nID`합니다.  
  
##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout  
 컨트롤의 목록에 있는 컨트롤의 내부 레이아웃을 다시 계산합니다.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bNotify`  
 이 매개 변수는 사용되지 않습니다.  
  
##  <a name="releaseemptypanecontainers"></a>  CDockingManager::ReleaseEmptyPaneContainers  
 빈 창 컨테이너를 해제합니다.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>  CDockingManager::RemoveHiddenMDITabbedBar  
 지정 된 숨겨진 창 막대를 제거 합니다.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 막대에 대 한 포인터를 제거 하는 창입니다.  
  
##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame  
 미니 프레임의 목록에서 지정된 된 프레임을 제거 합니다.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 제거할 프레임에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 지정된 된 프레임이 제거 하는 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager  
 창을 등록을 취소 하 고 도킹 관리자에 있는 목록에서 제거 합니다.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 제거할 창에 대 한 포인터입니다.  
  
 [in] `bDestroy`  
 경우 `TRUE`, 제거 창 소멸 됩니다.  
  
 [in] `bAdjustLayout`  
 경우 `TRUE`를 즉시 도킹 레이아웃을 조정 합니다.  
  
 [in] `bAutoHide`  
 경우 `TRUE`을 하면 창 자동 숨기기 막대의 목록에서 제거 됩니다. 경우 `FALSE`, 창 일반 창의 목록에서 제거 됩니다.  
  
 [in] `pBarReplacement`  
 제거 창을 대체 하는 창에 대 한 포인터입니다.  
  
##  <a name="replacepane"></a>  CDockingManager::ReplacePane  
 한 창을 다른 창으로 대체합니다.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOriginalBar`  
 원래 창에 대 한 포인터입니다.  
  
 [in] `pNewBar`  
 원래 창을 대체 하는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창에서 성공적으로 바뀌면; `FALSE` 그렇지 않은 경우.  
  
##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder  
 미니 프레임 목록에서 프레임을 다시 정렬 합니다.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>  CDockingManager::SaveState  
 레지스트리에 도킹 관리자의 상태를 저장합니다.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 레지스트리 키 경로입니다.  
  
 [in] `uiID`  
 도킹 관리자 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 상태가 성공적으로; 저장 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 레지스트리에 고 도킹 관리자 상태 저장 컨트롤 막대의 상태, 자동 숨기기 막대의 상태 및 고 도킹 관리자에 있는 미니 프레임의 상태를 저장 하는 것입니다.  
  
##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames  
 모든 미니 프레임에 지정된 된 메시지를 보냅니다.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uMessage`  
 메시지를 보냅니다.  
  
 [in] `wParam`  
 추가 메시지 종속 정보입니다.  
  
 [in] `lParam`  
 추가 메시지 종속 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 항상 합니다.  
  
##  <a name="serialize"></a>  CDockingManager::Serialize  
 보관 하 고 도킹 관리자를 씁니다.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ar`  
 보관 개체에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 도킹 컨트롤 막대 및 슬라이더와 아카이브에 컨트롤 막대, 미니 프레임, 자동 숨기기 막대 및 MDI 탭 모음 쓰기 수를 결정 하 고 도킹 관리자 보관 파일에 쓰기 작업이 포함 됩니다.  
  
##  <a name="setautohidezorder"></a>  CDockingManager::SetAutohideZOrder  
 크기, 너비 및 높이 컨트롤 막대와 지정 된 창에 설정합니다.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pAHDockingBar`  
 도킹 가능한 창에 대 한 포인터입니다.  
  
##  <a name="setdockingmode"></a>  CDockingManager::SetDockingMode  
 도킹 모드를 설정합니다.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>매개 변수  
 `dockMode`  
 새 도킹 모드를 지정합니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
 `theme`  
 스마트 도킹 표식의 사용할 테마를 지정 합니다. 다음 열거형된 값 중 하나일 수 있습니다: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008 합니다.  
  
### <a name="remarks"></a>설명  
 도킹 모드를 설정 하려면이 정적 메서드를 호출 합니다.  
  
 `dockMode` 다음 값 중 하나일 수 있습니다.  
  
- `DT_STANDARD` -표준 Visual Studio.NET 2003에서 구현 될 때 모드를 도킹 합니다. 창 끌기 컨텍스트 없이 드래그 됩니다.  
  
- `DT_IMMEDIATE` -Microsoft visio에서 즉시 도킹 모드를 구현 합니다. 창 끌기 컨텍스트와 끈 있지만 표식 없이 표시 됩니다.  
  
- `DT_SMART` -Visual Studio 2005에서 구현 될 때 도킹 모드를 스마트 합니다. 창 끌기 컨텍스트와 끈 및 스마트 표식이 표시 되는 창에서 도킹 될 수를 보여 주는 합니다.  
  
##  <a name="setdockstate"></a>  CDockingManager::SetDockState  
 컨트롤 막대, 미니 프레임 및 자동 숨기기 막대의 도킹 상태를 설정합니다.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>  CDockingManager::SetPrintPreviewMode  
 인쇄 미리 보기에 표시 되는 막대의 인쇄 미리 보기 모드를 설정 합니다.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bPreview`  
 `TRUE` 인쇄 미리 보기 모드가 설정 된; `FALSE` 그렇지 않은 경우.  
  
 [in] `pState`  
 미리 보기 상태에 대 한 포인터입니다. 이 매개 변수는 사용되지 않습니다.  
  
##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams  
 스마트 도킹의 동작을 정의 하는 매개 변수를 설정 합니다.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `params`  
 스마트 도킹의 매개 변수를 정의합니다.  
  
### <a name="remarks"></a>설명  
 모양, 색 또는 스마트 도킹 표식의 모양 사용자 지정 하려는 경우이 메서드를 호출 합니다.  
  
 스마트 도킹 표식의 기본 모양이 사용 하려면 초기화 되지 않은 인스턴스를 전달 [CSmartDockingInfo 클래스](../../mfc/reference/csmartdockinginfo-class.md) 를 `params`합니다.  
  
##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames  
 표시 하거나 미니 프레임 창을 숨깁니다.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 `TRUE` 표시 된 프레임의 창; 활성화 하려면 `FALSE to` 프레임 창을 숨깁니다.  
  
##  <a name="showpanes"></a>  CDockingManager::ShowPanes  
 표시 하거나 제어 및 자동 숨기기 막대의 창을 숨깁니다.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 `TRUE` 창을 표시 하 여; `FALSE to` 창을 숨깁니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE`입니다.  
  
##  <a name="startsdocking"></a>  CDockingManager::StartSDocking  
 스마트 도킹 관리자의 맞춤에 따라 지정 된 창의 스마트 도킹을 시작 합니다.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDockingWnd`  
 도킹 창에 대 한 포인터입니다.  
  
##  <a name="stopsdocking"></a>  CDockingManager::StopSDocking  
 중지 스마트 도킹 합니다.  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>  CDockingManager::GetSmartDockingTheme  
 스마트 도킹 표식을 표시 하는 데 사용 되는 테마를 반환 하는 정적 메서드.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>반환 값  
 다음 열거형된 값 중 하나를 반환 합니다: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008 합니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)
