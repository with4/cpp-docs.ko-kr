---
title: "CDockablePane 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePane
- AFXDOCKABLEPANE/CDockablePane
- AFXDOCKABLEPANE/CDockablePane::CDockablePane
- AFXDOCKABLEPANE/CDockablePane::AttachToTabWnd
- AFXDOCKABLEPANE/CDockablePane::CalcFixedLayout
- AFXDOCKABLEPANE/CDockablePane::CanAcceptMiniFrame
- AFXDOCKABLEPANE/CDockablePane::CanAcceptPane
- AFXDOCKABLEPANE/CDockablePane::CanAutoHide
- AFXDOCKABLEPANE/CDockablePane::CanBeAttached
- AFXDOCKABLEPANE/CDockablePane::ConvertToTabbedDocument
- AFXDOCKABLEPANE/CDockablePane::CopyState
- AFXDOCKABLEPANE/CDockablePane::Create
- AFXDOCKABLEPANE/CDockablePane::CreateDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::CreateEx
- AFXDOCKABLEPANE/CDockablePane::CreateTabbedPane
- AFXDOCKABLEPANE/CDockablePane::DockPaneContainer
- AFXDOCKABLEPANE/CDockablePane::DockPaneStandard
- AFXDOCKABLEPANE/CDockablePane::DockToRecentPos
- AFXDOCKABLEPANE/CDockablePane::DockToWindow
- AFXDOCKABLEPANE/CDockablePane::EnableAutohideAll
- AFXDOCKABLEPANE/CDockablePane::EnableGripper
- AFXDOCKABLEPANE/CDockablePane::GetAHRestoredRect
- AFXDOCKABLEPANE/CDockablePane::GetAHSlideMode
- AFXDOCKABLEPANE/CDockablePane::GetCaptionHeight
- AFXDOCKABLEPANE/CDockablePane::GetDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::GetDockingStatus
- AFXDOCKABLEPANE/CDockablePane::GetDragSensitivity
- AFXDOCKABLEPANE/CDockablePane::GetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::GetTabArea
- AFXDOCKABLEPANE/CDockablePane::GetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::HasAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::HitTest
- AFXDOCKABLEPANE/CDockablePane::IsAutohideAllEnabled
- AFXDOCKABLEPANE/CDockablePane::IsAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsDocked
- AFXDOCKABLEPANE/CDockablePane::IsHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsInFloatingMultiPaneFrameWnd
- AFXDOCKABLEPANE/CDockablePane::IsResizable
- AFXDOCKABLEPANE/CDockablePane::IsTabLocationBottom
- AFXDOCKABLEPANE/CDockablePane::IsTracked
- AFXDOCKABLEPANE/CDockablePane::IsVisible
- AFXDOCKABLEPANE/CDockablePane::OnAfterChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnAfterDockFromMiniFrame
- AFXDOCKABLEPANE/CDockablePane::OnBeforeChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnBeforeFloat
- AFXDOCKABLEPANE/CDockablePane::RemoveFromDefaultPaneDividier
- AFXDOCKABLEPANE/CDockablePane::ReplacePane
- AFXDOCKABLEPANE/CDockablePane::RestoreDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideParents
- AFXDOCKABLEPANE/CDockablePane::SetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::SetRestoredDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::ShowPane
- AFXDOCKABLEPANE/CDockablePane::Slide
- AFXDOCKABLEPANE/CDockablePane::ToggleAutoHide
- AFXDOCKABLEPANE/CDockablePane::UndockPane
- AFXDOCKABLEPANE/CDockablePane::CheckAutoHideCondition
- AFXDOCKABLEPANE/CDockablePane::CheckStopSlideCondition
- AFXDOCKABLEPANE/CDockablePane::DrawCaption
- AFXDOCKABLEPANE/CDockablePane::OnPressButtons
- AFXDOCKABLEPANE/CDockablePane::OnSlide
- AFXDOCKABLEPANE/CDockablePane::m_bDisableAnimation
- AFXDOCKABLEPANE/CDockablePane::m_bHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::m_nSlideSteps
dev_langs:
- C++
helpviewer_keywords:
- CDockablePane [MFC], CDockablePane
- CDockablePane [MFC], AttachToTabWnd
- CDockablePane [MFC], CalcFixedLayout
- CDockablePane [MFC], CanAcceptMiniFrame
- CDockablePane [MFC], CanAcceptPane
- CDockablePane [MFC], CanAutoHide
- CDockablePane [MFC], CanBeAttached
- CDockablePane [MFC], ConvertToTabbedDocument
- CDockablePane [MFC], CopyState
- CDockablePane [MFC], Create
- CDockablePane [MFC], CreateDefaultPaneDivider
- CDockablePane [MFC], CreateEx
- CDockablePane [MFC], CreateTabbedPane
- CDockablePane [MFC], DockPaneContainer
- CDockablePane [MFC], DockPaneStandard
- CDockablePane [MFC], DockToRecentPos
- CDockablePane [MFC], DockToWindow
- CDockablePane [MFC], EnableAutohideAll
- CDockablePane [MFC], EnableGripper
- CDockablePane [MFC], GetAHRestoredRect
- CDockablePane [MFC], GetAHSlideMode
- CDockablePane [MFC], GetCaptionHeight
- CDockablePane [MFC], GetDefaultPaneDivider
- CDockablePane [MFC], GetDockingStatus
- CDockablePane [MFC], GetDragSensitivity
- CDockablePane [MFC], GetLastPercentInPaneContainer
- CDockablePane [MFC], GetTabArea
- CDockablePane [MFC], GetTabbedPaneRTC
- CDockablePane [MFC], HasAutoHideMode
- CDockablePane [MFC], HitTest
- CDockablePane [MFC], IsAutohideAllEnabled
- CDockablePane [MFC], IsAutoHideMode
- CDockablePane [MFC], IsDocked
- CDockablePane [MFC], IsHideInAutoHideMode
- CDockablePane [MFC], IsInFloatingMultiPaneFrameWnd
- CDockablePane [MFC], IsResizable
- CDockablePane [MFC], IsTabLocationBottom
- CDockablePane [MFC], IsTracked
- CDockablePane [MFC], IsVisible
- CDockablePane [MFC], OnAfterChangeParent
- CDockablePane [MFC], OnAfterDockFromMiniFrame
- CDockablePane [MFC], OnBeforeChangeParent
- CDockablePane [MFC], OnBeforeFloat
- CDockablePane [MFC], RemoveFromDefaultPaneDividier
- CDockablePane [MFC], ReplacePane
- CDockablePane [MFC], RestoreDefaultPaneDivider
- CDockablePane [MFC], SetAutoHideMode
- CDockablePane [MFC], SetAutoHideParents
- CDockablePane [MFC], SetLastPercentInPaneContainer
- CDockablePane [MFC], SetRestoredDefaultPaneDivider
- CDockablePane [MFC], SetTabbedPaneRTC
- CDockablePane [MFC], ShowPane
- CDockablePane [MFC], Slide
- CDockablePane [MFC], ToggleAutoHide
- CDockablePane [MFC], UndockPane
- CDockablePane [MFC], CheckAutoHideCondition
- CDockablePane [MFC], CheckStopSlideCondition
- CDockablePane [MFC], DrawCaption
- CDockablePane [MFC], OnPressButtons
- CDockablePane [MFC], OnSlide
- CDockablePane [MFC], m_bDisableAnimation
- CDockablePane [MFC], m_bHideInAutoHideMode
- CDockablePane [MFC], m_nSlideSteps
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb32fc827c576830def3901389d400450b79f5ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdockablepane-class"></a>CDockablePane Class
도킹 사이트에 도킹되거나 탭 창에 포함될 수 있는 창을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|`CDockablePane` 개체를 생성하고 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](#attachtotabwnd)|창을 다른 창으로 연결합니다. 이렇게 하면 탭된 창을 만들어집니다.|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|창 사각형의 크기를 반환합니다.|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|지정된 된 미니 프레임 창으로 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|다른 창에서 현재 창으로 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::CanAutoHide](#canautohide)|창 자동 숨기기 모드를 지원 하는지 여부를 결정 합니다. (재정의 [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|현재 창을 다른 창에 도킹할 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.|  
|[CDockablePane::CopyState](#copystate)|도킹 가능한 창 상태를 복사합니다.|  
|[CDockablePane::Create](#create)|Windows 컨트롤을 만들고에 연결 된 `CDockablePane` 개체입니다.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|프레임 창으로 도킹 창에 대 한 기본 구분선을 만듭니다.|  
|[Cdockablepane:: Createex](#createex)|Windows 컨트롤을 만들고에 연결 된 `CDockablePane` 개체입니다.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|현재 창에서 탭된 창을 만듭니다.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|컨테이너에서 창으로 도킹합니다.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|개요 (표준) 도킹을 사용 하 여 창을 도킹 합니다.|  
|`CDockablePane::DockToFrameWindow`|내부적으로 사용 합니다. 사용 하 여 창의 고정 하려면 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) 또는 [CDockablePane::DockToWindow](#docktowindow)합니다.|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|저장 된 최근의 도킹 위치로 창을 도킹합니다.|  
|[CDockablePane::DockToWindow](#docktowindow)|하나의 도킹 창을 다른 도킹 창으로 도킹합니다.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|컨테이너에 있는 다른 창와 함께이 창에 대 한 자동 숨기기 모드를 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CDockablePane::EnableGripper](#enablegripper)|표시 하거나 숨깁니다. 캡션 (그리퍼).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|창 자동 숨기기 모드로 표시 되었을 때의 위치를 지정 합니다.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|창에 대 한 자동 숨기기 슬라이드 모드를 검색합니다.|  
|`CDockablePane::GetAutoHideButton`|내부적으로 사용 합니다.|  
|`CDockablePane::GetAutoHideToolBar`|내부적으로 사용 합니다.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|현재 캡션의 높이 반환합니다.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|컨테이너의 창에 대 한 기본 창 구분선을 반환합니다.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|창 도킹 될 하는 기능은 제공 된 포인터 위치에 따라 결정 합니다.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|도킹 창 끌어서 민감도 반환합니다.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|해당 컨테이너 내에서 창을 차지 하는 공간의 백분율을 검색 합니다.|  
|[CDockablePane::GetTabArea](#gettabarea)|창에 대 한 탭 영역을 검색합니다.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|다른 창에서 현재 창으로 도킹 시 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 반환 합니다.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|도킹 창을 자동 숨기기 모드로 전환할 수 수 있는지 여부를 지정 합니다.|  
|[CDockablePane::HitTest](#hittest)|사용자가 마우스를 클릭 하는 창에서 특정 위치를 지정 합니다.|  
|`CDockablePane::IsAccessibilityCompatible`|내부적으로 사용 합니다.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|도킹 창 및 컨테이너에 있는 다른 모든 창 자동 숨기기 모드로 전환할 수 있는지 여부를 나타냅니다.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|창을 자동 숨기기 모드 인지 여부를 결정 합니다.|  
|`CDockablePane::IsChangeState`|내부적으로 사용 합니다.|  
|[CDockablePane::IsDocked](#isdocked)|현재 창 도킹 되는지 여부를 결정 합니다.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|경우 표시 된 (숨겨진)를 호출 하 여 자동 숨기기 모드에 있는 창의 동작을 결정 `ShowPane`합니다.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|다중 창 프레임 창에는 창이 되는지 여부를 지정 합니다.|  
|[CDockablePane::IsResizable](#isresizable)|창 크기를 조정할 수 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|탭이 맨 위 또는 맨 아래 창에 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsTracked](#istracked)|사용자가 창을 끌어온 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsVisible](#isvisible)|현재 창이 표시 되는지를 결정 합니다.|  
|[Cdockablepane:: Loadstate](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|내부적으로 사용 합니다.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|부모 창의 변경 될 때 프레임 워크에서 호출 됩니다. (재정의 [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|프레임 창에는 부동 도킹 모음 도킹 프레임 워크에서 호출 됩니다.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|부모 창의 변경 되려고 할 때 프레임 워크에서 호출 됩니다. (재정의 [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Float에 대 한이 되 면 프레임 워크에서 호출 됩니다. (재정의 [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|프레임 워크 창을 도킹 되는 경우이 메서드를 호출 합니다.|  
|[CDockablePane::ReplacePane](#replacepane)|창에서 지정 된 창으로 대체합니다.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|기본 창 구분선을 복원 하는 창을 역직렬화 할 때이 메서드를 호출 하는 프레임 워크입니다.|  
|`CDockablePane::SaveState`|내부적으로 사용 합니다.|  
|`CDockablePane::Serialize`|창을 serialize합니다. (`CBasePane::Serialize`를 재정의합니다.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|표시 사이의 도킹 창을 설정/해제 및 자동 숨기기 모드입니다.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|자동 숨기기 단추를 설정 하는 창에 대 한 자동 숨기기 도구 모음입니다.|  
|`CDockablePane::SetDefaultPaneDivider`|내부적으로 사용 합니다.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|해당 컨테이너 내에서 창을 차지 하는 공간의 백분율을 설정 합니다.|  
|`CDockablePane::SetResizeMode`|내부적으로 사용 합니다.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|복원 된 기본 창 구분선을 설정합니다.|  
|[Cdockablepane:: Settabbedpanertc](#settabbedpanertc)|두 개의 창이 도킹 함께 때 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 설정 합니다.|  
|[CDockablePane::ShowPane](#showpane)|표시 하거나 창을 숨깁니다.|  
|[CDockablePane::Slide](#slide)|표시 하거나 창 자동 숨기기 모드에 있을 때만 표시 하는 슬라이딩 애니메이션으로 창을 숨깁니다.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|자동 숨기기 모드를 설정/해제 합니다. (재정의 [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|주 프레임 창 또는 미니 프레임 창 컨테이너에서 창을 도킹이 해제 되어 있습니다.|  
|`CDockablePane::UnSetAutoHideMode`|내부적으로 사용 합니다. 자동 숨기기 모드를 설정 하려면 [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|도킹 창 자동 숨김 모드에서 숨겨지는지 여부를 결정 합니다.|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|슬라이딩 자동 숨김 도킹 창의 중지 시기를 결정 합니다.|  
|[CDockablePane::DrawCaption](#drawcaption)|도킹 창의 캡션 (그리퍼)를 그립니다.|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|사용자가 아닌 다른 캡션 단추를 누를 때 호출 된 `AFX_HTCLOSE` 및 `AFX_HTMAXBUTTON` 단추입니다.|  
|[CDockablePane::OnSlide](#onslide)|창에서 표시 되거나 숨겨진 때 자동 숨기기 슬라이드 효과가 렌더링 하기 위해 프레임 워크에서 호출 됩니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|도킹 가능한 창 자동 숨기기 애니메이션 되지 않는지 여부를 지정 합니다.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|창 자동 숨기기 모드에 있을 때 창의 동작을 결정 합니다.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|될 때 애니메이션 속도 창 지정 나타나거나 사라질 자동 숨기기 모드에 있을 때.|  
  
## <a name="remarks"></a>설명  
 `CDockablePane`다음과 같은 기능을 구현합니다.  
  
-   창을 주 프레임 창으로 도킹 합니다.  
  
-   창을 자동 숨기기 모드로 전환 합니다.  
  
-   창이 탭된 창에 연결 합니다.  
  
-   미니 프레임 창에서 창을 부동합니다.  
  
-   창을 부동 미니 프레임 창에는 다른 창으로 도킹 합니다.  
  
-   창 크기를 조정 합니다.  
  
-   로드 하 고 도킹 창에 대 한 상태를 저장 합니다.  
  
    > [!NOTE]
    >  상태 정보는 Windows 레지스트리에 저장 됩니다.  
  
-   캡션을 유무는 창 만들기 캡션 텍스트 레이블 수 있으며 그라데이션 색으로 채워질 수 있습니다.  
  
-   창의 내용을 표시 하는 동안 창을 끌어  
  
-   끌기 사각형을 표시 하는 동안 창을 끕니다.  
  
 도킹 창에서 응용 프로그램을 사용 하려면 창에서 파생 된 `CDockablePane` 클래스입니다. 주 프레임 창 개체 또는 사용자 창의 인스턴스를 제어 하는 창 개체에 파생된 개체를 포함 하는 중 다음 호출에서 [CDockablePane::Create](#create) 메서드 또는 [cdockablepane:: Createex](#createex) 처리 하는 경우 메서드는 `WM_CREATE` 주 프레임 창에 메시지입니다. 마지막으로 호출 하 여 창 개체를 설정 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [cbasepane:: Dockpane](../../mfc/reference/cbasepane-class.md#dockpane), 또는 [CDockablePane::AttachToTabWnd](#attachtotabwnd)합니다.  
  
## <a name="customization-tips"></a>사용자 지정 팁  
 다음 팁에 적용 `CDockablePane` 개체:  
  
-   호출 하는 경우 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 두 탭, 도킹 가능한 창이 탭된 창에 대 한 포인터에 반환 됩니다는 `ppTabbedControlBar` 매개 변수입니다. 이 매개 변수를 사용 하 여 탭된 창에 탭을 추가 하려면 계속 수 있습니다.  
  
-   탭된 창에 의해 만들어진 유형의 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 에 의해 결정 됩니다는 `CDockablePane` 개체는 `pTabControlBarAttachTo` 매개 변수입니다. 호출할 수 있습니다 [cdockablepane:: Settabbedpanertc](#settabbedpanertc) 에 탭된 창의 종류를 설정의 `CDockablePane` 만들어집니다. 기본 형식은에 의해 결정 됩니다는 `dwTabbedStyle` 의 [CDockablePane::Create](#create) 처음 만들 때의 `CDockablePane`합니다. 경우 `dwTabbedStyle` 은 기본 형식이 AFX_CBRS_OUTLOOK_TABS [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)경우 `dwTabbedStyle` 은 기본 형식이 AFX_CBRS_REGULAR_TABS [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
-   다른 한 도킹 가능한 창을 도킹 하려면 호출는 [CDockablePane::DockToWindow](#docktowindow) 메서드. 원래 창 도킹 해야 합니다 곳이 메서드를 호출 하기 전에.  
  
-   멤버 변수 [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) 컨트롤 도킹 가능한 창을 자동으로 작동 하는 방법 숨기기 모드를 호출할 때 [CDockablePane::ShowPane](#showpane)합니다. 이 멤버 변수 설정 된 경우 `TRUE`, 도킹 가능한 창 및 해당 자동 숨기기 단추는 숨겨집니다. 그렇지 않으면 이러한 됩니다 슬라이드 / 로그 아웃 합니다.  
  
-   자동 숨기기 애니메이션을 사용 하지 않도록 설정 하 여 수는 [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) 멤버 변수를 `TRUE`합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 구성 하는 `CDockablePane` 에서 다양 한 메서드를 사용 하 여 개체는 `CDockablePane` 클래스입니다. 이 예제에서는 자동 숨김 도킹 가능한 창에 대 한 모든 기능을 활성화, 캡션 또는 위치 조정 막대를 사용 하도록 설정, 자동 숨기기 모드를 사용 하도록 설정, 창을 표시 및 자동 숨기기 모드에 있는 창에 애니메이션을 적용 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>CDockablePane::AttachToTabWnd  
 현재 창 탭된 창을 만드는 대상 창에서 연결 합니다.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pTabControlBarAttachTo`  
 현재 창에 연결 하는 대상 창을 지정 합니다. 대상 창 도킹 가능한 창 이어야 합니다.  
  
 [in] `dockMethod`  
 도킹 방법을 지정합니다.  
  
 [in] `bSetActive`  
 `TRUE`연결 작업; 후 탭된 창을 활성화 하려면 그렇지 않으면 `FALSE`합니다.  
  
 [out] `ppTabbedControlBar`  
 연결 작업의 결과로 생성 되는 탭된 창에 포함 되어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 탭된 창; 없으면 현재 창에 대 한 포인터 그렇지 않은 경우 연결 작업의 결과로 생성 되는 탭된 창에 대 한 포인터입니다. 반환 값은 `NULL` 현재 창에 연결할 수 없습니다, 또는 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 하나의 도킹 가능한 창에이 메서드를 사용 하 여 다른 창을 연결할 때 결과 다음과 같습니다.  
  
1.  Framework 검사 하는지 여부를 대상 창 `pTabControlBarAttachTo` 은 일반 도킹 창 이거나에서 파생 된 경우 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)합니다.  
  
2.  대상 창은 탭된 창, 프레임 워크는 탭으로 현재 창에 추가 합니다.  
  
3.  대상 창 도킹 창을 일반 이면 프레임 워크는 탭된 창을 만듭니다.  
  
    -   프레임 워크를 호출 하 여 `pTabControlBarAttachTo->CreateTabbedPane`합니다. 새 탭된 창 스타일에 따라 달라 집니다는 `m_pTabbedControlBarRTC` 멤버입니다. 기본적으로이 멤버의 런타임 클래스에 설정 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)합니다. 전달 하는 경우는 `AFX_CBRS_OUTLOOK_TABS` 스타일로 된 `dwTabbedStyle` 매개 변수를는 [CDockablePane::Create](#create) 방법은, 런타임 클래스 개체의 런타임 클래스로 설정 되어 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)합니다. 이 멤버는 언제 든 지 새 창의 스타일을 변경 하려면 변경할 수 있습니다.  
  
    -   이 메서드가 만들고는 탭된 창, 프레임 워크에 대 한 포인터를 대체 `pTabControlBarAttachTo` (창이 않는 경우 도킹 또는 부동 다중 미니 프레임 창에서) 새 탭된 창에 대 한 포인터입니다.  
  
    -   추가 하는 프레임 워크는 `pTabControlBarAttachTo` 창으로 첫 번째 탭에서 탭된 창으로 합니다. 프레임 워크는 다음 두 번째 탭으로 현재 창을 추가합니다.  
  
4.  현재 창에서 파생 된 경우 `CBaseTabbedPane`, 모두의 탭으로 이동 됩니다 `pTabControlBarAttachTo` 현재 창 소멸 됩니다. 따라서이 메서드를 호출할 때 때문에 기해야 메서드가 반환 될 때 현재 창에 대 한 포인터 유효할 수 있습니다.  
  
 도킹 레이아웃을 만들 때 다른 하나의 창 연결 하는 경우 설정 `dockMethod` 를 `DM_SHOW`합니다.  
  
 다른 창에 연결 하기 전에 첫 번째 창을 도킹 해야 합니다.  
  
##  <a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
 창 사각형의 크기를 반환합니다.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bStretch`  
 사용되지 않습니다.  
  
 [in] `bHorz`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 A `CSize` 창 사각형의 크기를 포함 하는 개체입니다.  
  
##  <a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 지정된 된 미니 프레임 창으로 도킹 될 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMiniFrame`  
 `CPaneFrameWnd` 개체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 `pMiniFrame` 창으로 도킹 되지 않으면, `FALSE`합니다.  
  
##  <a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 다른 창에서 현재 창으로 도킹 될 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 현재 창으로 도킹 창을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정 된 창;이 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는 창이 현재 창에 도킹 되어 전에이 메서드를 호출 합니다.  
  
 특정 창으로 도킹을 사용 하지 않도록 설정 하거나 설정 하려면 파생된 클래스에서이 함수를 재정의 합니다.  
  
 기본적으로이 메서드는 다음과 같이 반환 됩니다. `TRUE` 경우 `pBar` 부모 형식이 아니거나 `CDockablePane`합니다.  
  
##  <a name="canautohide"></a>CDockablePane::CanAutoHide  
 여부의 창 수 자동 숨기기를 결정 합니다.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 수 자동 숨기기 경우; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 `CDockablePane::CanAutoHide`반환 `FALSE` 다음과 같은 상황 중 하나에서:  
  
-   창에 부모가 없습니다.  
  
-   도킹 관리자 창을 자동 숨기기를 허용 하지 않습니다.  
  
-   창 도킹 되지 않습니다.  
  
##  <a name="canbeattached"></a>CDockablePane::CanBeAttached  
 현재 창을 다른 창에 도킹할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창을 다른 창으로 나 주 프레임 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드는 항상 반환 `TRUE`합니다. 이 메서드를 호출 하지 않고 도킹을 사용할지 파생된 클래스에서 재정의 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)합니다.  
  
##  <a name="cdockablepane"></a>CDockablePane::CDockablePane  
 생성 하 고 초기화는 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창 개체를 생성 한 후 호출 [CDockablePane::Create](#create) 또는 [cdockablepane:: Createex](#createex) 를 만듭니다.  
  
##  <a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActiveTabOnly`  
 변환 하는 경우는 `CTabbedPane`, 지정 `TRUE` 활성 탭만 변환 합니다. 지정 `FALSE` 창에서 모든 탭을 변환할 수 있습니다.  
  
##  <a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 도킹 창 (자동 숨기기 모드 라고도 함) 숨겨져 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`숨기기 조건이 충족 됩니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는 타이머를 사용 하 여 정기적으로 숨기기 autohide 도킹 가능한 창 것인지 확인. 메서드가 반환 `TRUE` 는 창이 활성화 되지 않으면, 창에서 조정 되지 않습니다 마우스 포인터가 없는 경우 창 위에 있습니다.  
  
 프레임 워크를 호출 하는 모든 이전 조건이 충족 되 면 [CDockablePane::Slide](#slide) 창을 숨기려면 합니다.  
  
##  <a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 시기는 자동 숨기기 도킹 창 슬라이딩 중지 하도록 결정 합니다.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDirection`  
 `TRUE`창에서 표시 되 면 `FALSE` 경우 있는 창이 사라집니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`stop 조건이 충족 될; 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창 자동 숨기기 모드로 설정 되 면 프레임 워크를 사용 하 여 슬라이딩 효과 창을 표시 하거나 숨깁니다. 프레임 워크의 창 슬라이딩는 경우이 함수를 호출 합니다. `CheckStopSlideCondition`반환 `TRUE` 창에서 완전히 표시 된 경우 또는 완전히으로 숨겨집니다.  
  
 사용자 지정 자동 숨기기 효과 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="copystate"></a>CDockablePane::CopyState  
 도킹 가능한 창 상태를 복사합니다.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOrgBar`  
 도킹 가능한 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `CDockablePane::CopyState`상태를 복사 `pOrgBar` 다음 메서드를 호출 하 여 현재 창:  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>CDockablePane::Create  
 Windows 컨트롤을 만들고에 연결 된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);

 
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    CSize sizeDefault,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle = WS_CHILD|WS_VISIBLE|CBRS_TOP|CBRS_HIDE_INPLACE,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszCaption`  
 창 이름을 지정합니다.  
  
 [in] [out]`pParentWnd`  
 부모 창을 지정합니다.  
  
 [in] `rect`  
 클라이언트 좌표에서 창의 위치와 크기 지정 `pParentWnd`합니다.  
  
 [in] `bHasGripper`  
 `TRUE`캡션; 사용 하 여 창을 만들려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `nID`  
 자식 창 ID를 지정합니다. 이 값이 도킹 창에 대 한 도킹 상태를 저장 하려는 경우에 고유 해야 합니다.  
  
 [in] `dwStyle`  
 창 스타일 특성을 지정합니다.  
  
 [in] `dwTabbedStyle`  
 사용자가이 창의 캡션을 창을 끌 때 만들어지는 탭된 창의 탭된 스타일을 지정 합니다.  
  
 [in] `dwControlBarStyle`  
 다른 스타일 특성을 지정합니다.  
  
 [in] [out]`pContext`  
 창 만들기 컨텍스트를 지정합니다.  
  
 [in] `lpszWindowName`  
 창 이름을 지정합니다.  
  
 [in] `sizeDefault`  
 창의 크기를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 성공적으로 만들어지면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 Windows 창을 만들고 연결 하는 `CDockablePane` 개체입니다.  
  
 경우는 `dwStyle` 창 스타일에는 `CBRS_FLOAT_MULTI` 플래그를 미니 프레임 창을 미니 프레임 창에 있는 다른 창으로 배치할 수 있습니다. 기본적으로 창이 도킹 수만 부동 소수점 개별적으로 합니다.  
  
 경우는 `dwTabbedStyle` 매개 변수에 `AFX_CBRS_OUTLOOK_TABS` 창에서 다른 창을 사용 하 여이 창에 연결 될 때 Outlook 스타일 탭 창을 만드는 플래그를 지정 된 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드. 기본적으로 도킹 가능한 창을 만들 형식의 일반 탭된 창 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
##  <a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 프레임 창으로 도킹 창에 대 한 기본 구분선을 만듭니다.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 주 프레임 창에서 도킹 되의 가장자리를 지정 합니다. 경우 `dwAlignment` 포함는 `CBRS_ALIGN_LEFT` 또는 `CBRS_ALIGN_RIGHT` 플래그,이 메서드가 만드는 세로 ( `CPaneDivider::SS_VERT`) 구분선; 그렇지 않으면이 메서드가 만드는 가로 ( `CPaneDivider::SS_HORZ`) 구분선입니다.  
  
 [in] `pParent`  
 부모 프레임에 대 한 포인터입니다.  
  
 [in] `pSliderRTC`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 새로 만든 구분선에 대 한 포인터를 반환 하거나 `NULL` 구분선 만들기가 실패 하는 경우.  
  
### <a name="remarks"></a>설명  
 `dwAlignment`다음 값 중 하나일 수 있습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|창은 프레임 창의 클라이언트 영역의 위쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_BOTTOM`|창은 프레임 창의 클라이언트 영역 아래쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_LEFT`|창은 프레임 창의 클라이언트 영역의 왼쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_RIGHT`|창은 프레임 창의 클라이언트 영역의 오른쪽에 도킹 되 고 됩니다.|  
  
##  <a name="createex"></a>Cdockablepane:: Createex  
 Windows 컨트롤을 만들고에 연결 된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwStyleEx`  
 새 창에 대 한 확장 된 스타일 특성을 지정합니다.  
  
 [in] `lpszCaption`  
 창 이름을 지정합니다.  
  
 [in] [out]`pParentWnd`  
 부모 창을 지정합니다.  
  
 [in] `rect`  
 클라이언트 좌표에서 창의 위치와 크기 지정 `pParentWnd`합니다.  
  
 [in] `bHasGripper`  
 `TRUE`캡션; 사용 하 여 창을 만들려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `nID`  
 자식 창 ID를 지정합니다. 이 값이 도킹 창에 대 한 도킹 상태를 저장 하려는 경우에 고유 해야 합니다.  
  
 [in] `dwStyle`  
 창 스타일 특성을 지정합니다.  
  
 [in] `dwTabbedStyle`  
 사용자가이 창의 캡션을 창을 끌 때 만들어지는 탭된 창의 탭된 스타일을 지정 합니다.  
  
 [in] `dwControlBarStyle`  
 다른 스타일 특성을 지정합니다.  
  
 [in] [out]`pContext`  
 창 만들기 컨텍스트를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 성공적으로 만들어지면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 Windows 창을 만들고 연결 하는 `CDockablePane` 개체입니다.  
  
 경우는 `dwStyle` 창 스타일에는 `CBRS_FLOAT_MULTI` 플래그를 미니 프레임 창을 미니 프레임 창에 있는 다른 창으로 배치할 수 있습니다. 기본적으로 창이 도킹 수만 부동 소수점 개별적으로 합니다.  
  
 경우는 `dwTabbedStyle` 매개 변수에 `AFX_CBRS_OUTLOOK_TABS` 창에서 다른 창을 사용 하 여이 창에 연결 될 때 Outlook 스타일 탭 창을 만드는 플래그를 지정 된 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드. 기본적으로 도킹 가능한 창을 만들 형식의 일반 탭된 창 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
##  <a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 현재 창에서 탭된 창을 만듭니다.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>반환 값  
 새 탭된 창 또는 `NULL` 만들기 작업이 실패 한 경우.  
  
### <a name="remarks"></a>설명  
 프레임 워크는이 창을 대체 하는 탭된 창을 만들 때이 메서드를 호출 합니다. 자세한 내용은 참조 [CDockablePane::AttachToTabWnd](#attachtotabwnd)합니다.  
  
 이 방법을 어떻게 탭된 창을 사용자 지정 하려면 파생된 클래스에서 생성 되 고 초기화를 재정의 합니다.  
  
 탭된 창에 저장 된 런타임 클래스 정보에 따라 생성 되는 `m_pTabbedControlBarRTC` 하 여 초기화 된 멤버는 [cdockablepane:: Createex](#createex) 메서드.  
  
##  <a name="dockpanecontainer"></a>CDockablePane::DockPaneContainer  
 컨테이너에서 창으로 도킹합니다.  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `barContainerManager`  
 도킹 되 고 있는 컨테이너의 컨테이너 관리자에 대 한 참조입니다.  
  
 [in] `dwAlignment`  
 `DWORD`컨테이너는 도킹 창 옆쪽에 지정 하는 합니다.  
  
 [in] `dockMethod`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`컨테이너의 창; 도킹 되어 성공적으로 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 `dwAlignment`다음 값 중 하나일 수 있습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|컨테이너 창 위쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_BOTTOM`|컨테이너 창 아래쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_LEFT`|컨테이너 창의 왼쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_RIGHT`|컨테이너 창의 오른쪽에 도킹 되 고 됩니다.|  
  
##  <a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 개요 (표준) 도킹을 사용 하 여 창을 도킹 합니다.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bWasDocked`  
 메서드가 반환 될 때이 값 포함 `TRUE` 포함 된 창 했으면 성공적으로 도킹, `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 탭된 창으로 도킹 되어 창 또는 탭된 창 도킹 결과로 생성 된 경우이 메서드는 탭된 창에 대 한 포인터를 반환 합니다. 이 메서드가 반환 하는 경우 창에서를 그렇지 않으면 성공적으로 도킹 된 `this` 포인터입니다. 이 메서드가 반환 실패 한 경우 도킹 `NULL`합니다.  
  
##  <a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 저장 된 도킹 위치로 창을 도킹합니다.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 도킹 되어 있는 성공적으로; 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창에서 최근의 도킹 정보를 저장 한 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) 개체입니다.  
  
##  <a name="docktowindow"></a>CDockablePane::DockToWindow  
 하나의 도킹 창을 다른 도킹 창으로 도킹합니다.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pTargetWindow`  
 도킹 가능한 창에이 창을 도킹 하려면를 지정 합니다.  
  
 [in] `dwAlignment`  
 창에 대 한 도킹 맞춤을 지정합니다. CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM 또는 CBRS_ALIGN_ANY 중 하나일 수 있습니다. (Afxres.h에 정의).  
  
 [in] `lpRect`  
 창에 대 한 도킹 사각형을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 성공적으로; 도킹 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 로 지정 된 맞춤으로 한 창을 다른 창으로 도킹 하려면이 메서드를 호출 `dwAlignment`합니다.  
  
##  <a name="drawcaption"></a>CDockablePane::DrawCaption  
 도킹 창의 캡션 (그리퍼 라고도 함)를 그립니다.  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 그리기에 사용 되는 장치 컨텍스트를 나타냅니다.  
  
 [in] `rectCaption`  
 창 캡션의 경계 사각형을 지정합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크의 도킹 가능한 창 캡션을 그리도록이 메서드를 호출 합니다.  
  
 캡션 모양을 사용자 지정 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 이 창에 대 한 및 컨테이너에 있는 다른 창에 대 한 자동 숨기기 모드를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`자동 숨기기 도킹 가능한 창;에 대 한 모든 기능을 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 사용자는 경우 보유는 `Ctrl` 키 및 창을 동일한 컨테이너에 있는 모든 다른 창 자동 숨기기 모드로 전환 하려면 핀 단추는 또한 자동 숨기기 모드로 전환할 클릭 합니다.  
  
 이 메서드를 호출 `bEnable` 로 설정 `FALSE` 특정 창에 대 한이 기능을 해제할 수 있습니다.  
  
##  <a name="enablegripper"></a>CDockablePane::EnableGripper  
 표시 하거나 숨깁니다 (그리퍼 라고도 함) 캡션입니다.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`캡션;를 사용 하도록 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크 도킹 가능한 창 만들면 갖지 않습니다는 **WS_STYLE** 창 스타일을 지정 하는 경우에 마찬가지입니다. 이 영역 표준 창 캡션에는 다른 지 창의 캡션이 되는 프레임 워크에 의해 제어 되는 비클라이언트 영역을 의미 합니다.  
  
 표시 하거나 언제 든 지 캡션을 숨길 수 있습니다. 창이 탭된 창 또는 미니 프레임 창의 움직이는 창을 탭으로 추가 될 때 프레임 워크 캡션을 숨깁니다.  
  
##  <a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 자동 숨기기 모드에 있을 때 창 위치를 지정 합니다.  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 자동 숨기기 모드에 있을 때 창의 위치를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 창 자동 숨김 슬라이드 모드를 검색합니다.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `UINT` 창 자동 숨김 슬라이드 모드를 지정 하 합니다. 반환 값 `AFX_AHSM_MOVE` 또는 `AFX_AHSM_STRETCH`, 구현만 사용 하지만 `AFX_AHSM_MOVE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 현재 캡션의 픽셀 높이 반환합니다.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 캡션 높이입니다.  
  
### <a name="remarks"></a>설명  
 캡션을 의해 숨겨진 된 경우 캡션 높이 0에서 [CDockablePane::EnableGripper](#enablegripper) 메서드를 창 캡션이 없는 경우 또는 합니다.  
  
##  <a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 컨테이너의 창에 대 한 기본 창 구분선을 반환합니다.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>반환 값  
 유효한 [CPaneDivider](../../mfc/reference/cpanedivider-class.md) 개체는 도킹 가능한 창을 주 프레임 창에 도킹 되는 경우 또는 `NULL` 도킹 가능한 창이 도킹 되지 않은 경우 또는 부동 창인 것입니다.  
  
### <a name="remarks"></a>설명  
 창 구분선에 대 한 자세한 내용은 참조 [CPaneDivider 클래스](../../mfc/reference/cpanedivider-class.md)합니다.  
  
##  <a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 창 도킹 될 하는 기능은 제공 된 포인터 위치에 따라 결정 합니다.  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pt`  
 화면 좌표에서 포인터의 위치입니다.  
  
 [in] `nSensitivity`  
 거리 (픽셀) 사각형의 가장자리에서 포인터 도킹 사용할 수 있도록 이어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 다음과 같은 상태 값 중 하나입니다.  
  
|`AFX_CS_STATUS` 값|의미|  
|---------------------------|-------------|  
|`CS_NOTHING`|도킹 사이트를 통해는 포인터가 아닙니다. 프레임 워크 창을 도킹 하지 않습니다.|  
|`CS_DOCK_IMMEDIATELY`|포인터가 있는 위치에 도킹 사이트에 대해 직접 실행 모드에서 (창에서 사용 하 여는 `DT_IMMEDIATE` 도킹 모드). 프레임 워크는 즉시 창을 도킹 합니다.|  
|`CS_DELAY_DOCK`|포인터가 다른 도킹 창 또는 주 프레임 가장자리 가장 도킹 사이트 끝났습니다. 프레임 워크의 지연 후 창을 도킹 합니다. 이 지연에 대 한 자세한 내용은 설명 섹션을 참조 하십시오.|  
|`CS_DELAY_DOCK_TO_TAB`|창에 탭된 창에서 도킹 될 도킹 사이트 위에 포인터를 배치 합니다. 나는 탭된 창의 탭 영역을 다른 도킹 창의 캡션을 통해 포인터가 있는 경우 발생 합니다.|  
  
### <a name="remarks"></a>설명  
 프레임 워크 부동 창의 도킹을 처리 하려면이 메서드를 호출 합니다.  
  
 사용 하는 창을 도킹 하거나 부동 도구 모음에 대 한는 `DT_IMMEDIATE` 프레임 워크를 도킹 발생 하기 전에 창을 부모 프레임의 클라이언트 영역 밖으로 이동 하 여 사용자를 활성화 하는 도킹 명령 지연 모드를 도킹 합니다. 지연의 길이 밀리초 단위로 측정 및에 의해 제어 됩니다는 [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 데이터 멤버입니다. 기본값 [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 는 200 개입니다. 이 동작의 도킹 동작을 에뮬레이션 [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007입니다.  
  
 도킹 상태 지연에 대 한 ( `CS_DELAY_DOCK` 및 `CS_DELAY_DOCK_TO_TAB`), 사용자가 마우스 단추를 놓을 때까지 도킹 프레임 워크를 수행 하지 않습니다. 창을 사용 하는 경우는 `DT_STANDARD` 모드를 도킹 프레임 워크가 표시 사각형을 프로젝션 된 도킹 위치에 있습니다. 창을 사용 하는 경우는 `DT_SMART` 모드를 도킹 프레임 워크가 표시 스마트 도킹 마커 및 반투명 사각형 프로젝션 된 도킹 위치에 있습니다. 호출 하 여 창에 대 한 도킹 모드를 지정 하려면는 [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) 메서드. 스마트 도킹 하는 방법에 대 한 자세한 내용은 참조 [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams)합니다.  
  
##  <a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 도킹 창 끌어서 민감도 반환합니다.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 너비와 높이 (픽셀)는, 끌기 지점에 중심이 있는 사각형의 포함 된 개체입니다. 이 사각형 외부 마우스 포인터가 이동할 때까지 끌기 작업이 시작 되지 않습니다.  
  
##  <a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 해당 컨테이너의 창을 차지 하는 공간의 백분율 검색 ( [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `int` 해당 컨테이너의 창에서 차지 하는 공간의 백분율을 지정 하는 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 컨테이너의 레이아웃을 조정 하는 경우에 사용 됩니다.  
  
##  <a name="gettabarea"></a>CDockablePane::GetTabArea  
 창에 대 한 탭 영역을 검색합니다.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectTabAreaTop`  
 `GetTabArea`탭이 창의 위쪽에 있는 경우 탭 영역으로이 변수를 채웁니다. 탭 창의 맨 아래에 있는 경우이 변수는 빈 사각형 채워집니다.  
  
 [in] `rectTabAreaBottom`  
 `GetTabArea`탭 창의 맨 아래에 있는 경우 탭 영역으로이 변수를 채웁니다. 탭 창의 위쪽에 있는 경우이 변수는 빈 사각형 채워집니다.  
  
### <a name="remarks"></a>설명  
 파생 된 클래스에만이 메서드는 `CDockablePane` 탭이 나타나도록 하 고 있습니다. 자세한 내용은 참조 [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) 및 [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea)합니다.  
  
##  <a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 다른 창에서 현재 창으로 도킹 시 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 반환 합니다.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도킹 가능한 창에 대 한 런타임 클래스 정보입니다.  
  
### <a name="remarks"></a>설명  
 탭된 창 동적으로 만들어진에 대 한 런타임 클래스 정보를 검색 하려면이 메서드를 호출 합니다. 이 사용자가 단일 창을 다른 창의 캡션을 끌면 또는 호출 하는 경우 발생할 수 있습니다는 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드를 프로그래밍 방식으로 두 개의 도킹 가능한 창에서 탭된 창 만들기.  
  
 호출 하 여 런타임 클래스 정보를 설정할 수 있습니다는 [cdockablepane:: Settabbedpanertc](#settabbedpanertc) 메서드.  
  
##  <a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 도킹 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 자동 숨기기 모드를 전환할 수 있습니다 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 특정 도킹 가능한 창에 대 한 자동 숨기기 모드를 사용 하지 않도록 설정 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="hittest"></a>CDockablePane::HitTest  
 사용자가 마우스를 클릭 하는 창에서 위치를 지정 합니다.  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 테스트할 점의 지정 합니다.  
  
 [in] `bDetectCaption`  
 `TRUE`경우 `HTCAPTION` 포인터가 창의 캡션을;에 경우 반환 되어야 그렇지 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
- `HTNOWHERE`경우 `point` 이 도킹 가능한 창에 있습니다.  
  
- `HTCLIENT`경우 `point` 도킹 가능한 창의 클라이언트 영역에 있습니다.  
  
- `HTCAPTION`경우 `point` 도킹 가능한 창의 캡션 영역에 있습니다.  
  
- `AFX_HTCLOSE`경우 `point` 닫기 단추가 켜져 있습니다.  
  
- `HTMAXBUTTON`경우 `point` 고정 단추 켜져 있습니다.  
  
##  <a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 도킹 창 및 컨테이너에 있는 다른 모든 창에 자동 숨기기 모드로 전환할 수 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 및 컨테이너의 다른 모든 창 자동 숨기기 모드를 전환할 수 있는 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 누른 채 도킹 핀 단추를 클릭 하 여 자동 숨기기 모드를 활성화 하는 사용자는 **Ctrl** 키  
  
 를 사용 하거나이 동작을 사용 하지 않도록 설정 하려면 호출는 [CDockablePane::EnableAutohideAll](#enableautohideall) 메서드.  
  
##  <a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 창을 자동 숨기기 모드 인지 여부를 결정 합니다.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 자동 숨기기 모드; 이면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isdocked"></a>CDockablePane::IsDocked  
 현재 창 도킹 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`미니 프레임 창을 다른 창에는 부동 창인 또는 도킹 가능한 창 미니 프레임 창에 속해 있지 않습니다. `FALSE`표시 되는 미니 프레임 창의 자식 되어 미니 프레임 창에 속해 있는 다른 창이 없습니다.  
  
### <a name="remarks"></a>설명  
 창에서 주 프레임 창에 도킹 되는지 여부를 확인, 하려면 호출 [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)합니다. 메서드가 NULL이 아닌 포인터를 반환 하는 경우는 창은 주 프레임 창에 도킹 됩니다.  
  
##  <a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 경우 표시 된 (숨겨진)를 호출 하 여 자동 숨기기 모드에 있는 창의 동작을 결정 [CDockablePane::ShowPane](#showpane)합니다.  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 자동 숨기기 모드에 있을 때 숨겨야 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창 자동 숨기기 모드 이면 동작 다르게 호출 하는 경우 `ShowPane` 을 숨기 거 나 창을 표시 합니다. 이 동작은 정적 멤버에 의해 제어 됩니다 [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)합니다. 이 멤버는 경우 `TRUE`, 도킹 가능한 창 자동 숨기기 관련된 도구 모음 또는 자동 숨기기 단추를 표시 하거나 숨길를 호출할 때 `ShowPane`합니다. 그렇지 않으면 도킹 가능한 창을 활성화 또는 비활성화과 해당 관련된 autohide 도구 모음이 나 autohide 단추 항상 표시 됩니다.  
  
 개별 창에 대 한 기본 동작을 변경 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
 `m_bHideInAutoHideMode`의 기본값은 `FALSE`입니다.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 다중 창 프레임 창에는 창 인지를 지정 ( [CMultiPaneFrameWnd 클래스](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다중 창 프레임 창의 창이 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="isresizable"></a>CDockablePane::IsResizable  
 창 크기를 조정할 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 크기를 조정할 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 도킹 가능 창 크기를 조정할 수는 있습니다. 크기 조정를 방지 하려면 파생된 클래스에서이 메서드를 재정의 하 고 반환 `FALSE`합니다. 한 `FALSE` 값에 따라 실패 한 `ASSERT` 에 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)합니다. 사용 하 여 [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) 대신 부모 프레임 내에서 창을 도킹 하려면.  
  
 크기를 조정할 수 없는 창 둘 다를 수 있습니다 float 또는 자동 숨기기 모드를 입력 하 고, 부모 프레임의 바깥쪽 가장자리에 항상 나와 있습니다.  
  
##  <a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 탭이 맨 위 또는 맨 아래 창에 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 창; 맨 아래에 있는 경우 `FALSE` 탭이 창의 위쪽에 있는 경우.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom)합니다.  
  
##  <a name="istracked"></a>CDockablePane::IsTracked  
 사용자가 창을 이동 되 고 있는지 여부를 지정 합니다.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창; 이동 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isvisible"></a>CDockablePane::IsVisible  
 현재 창이 표시 되는지를 결정 합니다.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창에 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창을 표시 되는지 여부를 확인 하려면이 메서드를 호출 합니다. 이 메서드를 사용 하 여 호출 하는 대신 [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) 또는 대 한 테스트는 `WS_VISIBLE` 스타일입니다. 반환 된 표시 여부 상태에 따라 달라 집니다 자동 숨기기 모드의 활성화 여부의 값은 [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) 속성입니다.  
  
 도킹 가능한 창 자동 숨기기 모드에 있으면 및 `IsHideInAutoHideMode` 반환 `FALSE` 표시 여부 상태는 항상 `FALSE`합니다.  
  
 도킹 가능한 창 자동 숨기기 모드에 있으면 및 `IsHideInAutoHideMode` 반환 `TRUE` 표시 여부 상태 관련된 autohide 도구 모음의 표시 여부 상태에 따라 달라 집니다.  
  
 표시 여부 상태 결정 기준의 도킹 가능한 창 자동 숨기기 모드에 없는 경우는 [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) 메서드.  
  
##  <a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 도킹 가능한 창 자동 숨기기 애니메이션 되지 않는지 여부를 지정 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 창 자동 숨기기 모드에 있을 때 창의 동작을 결정 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>설명  
 이 값에 응용 프로그램의 모든 도킹 창을 영향을 줍니다.  
  
 이 멤버를 설정 하는 경우 `TRUE`, 도킹 가능한 창 숨겨지거나 호출 하는 경우의 관련된 autohide 도구 모음과 단추 함께 표시 되는 [CDockablePane::ShowPane](#showpane)합니다.  
  
 이 멤버를 설정 하는 경우 `FALSE`, 도킹 가능한 창은 활성화 되거나 비활성화를 호출할 때 [CDockablePane::ShowPane](#showpane)합니다.  
  
##  <a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 자동 숨기기 모드에 있을 때 창 애니메이션 속도 지정 합니다.  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>설명  
 더 빠른 애니메이션 효과 위해이 값을 줄입니다. 애니메이션 효과 느린에 대 한이 값을 높입니다.  
  
##  <a name="onafterchangeparent"></a>CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndOldParent`  
  
### <a name="remarks"></a>설명  
  
##  <a name="onafterdockfromminiframe"></a>CDockablePane::OnAfterDockFromMiniFrame  
 프레임 창에는 부동 도킹 모음 도킹 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다.  
  
##  <a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 프레임 워크에서 창의 부모를 변경 하기 전에이 메서드를 호출 합니다.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndNewParent`  
 새 부모 창에 대 한 포인터입니다.  
  
 [in] `bDelay`  
 `BOOL`하는 창이 도킹 되지 않는 경우 도킹 레이아웃에 다시 계산을 지연 시킬 것인지 지정 합니다. 자세한 내용은 참조 [CDockablePane::UndockPane](#undockpane)합니다.  
  
### <a name="remarks"></a>설명  
 창이 도킹 되어 있는 새 부모 도킹을 허용 하지 않는 경우이 메서드 창에서 도킹이 해제 되어 있습니다.  
  
 탭된 문서 창에서 변환 되 고,이 메서드는 최근의 도킹 위치를 저장 합니다. 최근 도킹 위치를 사용 하 여 도킹 된 상태로 돌아와서 변환 될 때 창의 위치를 복원 하는 프레임 워크입니다.  
  
##  <a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 프레임 워크는 창 하기 전에이 메서드 전환 부동 상태로 호출 합니다.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectFloat`  
 부동 상태에 있을 때 창의 크기와 위치를 지정 합니다.  
  
 [in] `dockMethod`  
 도킹 방법을 지정합니다. 참조 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) 목록이 가능한 값에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 수 놓을지; 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 float로에 대 한이 되 면 프레임 워크에서 호출 됩니다. 창에서 표시 하기 전에 모든 처리를 수행 하려는 경우이 메서드는 파생된 클래스에서 재정의할 수 있습니다.  
  
##  <a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 사용자가 아닌 다른 캡션 단추를 누를 때 호출 된 `AFX_HTCLOSE` 및 `AFX_HTMAXBUTTON` 단추입니다.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHit`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창 캡션에 사용자 지정 단추를 추가 하는 경우 사용자가 단추를 누를 때 알림을 받으려면이 메서드를 재정의 합니다.  
  
##  <a name="onslide"></a>CDockablePane::OnSlide  
 자동 숨기기 모드에 있을 때 창에서 애니메이션을 적용 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSlideOut`  
 `TRUE`창을 표시 하려면 `FALSE` 창을 숨기려면 합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 자동 숨기기 효과 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 프레임 워크 창을 도킹 되는 경우이 메서드를 호출 합니다.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 기본 창 구분선 설정 `NULL` 창에서 해당 컨테이너에서 제거 합니다.  
  
##  <a name="replacepane"></a>CDockablePane::ReplacePane  
 창에서 지정 된 창으로 대체합니다.  
  
```  
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bRegisterWithFrame = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBarToReplaceWith`  
 도킹 가능한 창에 대 한 포인터입니다.  
  
 [in] `dockMethod`  
 사용되지 않습니다.  
  
 [in] `bRegisterWithFrame`  
 경우 `TRUE`, 새 창의 부모 항목의 이전 창 고 도킹 관리자에 등록 되어 있습니다. 새 창은 도킹 관리자에 의해 유지 관리 되는 창의 목록에서 이전 창의 인덱스에 삽입 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`교체에 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 창을 deserialize 하는 프레임 워크는 기본 창 구분선을 복원 하려면이 메서드를 호출 합니다.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>설명  
 복원 된 기본 창 구분선이 있는 경우 현재 기본 창 구분선을 대체 합니다.  
  
##  <a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 표시 사이의 도킹 창을 설정/해제 및 자동 숨기기 모드입니다.  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bMode`  
 `TRUE`자동 숨기기 모드를 사용 하도록 설정 하려면 `FALSE` 일반 도킹 모드를 사용 하도록 합니다.  
  
 [in] `dwAlignment`  
 만들려는 자동 숨기기 창의 맞춤을 지정 합니다.  
  
 [in] [out]`pCurrAutoHideBar`  
 현재 autohide 도구 모음에 대 한 포인터입니다. 수 `NULL`합니다.  
  
 [in] `bUseTimer`  
 창 자동 숨기기 모드로 전환할 때 자동 숨기기 효과 사용 하려면 또는 즉시 창을 숨기려면 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 자동 숨기기 모드로 전환 결과로 생성 된 자동 숨기기 도구 모음 또는 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 도킹 가능한 창 자동 숨기기 모드로 일반 도킹 모드로 전환할 수 있는 핀 단추를 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.  
  
 프로그래밍 방식으로 도킹 가능한 창 자동 숨기기 모드로 전환 하려면이 메서드를 호출 합니다. 창에서 주 프레임 창에 도킹 해야 합니다 ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) 에 대 한 유효한 포인터를 반환 해야 합니다는 [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 자동 숨기기 단추를 설정 하는 창에 대 한 자동 숨기기 도구 모음입니다.  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pToolBar`  
 자동 숨기기 도구 모음에 대 한 포인터입니다.  
  
 [in] `pBtn`  
 자동 숨기기 단추에 대 한 포인터입니다.  
  
##  <a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 해당 컨테이너의 창을 차지 하는 공간의 백분율을 설정 합니다.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `n`  
 `int` 해당 컨테이너의 창에서 차지 하는 공간의 백분율을 지정 하는 합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크의 창 레이아웃 다시 계산할 때 새 값을 사용 하도록 조정 합니다.  
  
##  <a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 복원 된 기본 창 구분선을 설정합니다.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hRestoredSlider`  
 창 구분선 (슬라이더)에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 복원 된 기본 창 구분선을 deserialize 하는 창을 가져옵니다. 자세한 내용은 참조 [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)합니다.  
  
##  <a name="settabbedpanertc"></a>Cdockablepane:: Settabbedpanertc  
 두 개의 창이 도킹 함께 때 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 설정 합니다.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRTC`  
 탭된 창에 대 한 런타임 클래스 정보입니다.  
  
### <a name="remarks"></a>설명  
 탭된 창 동적으로 만들어진에 대 한 런타임 클래스 정보를 설정 하려면이 메서드를 호출 합니다. 이 사용자가 단일 창을 다른 창의 캡션을 끌면 또는 호출 하는 경우 발생할 수 있습니다는 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드를 프로그래밍 방식으로 두 개의 도킹 가능한 창에서 탭된 창 만들기.  
  
 기본 런타임 클래스에 따라 설정 된 `dwTabbedStyle` 의 매개 변수 [CDockablePane::Create](#create) 및 [cdockablepane:: Createex](#createex)합니다. 새 탭된 창, 사용자 지정 하려면 클래스에 다음 클래스 중 하나에서 파생 됩니다.  
  
- [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)  
  
- [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
 그런 다음이 메서드는 런타임 클래스 정보에 대 한 포인터를 호출 합니다.  
  
##  <a name="showpane"></a>CDockablePane::ShowPane  
 표시 하거나 창을 숨깁니다.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 `TRUE`창을 표시 하려면 `FALSE` 창을 숨기려면 합니다.  
  
 [in] `bDelay`  
 `TRUE`도킹 레이아웃; 조정 지연 `FALSE` 즉시 도킹 레이아웃을 조정 해야 합니다.  
  
 [in] `bActivate`  
 `TRUE`창 표시; 때 활성화 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 대신이 메서드를 호출 하는 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) 표시 하거나 도킹 가능한 창 숨기기 때.  
  
##  <a name="slide"></a>CDockablePane::Slide  
 자동 숨기기 모드에 있는 창 애니메이션 효과 적용 합니다.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSlideOut`  
 `TRUE`창을 표시 하려면 `FALSE` 창을 숨기려면 합니다.  
  
 [in] `bUseTimer`  
 `TRUE`표시 하거나 숨기기 autohide 효과; 창에는 `FALSE` 표시 하거나 즉시 창을 숨깁니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는 자동 숨기기 모드에 있는 창 애니메이션 효과를 줄이 메서드를 호출 합니다.  
  
 이 메서드는 사용 된 `CDockablePane::m_nSlideDefaultTimeOut` 슬라이드 효과가의 제한 시간을 결정 하는 값입니다. 시간 제한의 기본값은 1입니다. 자동 숨기기 알고리즘을 사용자 지정 하는 경우 제한 시간을 변경 하려면이 멤버를 수정 합니다.  
  
##  <a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 창이 간의 항상 표시 및 자동 숨기기 모드를 전환합니다.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 하 여 창의 자동 숨기기 모드를 전환 [CDockablePane::SetAutoHideMode](#setautohidemode)합니다.  
  
##  <a name="undockpane"></a>CDockablePane::UndockPane  
 주 프레임 창 또는 미니 프레임 창 컨테이너에서 창을 도킹이 해제 되어 있습니다.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDelay`  
 `TRUE`도킹 레이아웃; 계산 지연 `FALSE` 를 도킹 레이아웃을 즉시 다시 계산 합니다.  
  
### <a name="remarks"></a>설명  
 주 프레임 창 또는 다중 미니 프레임 창 컨테이너 (단일 미니 프레임 창을 다른 창에 부동 창)에서 창을 도킹을 해제 하려면이 메서드를 호출 합니다.  
  
 수행 되지 않는 하는 모든 외부 작업을 수행 하기 전에 창을 도킹 해야 합니다는 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)합니다. 예를 들어 프로그래밍 방식으로 한 위치를 이동 하는 창 고정을 해제 해야 합니다.  
  
 프레임 워크는 창이 자동으로 도킹 해제 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane 클래스](../../mfc/reference/cpane-class.md)
