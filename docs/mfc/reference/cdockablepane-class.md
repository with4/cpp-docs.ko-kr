---
title: "CDockablePane 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePane
dev_langs:
- C++
helpviewer_keywords:
- CDockablePane class
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 34
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
ms.openlocfilehash: dea1f1ce66c0e9bedbe83109ab62055a4af2ebce
ms.lasthandoff: 02/24/2017

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
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|지정된 된 미니 프레임 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|다른 창의 현재 창에 도킹할 수 있는지 여부를 결정 합니다.|  
|[CDockablePane::CanAutoHide](#canautohide)|창 자동 숨기기 모드를 지원 하는지 여부를 결정 합니다. (재정의 [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|현재 창을 다른 창에 도킹할 수 있는 여부를 결정 합니다.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.|  
|[CDockablePane::CopyState](#copystate)|도킹 가능한 창의 상태를 복사합니다.|  
|[CDockablePane::Create](#create)|Windows 컨트롤을 만들고 연결 하는 `CDockablePane` 개체입니다.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|프레임 창에 도킹 된 창에 대 한 기본 구분선을 만듭니다.|  
|[CDockablePane::CreateEx](#createex)|Windows 컨트롤을 만들고 연결 하는 `CDockablePane` 개체입니다.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|현재 창에서 탭된 창을 만듭니다.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|컨테이너 응용 프로그램의 창에 도킹 합니다.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|개요 (표준) 도킹을 사용 하 여 창을 도킹 합니다.|  
|`CDockablePane::DockToFrameWindow`|내부적으로 사용 합니다. 창을 도킹을 사용 하 여 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) 또는 [CDockablePane::DockToWindow](#docktowindow)합니다.|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|저장 된 최근 도킹 위치로 창을 도킹합니다.|  
|[CDockablePane::DockToWindow](#docktowindow)|다른 도킹 창으로 도킹 한 창을 도킹합니다.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|사용 하거나 컨테이너에 있는 다른 창 함께이 창에 대 한 자동 숨김 모드를 사용 하지 않도록 설정 합니다.|  
|[CDockablePane::EnableGripper](#enablegripper)|표시 하거나 숨깁니다 캡션 (위치 조정 막대).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|창 자동 숨기기 모드에서 표시 하는 경우의 위치를 지정 합니다.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|창 자동 숨기기 슬라이드 모드를 검색합니다.|  
|`CDockablePane::GetAutoHideButton`|내부적으로 사용 합니다.|  
|`CDockablePane::GetAutoHideToolBar`|내부적으로 사용 합니다.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|현재 캡션 높이 반환합니다.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|컨테이너의 창에 대 한 기본 창 구분선을 반환합니다.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|제공 된 포인터 위치를 기준으로 고정 하는 창의 기능을 결정 합니다.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|도킹 창 끌기 민감도 반환합니다.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|해당 컨테이너 내에서 차지 하는 창 공간의 백분율을 검색 합니다.|  
|[CDockablePane::GetTabArea](#gettabarea)|창 탭 영역을 검색합니다.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|현재 창에 다른 창 도킹 시 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 반환 합니다.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|도킹 창에 자동 숨김 모드로 전환할 수 수 있는지 여부를 지정 합니다.|  
|[CDockablePane::HitTest](#hittest)|사용자가 마우스를 클릭 하는 창에서 특정 위치를 지정 합니다.|  
|`CDockablePane::IsAccessibilityCompatible`|내부적으로 사용 합니다.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|도킹 창 및 컨테이너에 있는 다른 모든 창 자동 숨기기 모드로 전환할 수 있는지 여부를 나타냅니다.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|창 자동 숨기기 모드 인지 여부를 결정 합니다.|  
|`CDockablePane::IsChangeState`|내부적으로 사용 합니다.|  
|[CDockablePane::IsDocked](#isdocked)|현재 창 도킹 되는지 여부를 결정 합니다.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|또는 되어 있으면 표시 (숨김)를 호출 하 여 자동 숨김 모드에 있는 창의 동작을 결정 `ShowPane`합니다.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|다중 창 프레임 창에는 창이 되는지 여부를 지정 합니다.|  
|[CDockablePane::IsResizable](#isresizable)|창 크기를 조정할 수 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|탭 맨 위 또는 맨 아래 창에 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsTracked](#istracked)|사용자가 창을 끄는 있는지 여부를 지정 합니다.|  
|[CDockablePane::IsVisible](#isvisible)|현재 창이 표시 되는지를 결정 합니다.|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|내부적으로 사용 합니다.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|부모 창에 변경 된 경우에 프레임 워크에서 호출 합니다. (재정의 [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|프레임 창에는 부동 도킹 모음 도킹 때 프레임 워크에 의해 호출 됩니다.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|부모 창의 변경 되려고 할 때에 프레임 워크에서 호출 합니다. (재정의 [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Float로에 대 한이 되 면 프레임 워크에 의해 호출 됩니다. (재정의 [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|프레임 워크는 창 고정 해제 되는 경우이 메서드를 호출 합니다.|  
|[CDockablePane::ReplacePane](#replacepane)|창을 지정 된 창으로 바꿉니다.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|기본 창 구분선을 복원 하는 창 deserialize 될 때이 메서드를 호출 하는 프레임 워크입니다.|  
|`CDockablePane::SaveState`|내부적으로 사용 합니다.|  
|`CDockablePane::Serialize`|창에서 serialize합니다. (`CBasePane::Serialize`를 재정의합니다.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|표시 되는 도킹 창 설정/해제 및 자동 숨김 모드입니다.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|자동 숨기기 단추와 창 자동 숨기기 도구 모음을 설정합니다.|  
|`CDockablePane::SetDefaultPaneDivider`|내부적으로 사용 합니다.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|해당 컨테이너 내에서 차지 하는 창 공간의 백분율을 설정 합니다.|  
|`CDockablePane::SetResizeMode`|내부적으로 사용 합니다.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|복원 된 기본 창 구분선을 설정합니다.|  
|[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)|두 개의 창이 함께 도킹할 때 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 설정 합니다.|  
|[CDockablePane::ShowPane](#showpane)|표시 하거나 창을 숨깁니다.|  
|[CDockablePane::Slide](#slide)|창을 표시 하거나 숨깁니다는 슬라이딩 애니메이션의 창 자동 숨기기 모드일 때만 표시 합니다.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|자동 숨김 모드 설정/해제 합니다. (재정의 [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|창을 주 프레임 창 또는 미니 프레임 창 컨테이너에서 도킹 해제 합니다.|  
|`CDockablePane::UnSetAutoHideMode`|내부적으로 사용 합니다. 자동 숨김 모드를 설정 하려면 사용 하 여 [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|도킹 창 (자동 숨김 모드)에서 숨겨지는지 여부를 결정 합니다.|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|자동 숨김 도킹 창을 해야 중지 하는 경우 상대 (sliding)를 결정 합니다.|  
|[CDockablePane::DrawCaption](#drawcaption)|도킹 창 캡션 (위치 조정 막대)를 그립니다.|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|사용자가 아닌 다른 캡션 단추를 누를 때 호출 된 `AFX_HTCLOSE` 및 `AFX_HTMAXBUTTON` 단추입니다.|  
|[CDockablePane::OnSlide](#onslide)|창 표시 또는 숨길 때 자동 숨기기 슬라이드 효과 렌더링 하는 프레임 워크에서 호출 됩니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|도킹 가능한 창 자동 숨기기 애니메이션 되지 않는지 여부를 지정 합니다.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|창 자동 숨기기 모드일 때 창 동작을 결정 합니다.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|될 때 창 애니메이션 속도 지정 합니다. 표시 하거나 숨길 자동 숨기기 모드일 때.|  
  
## <a name="remarks"></a>주의  
 `CDockablePane`다음과 같은 기능을 구현합니다.  
  
-   주 프레임 창에 도킹 된 창입니다.  
  
-   창 자동 숨기기 모드로 전환 합니다.  
  
-   창이 탭된 창으로 연결 합니다.  
  
-   미니 프레임 창의 창을 부동합니다.  
  
-   미니 프레임 창의 부동 다른 창으로 도킹 된 창입니다.  
  
-   창 크기를 조정 합니다.  
  
-   로드 하 고 도킹 창에 대 한 상태를 저장 합니다.  
  
    > [!NOTE]
    >  상태 정보는 Windows 레지스트리에 저장 됩니다.  
  
-   또는 캡션이 없는 창을 만드는 중입니다. 캡션 텍스트 레이블을 사용할 수 및 그라데이션 색으로 채워질 수 있습니다.  
  
-   창의 내용을 표시 하는 동안 창을 끌어  
  
-   끌기 사각형을 표시 하는 동안 창을 끕니다.  
  
 도킹 창에서 응용 프로그램을 사용 하려면 창에서 파생 된 `CDockablePane` 클래스입니다. 하거나 주 프레임 창 개체 또는 사용자 창의 인스턴스를 제어 하는 창 개체에 파생된 개체를 포함 합니다. 다음 호출는 [CDockablePane::Create](#create) 메서드 또는 [CDockablePane::CreateEx](#createex) 처리 하는 경우 메서드는 `WM_CREATE` 주 프레임 창에 있는 메시지입니다. 마지막으로 설정 하는 창 개체를 호출 하 여 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane), 또는 [CDockablePane::AttachToTabWnd](#attachtotabwnd)합니다.  
  
## <a name="customization-tips"></a>사용자 지정 팁  
 다음 팁에 적용 `CDockablePane` 개체:  
  
-   호출 하는 경우 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 두 탭, 도킹 가능한 창에 대 한 탭된 창에 대 한 포인터에 반환 되는 `ppTabbedControlBar` 매개 변수입니다. 이 매개 변수를 사용 하 여 탭된 창에 탭을 추가 하려면 계속 수 있습니다.  
  
-   탭된 창으로 만든 유형의 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 에 의해 결정 됩니다는 `CDockablePane` 개체는 `pTabControlBarAttachTo` 매개 변수입니다. 호출할 수 있습니다 [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) 하는 탭된 창의 종류를 설정는 `CDockablePane` 만들어집니다. 기본 형식은에 의해 결정 됩니다는 `dwTabbedStyle` 의 [CDockablePane::Create](#create) 처음 만드는 경우는 `CDockablePane`합니다. 경우 `dwTabbedStyle` 기본 형식은 AFX_CBRS_OUTLOOK_TABS는 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)경우 `dwTabbedStyle` 기본 형식은 AFX_CBRS_REGULAR_TABS는 [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
-   다른 한 도킹 가능한 창 도킹 하려면 호출의 [CDockablePane::DockToWindow](#docktowindow) 메서드. 원래 창 도킹 해야 합니다 곳이 메서드를 호출 하기 전에 합니다.  
  
-   멤버 변수 [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) 컨트롤 도킹 가능 창을 자동으로 작동 하는 방법 숨기기 모드를 호출할 때 [CDockablePane::ShowPane](#showpane)합니다. 이 멤버 변수로 설정 된 경우 `TRUE`, 도킹 가능한 창과 자동 숨기기 단추는 표시 되지 것입니다. 그렇지 않으면 이러한 됩니다 슬라이드 인 및 체크 아웃 합니다.  
  
-   자동 숨기기 애니메이션을 사용 하지 않도록 설정 하 여 수는 [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) 멤버 변수를 `TRUE`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 방법을 보여 줍니다.는 `CDockablePane` 의 다양 한 메서드를 사용 하 여 개체의 `CDockablePane` 클래스입니다. 이 예제에는 자동 숨김 도킹 가능한 창에 대 한 모든 기능을 활성화, 캡션 또는 위치 조정 막대를 사용 하도록 설정, 자동 숨김 모드를 사용 하도록 설정, 창을 표시 및 자동 숨김 모드에 있는 창에 애니메이션 효과 적용 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&27;](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&28;](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDockablePane.h  
  
##  <a name="a-nameattachtotabwnda--cdockablepaneattachtotabwnd"></a><a name="attachtotabwnd"></a>CDockablePane::AttachToTabWnd  
 탭된 창 만들기 대상 창에서 현재 창에 연결 합니다.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pTabControlBarAttachTo`  
 현재 창에 연결 하는 대상 창의 지정 합니다. 대상 창 도킹 가능한 창 이어야 합니다.  
  
 [in] `dockMethod`  
 도킹 방법을 지정합니다.  
  
 [in] `bSetActive`  
 `TRUE`연결 작업; 후 탭된 창 활성화 하려면 그렇지 않으면 `FALSE`합니다.  
  
 [out] `ppTabbedControlBar`  
 연결 작업에서 생성 되는 탭된 창에 포함 되어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 현재 창에서 탭된 창입니다; 없는 경우에 대 한 포인터 그렇지 않은 경우 연결 작업에서 생성 되는 탭된 창에 대 한 포인터입니다. 반환 값은 `NULL` 현재 창에 연결할 수 없습니다, 또는 오류가 발생 합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창에이 메서드를 사용 하 여 다른 창으로 연결 하는 경우 결과 다음과 같습니다.  
  
1.  Framework 검사 하는지 여부를 대상 창 `pTabControlBarAttachTo` 은 일반 도킹 창 또는에서 파생 하는 경우 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)합니다.  
  
2.  대상 창 탭된 창 인 프레임 워크는 탭으로 현재 창에 추가 합니다.  
  
3.  대상 창 일반 도킹 창 이면 프레임 워크 탭된 창을 만듭니다.  
  
    -   프레임 워크 호출 `pTabControlBarAttachTo->CreateTabbedPane`합니다. 새 탭된 창의 스타일에 따라 달라 집니다는 `m_pTabbedControlBarRTC` 멤버입니다. 기본적으로이 멤버의 런타임 클래스에 설정 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)합니다. 전달 하는 경우는 `AFX_CBRS_OUTLOOK_TABS` 으로 스타일의 `dwTabbedStyle` 매개 변수를는 [CDockablePane::Create](#create) 메서드는 런타임 클래스 개체의 런타임 클래스에 설정 되어 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)합니다. 언제 든 지 새 창의 스타일을 변경 하려면이 멤버를 변경할 수 있습니다.  
  
    -   이 메서드가 만들고 탭된 창, 프레임 워크에 대 한 포인터를 대체 `pTabControlBarAttachTo` (창이 않는 경우 고정 또는 부동 다중 미니 프레임 창에서) 새 탭된 창에 대 한 포인터입니다.  
  
    -   추가 하는 프레임 워크는 `pTabControlBarAttachTo` 첫 번째 탭 탭된 창에는 창입니다. 프레임 워크는 다음 두 번째 탭으로 현재 창을 추가합니다.  
  
4.  현재 창에서 파생 된 경우 `CBaseTabbedPane`, 모두 탭으로 이동 됩니다 `pTabControlBarAttachTo` 현재 창 소멸 됩니다. 따라서 주의 해야이 메서드를 호출 하면 메서드가 반환 될 때 현재 창에 대 한 포인터가 유효 있을 수 있으므로 합니다.  
  
 도킹 레이아웃을 만들 때 다른 하나의 창이 연결 하면 설정 `dockMethod` 를 `DM_SHOW`합니다.  
  
 다른 창에 연결 하기 전에 첫 번째 창을 도킹 해야 합니다.  
  
##  <a name="a-namecalcfixedlayouta--cdockablepanecalcfixedlayout"></a><a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
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
  
##  <a name="a-namecanacceptminiframea--cdockablepanecanacceptminiframe"></a><a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 지정된 된 미니 프레임 창에 도킹 될 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMiniFrame`  
 `CPaneFrameWnd` 개체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 `pMiniFrame` 창에 도킹 하 고, 그렇지 않으면 수 `FALSE`합니다.  
  
##  <a name="a-namecanacceptpanea--cdockablepanecanacceptpane"></a><a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 다른 창의 현재 창에 도킹할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 현재 창에 도킹 창을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정 된 창입니다;이 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 창이 현재 창에 도킹 되어 전에이 메서드를 호출 합니다.  
  
 특정 창으로 도킹을 사용 하지 않도록 설정 하거나 사용 하려면 파생된 클래스에서이 함수를 재정의 합니다.  
  
 기본적으로이 메서드는 다음과 같이 반환 됩니다. `TRUE` 경우 `pBar` 부모는 형식 또는 `CDockablePane`합니다.  
  
##  <a name="a-namecanautohidea--cdockablepanecanautohide"></a><a name="canautohide"></a>CDockablePane::CanAutoHide  
 여부의 창 수 자동 숨기기를 결정 합니다.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 수 자동 숨기기 경우; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `CDockablePane::CanAutoHide`반환 `FALSE` 다음 상황 중 하나에서:  
  
-   창에 부모가 없습니다.  
  
-   관리자는 도킹 창 자동 숨기기를 허용 하지 않습니다.  
  
-   창 도킹 되지 않습니다.  
  
##  <a name="a-namecanbeattacheda--cdockablepanecanbeattached"></a><a name="canbeattached"></a>CDockablePane::CanBeAttached  
 현재 창을 다른 창에 도킹할 수 있는 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`또는 주 프레임 창; 다른 창으로 도킹 가능한 창을 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 항상 반환 `TRUE`합니다. 이 메서드를 호출 하지 않고 도킹을 사용할지 파생된 클래스에서 재정의 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)합니다.  
  
##  <a name="a-namecdockablepanea--cdockablepanecdockablepane"></a><a name="cdockablepane"></a>CDockablePane::CDockablePane  
 생성 하 고 초기화는 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창 개체를 생성 한 후 호출 [CDockablePane::Create](#create) 또는 [CDockablePane::CreateEx](#createex) 를 만듭니다.  
  
##  <a name="a-nameconverttotabbeddocumenta--cdockablepaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActiveTabOnly`  
 변환 하는 경우는 `CTabbedPane`, 지정 `TRUE` 활성 탭만 변환 합니다. 지정 `FALSE` 창의 모든 탭을 변환할 수 있습니다.  
  
##  <a name="a-namecheckautohideconditiona--cdockablepanecheckautohidecondition"></a><a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 도킹 창 (자동 숨기기 모드 라고도 함) 숨겨져 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`숨기기 조건이 충족 되 고, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 타이머를 사용 하 여 정기적으로 자동 숨기기 도킹 가능한 창을 숨길 것인지를 확인 합니다. 메서드는 반환 `TRUE` 창에서 활성 상태가 아니므로 창에서 조정 되지 않습니다 하 고 창 위에 마우스 포인터를 않습니다.  
  
 프레임 워크를 호출 하는 모든 이전 조건이 충족 되 면 [CDockablePane::Slide](#slide) 창을 숨기려면 합니다.  
  
##  <a name="a-namecheckstopslideconditiona--cdockablepanecheckstopslidecondition"></a><a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 자동 숨기기 도킹 창 해야 중지 하는 경우 상대 (sliding)를 결정 합니다.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDirection`  
 `TRUE`창에서 표시 되 면 `FALSE` 창에서 숨겨진 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`stop 조건이 충족 되 고, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창 자동 숨기기 모드로 설정 되 면 프레임 워크를 사용 하 여 상대 (sliding) 효과 창을 표시 하거나 숨깁니다. 프레임 워크의 창을 상대 (sliding) 하는 경우이 함수를 호출 합니다. `CheckStopSlideCondition`반환 `TRUE` 창은 완전히 표시 되는 경우 또는 완전히으로 숨겨집니다.  
  
 사용자 지정 자동 숨기기 효과 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-namecopystatea--cdockablepanecopystate"></a><a name="copystate"></a>CDockablePane::CopyState  
 도킹 가능한 창의 상태를 복사합니다.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOrgBar`  
 도킹 가능한 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `CDockablePane::CopyState`상태를 복사 `pOrgBar` 다음 메서드를 호출 하 여 현재 창에 있습니다.  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="a-namecreatea--cdockablepanecreate"></a><a name="create"></a>CDockablePane::Create  
 Windows 컨트롤을 만들고 연결 하는 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다.  
  
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
 자식 창의 ID를 지정 합니다. 이 값이 도킹 창에 대 한 도킹 상태를 저장 하려는 경우에 고유 해야 합니다.  
  
 [in] `dwStyle`  
 창 스타일 특성을 지정합니다.  
  
 [in] `dwTabbedStyle`  
 사용자가이 창의 캡션에 창을 끌 때 만들어지는 탭된 창의 탭된 스타일을 지정 합니다.  
  
 [in] `dwControlBarStyle`  
 추가 스타일 특성을 지정합니다.  
  
 [in] [out]`pContext`  
 창 만들기 컨텍스트를 지정합니다.  
  
 [in] `lpszWindowName`  
 창 이름을 지정합니다.  
  
 [in] `sizeDefault`  
 창의 크기를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 성공적으로 만들어지면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 Windows 창을 만들고 연결 하는 `CDockablePane` 개체입니다.  
  
 하는 경우는 `dwStyle` 창 스타일에는 `CBRS_FLOAT_MULTI` 플래그를 미니 프레임 창을 미니 프레임 창에 있는 다른 창으로 배치할 수 있습니다. 기본적으로, 도킹 창 수만 이동 개별적으로입니다.  
  
 하는 경우는 `dwTabbedStyle` 매개 변수에 `AFX_CBRS_OUTLOOK_TABS` 플래그가 지정 된 창에서 다른 창을 사용 하 여이 창에 연결 될 때 Outlook 스타일 탭 창을 만드는 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드. 기본적으로, 도킹 가능 창을 만들 형식의 일반 탭된 창 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
##  <a name="a-namecreatedefaultpanedividera--cdockablepanecreatedefaultpanedivider"></a><a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 프레임 창에 도킹 된 창에 대 한 기본 구분선을 만듭니다.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 창 도킹 되 고 주 프레임의 가장자리를 지정 합니다. 경우 `dwAlignment` 포함는 `CBRS_ALIGN_LEFT` 또는 `CBRS_ALIGN_RIGHT` 플래그,이 메서드가 만드는 세로 ( `CPaneDivider::SS_VERT`) 구분선; 그렇지 않으면이 메서드가 만드는 가로 ( `CPaneDivider::SS_HORZ`) 구분선입니다.  
  
 [in] `pParent`  
 부모 프레임에 대 한 포인터입니다.  
  
 [in] `pSliderRTC`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 새로 만든 구분선에 대 한 포인터를 반환 하거나 `NULL` 구분선 만들기가 실패 하는 경우.  
  
### <a name="remarks"></a>주의  
 `dwAlignment`다음 값 중 하나일 수 있습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|창은 프레임 창의 클라이언트 영역 위쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_BOTTOM`|창은 프레임 창의 클라이언트 영역 아래쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_LEFT`|창은 프레임 창의 클라이언트 영역 왼쪽에 도킹 되 고 됩니다.|  
|`CBRS_ALIGN_RIGHT`|창은 프레임 창의 클라이언트 영역 오른쪽에 도킹 되 고 됩니다.|  
  
##  <a name="a-namecreateexa--cdockablepanecreateex"></a><a name="createex"></a>CDockablePane::CreateEx  
 Windows 컨트롤을 만들고 연결 하는 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다.  
  
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
 새 창에 대 한 확장된 스타일 특성을 지정합니다.  
  
 [in] `lpszCaption`  
 창 이름을 지정합니다.  
  
 [in] [out]`pParentWnd`  
 부모 창을 지정합니다.  
  
 [in] `rect`  
 클라이언트 좌표에서 창의 위치와 크기 지정 `pParentWnd`합니다.  
  
 [in] `bHasGripper`  
 `TRUE`캡션; 사용 하 여 창을 만들려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `nID`  
 자식 창의 ID를 지정 합니다. 이 값이 도킹 창에 대 한 도킹 상태를 저장 하려는 경우에 고유 해야 합니다.  
  
 [in] `dwStyle`  
 창 스타일 특성을 지정합니다.  
  
 [in] `dwTabbedStyle`  
 사용자가이 창의 캡션에 창을 끌 때 만들어지는 탭된 창의 탭된 스타일을 지정 합니다.  
  
 [in] `dwControlBarStyle`  
 추가 스타일 특성을 지정합니다.  
  
 [in] [out]`pContext`  
 창 만들기 컨텍스트를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 성공적으로 만들어지면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 Windows 창을 만들고 연결 하는 `CDockablePane` 개체입니다.  
  
 하는 경우는 `dwStyle` 창 스타일에는 `CBRS_FLOAT_MULTI` 플래그를 미니 프레임 창을 미니 프레임 창에 있는 다른 창으로 배치할 수 있습니다. 기본적으로, 도킹 창 수만 이동 개별적으로입니다.  
  
 하는 경우는 `dwTabbedStyle` 매개 변수에 `AFX_CBRS_OUTLOOK_TABS` 플래그가 지정 된 창에서 다른 창을 사용 하 여이 창에 연결 될 때 Outlook 스타일 탭 창을 만드는 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드. 기본적으로, 도킹 가능 창을 만들 형식의 일반 탭된 창 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
##  <a name="a-namecreatetabbedpanea--cdockablepanecreatetabbedpane"></a><a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 현재 창에서 탭된 창을 만듭니다.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>반환 값  
 새 탭된 창, 또는 `NULL` 만들기 작업이 실패 한 경우.  
  
### <a name="remarks"></a>주의  
 이 창을 대체 하는 탭된 창을 만들 때이 메서드를 호출 하는 프레임 워크입니다. 자세한 내용은 참조 [CDockablePane::AttachToTabWnd](#attachtotabwnd)합니다.  
  
 재정의 방법이 탭된 창 사용자 지정 하는 파생된 클래스에서이 메서드는 생성 하 고 초기화 합니다.  
  
 탭된 창에 저장 된 런타임 클래스 정보에 따라 생성 되는 `m_pTabbedControlBarRTC` 하 여 초기화 된 멤버는 [CDockablePane::CreateEx](#createex) 메서드.  
  
##  <a name="a-namedockpanecontainera--cdockablepanedockpanecontainer"></a><a name="dockpanecontainer"></a>CDockablePane::DockPaneContainer  
 컨테이너 응용 프로그램의 창에 도킹 합니다.  
  
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
 `DWORD`컨테이너는 도킹 창 옆쪽에 지정입니다.  
  
 [in] `dockMethod`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`컨테이너의 창; 도킹 되어 성공적으로 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `dwAlignment`다음 값 중 하나일 수 있습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|컨테이너 창 위쪽에 도킹 되 고 있습니다.|  
|`CBRS_ALIGN_BOTTOM`|컨테이너 창의 아래쪽에 도킹 되 고 있습니다.|  
|`CBRS_ALIGN_LEFT`|컨테이너 창의 왼쪽에 도킹 되 고 있습니다.|  
|`CBRS_ALIGN_RIGHT`|컨테이너 창의 오른쪽에 도킹 되 고 있습니다.|  
  
##  <a name="a-namedockpanestandarda--cdockablepanedockpanestandard"></a><a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 개요 (표준) 도킹을 사용 하 여 창을 도킹 합니다.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bWasDocked`  
 메서드가 반환 될 때이 값 포함 `TRUE` 포함 된 창에서 도킹 된 고, 그렇지 않으면 되었으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 탭된 창으로 도킹 되어 창 또는 탭된 창 도킹 결과로 생성 된 경우이 메서드는 탭된 창에 대 한 포인터를 반환 합니다. 이 메서드가 반환 하는 경우 창을 그렇지 않으면 도킹 성공적으로 `this` 포인터입니다. 이 메서드가 반환 하는 경우 실패 한 도킹 `NULL`합니다.  
  
##  <a name="a-namedocktorecentposa--cdockablepanedocktorecentpos"></a><a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 창을 도킹 저장된 위치에 도킹합니다.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 도킹 되어 있는 성공적으로; 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창에 최근 도킹 정보를 저장 한 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) 개체입니다.  
  
##  <a name="a-namedocktowindowa--cdockablepanedocktowindow"></a><a name="docktowindow"></a>CDockablePane::DockToWindow  
 다른 도킹 창으로 도킹 한 창을 도킹합니다.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pTargetWindow`  
 이 창의 도킹을 도킹 가능한 창을 지정 합니다.  
  
 [in] `dwAlignment`  
 창 도킹 맞춤을 지정 합니다. CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM 또는 CBRS_ALIGN_ANY 중 하나일 수 있습니다. (Afxres.h에 정의 합니다.)  
  
 [in] `lpRect`  
 창에 대 한 도킹 사각형을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 성공적으로 고정 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 로 지정 된 정렬 된 하나의 창이 다른 창으로 도킹 하려면이 메서드를 호출 `dwAlignment`합니다.  
  
##  <a name="a-namedrawcaptiona--cdockablepanedrawcaption"></a><a name="drawcaption"></a>CDockablePane::DrawCaption  
 도킹 창의 캡션 (위치 조정 막대 라고도 함)을 그립니다.  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 그리기에 사용 되는 장치 컨텍스트를 나타냅니다.  
  
 [in] `rectCaption`  
 창의 캡션의 경계 사각형을 지정합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 도킹 가능한 창 캡션의 하려면이 메서드를 호출 합니다.  
  
 캡션의 모양을 사용자 지정 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-nameenableautohidealla--cdockablepaneenableautohideall"></a><a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 사용 하거나 컨테이너에 있는 다른 창 및이 창에 대 한 자동 숨기기 모드를 사용 하지 않도록 설정 합니다.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`자동 숨기기는 도킹 가능한 창;에 대 한 모든 기능을 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용자 보유 하는 경우는 `Ctrl` 키 및 창을 동일한 컨테이너에 있는 다른 모든 창 자동 숨기기 모드로 전환 핀 단추는 자동 숨기기 모드로 전환도 클릭 합니다.  
  
 이 메서드를 호출 `bEnable` 로 설정 `FALSE` 특정 창에 대 한이 기능을 해제할 수 있습니다.  
  
##  <a name="a-nameenablegrippera--cdockablepaneenablegripper"></a><a name="enablegripper"></a>CDockablePane::EnableGripper  
 표시 하거나 숨깁니다 (위치 조정 막대 라고도 함) 캡션입니다.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`캡션;를 사용 하도록 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 도킹 가능 창을 만들면 없기는 **WS_STYLE** 창 스타일을 지정 하는 경우에 마찬가지입니다. 즉, 창의 캡션 되는 프레임 워크에 의해 제어 되는 비 클라이언트 영역이 있지만이 영역에서 표준 창 캡션에 다릅니다.  
  
 표시 하거나 언제 든 지 캡션을 숨길 수 있습니다. 프레임 워크 탭된 창 또는 미니 프레임 창의 창을 움직이는 창을 탭으로 추가 되 면 캡션을 숨깁니다.  
  
##  <a name="a-namegetahrestoredrecta--cdockablepanegetahrestoredrect"></a><a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 창 자동 숨기기 모드일 때의 위치를 지정 합니다.  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 자동 숨기기 모드일 때 창의 위치를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetahslidemodea--cdockablepanegetahslidemode"></a><a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 창 자동 숨기기 슬라이드 모드를 검색합니다.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `UINT` 창 자동 숨기기 슬라이드 모드를 지정 하는 합니다. 반환 값 수 `AFX_AHSM_MOVE` 또는 `AFX_AHSM_STRETCH`, 구현만 사용 하지만 `AFX_AHSM_MOVE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcaptionheighta--cdockablepanegetcaptionheight"></a><a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 현재 캡션의 픽셀 높이 반환합니다.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 캡션 높이입니다.  
  
### <a name="remarks"></a>주의  
 캡션 높이 0에서 캡션을 숨기면는 [CDockablePane::EnableGripper](#enablegripper) 메서드를 창 캡션이 없는 경우 또는 합니다.  
  
##  <a name="a-namegetdefaultpanedividera--cdockablepanegetdefaultpanedivider"></a><a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 컨테이너의 창에 대 한 기본 창 구분선을 반환합니다.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>반환 값  
 유효한 [CPaneDivider](../../mfc/reference/cpanedivider-class.md) 개체는 도킹 가능한 창을 주 프레임 창으로 고정 되어 있는 경우 또는 `NULL` 아니면 부동는 도킹 가능한 창 잠기지 않은 경우.  
  
### <a name="remarks"></a>주의  
 창 구분선에 대 한 자세한 내용은 참조 [CPaneDivider 클래스](../../mfc/reference/cpanedivider-class.md)합니다.  
  
##  <a name="a-namegetdockingstatusa--cdockablepanegetdockingstatus"></a><a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 제공 된 포인터 위치를 기준으로 고정 하는 창의 기능을 결정 합니다.  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pt`  
 화면 좌표에서 포인터의 위치입니다.  
  
 [in] `nSensitivity`  
 거리 (픽셀) 사각형의 가장자리에서 포인터 도킹을 사용 하도록 설정 하 여야 합니다.  
  
### <a name="return-value"></a>반환 값  
 다음과 같은 상태 값 중 하나입니다.  
  
|`AFX_CS_STATUS` 값|의미|  
|---------------------------|-------------|  
|`CS_NOTHING`|도크 사이트를 통해는 포인터가 아닙니다. 프레임 워크 창을 도킹 하지 않습니다.|  
|`CS_DOCK_IMMEDIATELY`|포인터는 도킹 사이트에 대해 직접 실행 모드에서 (창에서 사용 하 여 `DT_IMMEDIATE` 도킹 모드). 프레임 워크의 창을 즉시 도킹합니다.|  
|`CS_DELAY_DOCK`|도크 사이트 다른 도킹 창 또는 주 프레임의 가장자리를 가장 위에 포인터를 합니다. 프레임 워크는 잠시 후의 창을 도킹합니다. 이러한 지연 시간에 대 한 자세한 내용은 설명 섹션을 참조 합니다.|  
|`CS_DELAY_DOCK_TO_TAB`|도크 사이트를 창에 탭된 창에 도킹할 수 있는 위에 포인터를 배치 합니다. 이 포인터는 탭된 창에서 탭 영역의 이나 다른 도킹 창의 캡션에 대해 때 발생 합니다.|  
  
### <a name="remarks"></a>주의  
 프레임 워크 부동 창의 도킹을 처리 하려면이 메서드를 호출 합니다.  
  
 부동 도구 모음 또는 사용 하는 창을 도킹에 대 한는 `DT_IMMEDIATE` 모드 도킹을 프레임 워크 지연 도킹 명령의 창을 이동 하 고 부모 프레임의 클라이언트 영역에서 도킹 발생 하기 전에 사용자를 사용 하도록 설정 합니다. 지연 길이 밀리초에서로 측정 됩니다 및 의해 제어 되는 [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 데이터 멤버... 기본값 [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 는 200 개입니다. 이 동작의 도킹 동작을 에뮬레이션 [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007입니다.  
  
 상태를 도킹 지연에 대 한 ( `CS_DELAY_DOCK` 및 `CS_DELAY_DOCK_TO_TAB`), 마우스 단추를 놓을 때까지 도킹 프레임 워크를 수행 하지 않습니다. 창을 사용 하는 경우는 `DT_STANDARD` 모드 도킹을 프레임 워크가 표시 사각형을 프로젝션 된 도킹 위치에 있습니다. 창을 사용 하는 경우는 `DT_SMART` 모드 도킹을 프레임 워크 스마트 도킹 표식 및 반투명 사각형 위치에 표시 프로젝션 된 도킹 합니다. 호출 하 여 창에 대 한 도킹 모드를 지정 하려면는 [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) 메서드. 스마트 도킹 하는 방법에 대 한 자세한 내용은 참조 [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams)합니다.  
  
##  <a name="a-namegetdragsensitivitya--cdockablepanegetdragsensitivity"></a><a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 도킹 창 끌기 민감도 반환합니다.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 너비와 높이 (픽셀)는, 끌기 지점에 중심이 있는 사각형의 포함 개체입니다. 이 사각형 외부에 마우스 포인터가 이동할 때까지 끌기 작업이 시작 되지 않습니다.  
  
##  <a name="a-namegetlastpercentinpanecontainera--cdockablepanegetlastpercentinpanecontainer"></a><a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 검색 창을 해당 컨테이너에서 차지 하는 공간의 백분율 ( [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `int` 창에서 해당 컨테이너에서 차지 하는 공간의 백분율을 지정 하는 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 컨테이너의 레이아웃을 조정 하는 경우에 사용 됩니다.  
  
##  <a name="a-namegettabareaa--cdockablepanegettabarea"></a><a name="gettabarea"></a>CDockablePane::GetTabArea  
 창 탭 영역을 검색합니다.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectTabAreaTop`  
 `GetTabArea`탭 창의 위쪽에 배치 하는 경우에 탭 영역으로이 변수를 채웁니다. 탭 창의 아래쪽에 있는 경우이 변수는 빈 사각형 채워집니다.  
  
 [in] `rectTabAreaBottom`  
 `GetTabArea`탭 창의 맨 아래에 배치 하는 경우에 탭 영역으로이 변수를 채웁니다. 탭 창의 위쪽에 있는 경우이 변수는 빈 사각형 채워집니다.  
  
### <a name="remarks"></a>주의  
 파생 된 클래스에만이 메서드는 `CDockablePane` 탭 하 고 있습니다. 자세한 내용은 참조 [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) 및 [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea)합니다.  
  
##  <a name="a-namegettabbedpanertca--cdockablepanegettabbedpanertc"></a><a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 현재 창에 다른 창 도킹 시 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 반환 합니다.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도킹 가능한 창에 대 한 런타임 클래스 정보입니다.  
  
### <a name="remarks"></a>주의  
 동적으로 생성 하는 탭된 창에 대 한 런타임 클래스 정보를 검색 하려면이 메서드를 호출 합니다. 사용자가 하나의 창이 다른 창 캡션의 끌면 또는 호출 하는 경우 발생할 수 있습니다는 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드를 프로그래밍 방식으로 두 개의 도킹 가능한 창에서 탭된 창 만들기.  
  
 호출 하 여 런타임 클래스 정보를 설정할 수는 [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) 메서드.  
  
##  <a name="a-namehasautohidemodea--cdockablepanehasautohidemode"></a><a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 도킹 창 자동 숨기기 모드로 전환 될 수 있습니다 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 자동 숨기기; 모드로 전환 될 수 있습니다 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 특정 도킹 가능한 창에 대 한 자동 숨기기 모드를 사용 하지 않도록 설정 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-namehittesta--cdockablepanehittest"></a><a name="hittest"></a>CDockablePane::HitTest  
 사용자가 마우스를 클릭 하는 창에서 위치를 지정 합니다.  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 테스트를 지정 합니다.  
  
 [in] `bDetectCaption`  
 `TRUE`경우 `HTCAPTION` 를 반환할 경우 지점은 창의 캡션; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
- `HTNOWHERE`경우 `point` 이 도킹 가능한 창에 있습니다.  
  
- `HTCLIENT`경우 `point` 도킹 가능한 창의 클라이언트 영역에 있습니다.  
  
- `HTCAPTION`경우 `point` 도킹 가능한 창의 캡션 영역에 있습니다.  
  
- `AFX_HTCLOSE`경우 `point` 닫기 단추에 있습니다.  
  
- `HTMAXBUTTON`경우 `point` 핀 단추에 있습니다.  
  
##  <a name="a-nameisautohideallenableda--cdockablepaneisautohideallenabled"></a><a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 도킹 창 및 컨테이너에 있는 다른 모든 창에 자동 숨기기 모드로 전환할 수 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 및 컨테이너에 다른 모든 창 자동 숨기기; 모드로 전환 될 수 있습니다 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 보유 하는 동안 도킹 핀 단추를 클릭 하 여 자동 숨기기 모드를 활성화 하는 사용자는 **Ctrl** 키  
  
 를 사용 하거나이 동작을 사용 하지 않도록 설정 하려면 호출의 [CDockablePane::EnableAutohideAll](#enableautohideall) 메서드.  
  
##  <a name="a-nameisautohidemodea--cdockablepaneisautohidemode"></a><a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 창 자동 숨기기 모드 인지 여부를 결정 합니다.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 자동 숨기기; 모드인 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameisdockeda--cdockablepaneisdocked"></a><a name="isdocked"></a>CDockablePane::IsDocked  
 현재 창 도킹 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 미니 프레임 창에 속하지 않는 경우 또는 미니 프레임 창을 다른 창에는 부동 창인 경우. `FALSE`미니 프레임 창의 자식 창에서 많고 미니 프레임 창에 속하는 다른 창 없습니다.  
  
### <a name="remarks"></a>주의  
 창에서 주 프레임 창에 도킹 여부를 확인 하려면 호출 [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)합니다. 메서드에서 NULL이 아닌 포인터를 반환 하는 경우 창에서 주 프레임 창에 도킹 합니다.  
  
##  <a name="a-nameishideinautohidemodea--cdockablepaneishideinautohidemode"></a><a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 또는 되어 있으면 표시 (숨김)를 호출 하 여 자동 숨기기 모드에 있는 창의 동작을 결정 [CDockablePane::ShowPane](#showpane)합니다.  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창 자동 숨기기 모드에 있을 때 숨겨야 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창 자동 숨기기 모드일 때 작동 다르게 호출 하는 경우 `ShowPane` 을 숨기 거 나 창을 표시 합니다. 이 동작을 제어 하는 정적 멤버 여 [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)합니다. 이 멤버는 경우 `TRUE`, 도킹 가능한 창 자동 숨기기 관련된 도구 모음 또는 자동 숨기기 단추를 표시 하거나 숨길를 호출할 때 `ShowPane`합니다. 아니면 도킹 가능한 창 활성화 또는 비활성화 하 고 해당 관련된 자동 숨기기 도구 모음이 나 자동 숨기기 단추는 항상 표시 됩니다.  
  
 개별 창에 대 한 기본 동작을 변경 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
 `m_bHideInAutoHideMode`의 기본값은 `FALSE`입니다.  
  
##  <a name="a-nameisinfloatingmultipaneframewnda--cdockablepaneisinfloatingmultipaneframewnd"></a><a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 다중 창 프레임 창에는 창 인지를 지정 ( [CMultiPaneFrameWnd 클래스](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 다중 창 프레임 창의 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisresizablea--cdockablepaneisresizable"></a><a name="isresizable"></a>CDockablePane::IsResizable  
 창 크기를 조정할 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 있는 경우 크기를 조정할 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 도킹 가능한 창과 크기를 조정할 수는 있습니다. 크기 조정를 방지 하려면 파생된 클래스에서이 메서드를 재정의 하 고 반환 `FALSE`합니다. 한 `FALSE` 값 이면 실패 한 `ASSERT` 에서 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)합니다. 사용 하 여 [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) 대신 부모 프레임 내의 창을 도킹 합니다.  
  
 창 크기를 조정할 수 있는 수 float 나 자동 숨김 모드로 전환 및 부모 프레임의 외부 가장자리에 항상 있습니다.  
  
##  <a name="a-nameistablocationbottoma--cdockablepaneistablocationbottom"></a><a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 탭 맨 위 또는 맨 아래 창에 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 창, 맨 아래에 배치 하는 경우 `FALSE` 탭 창의 위쪽에 배치 하는 경우.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom)합니다.  
  
##  <a name="a-nameistrackeda--cdockablepaneistracked"></a><a name="istracked"></a>CDockablePane::IsTracked  
 사용자가 창을 이동할 수 있는지 여부를 지정 합니다.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 고, 이동 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameisvisiblea--cdockablepaneisvisible"></a><a name="isvisible"></a>CDockablePane::IsVisible  
 현재 창이 표시 되는지를 결정 합니다.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 가능한 창에 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창에 표시 되는지 여부를 확인 하려면이 메서드를 호출 합니다. 이 메서드를 사용 하 여 호출 하는 대신 [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) 또는 대 한 테스트는 `WS_VISIBLE` 스타일입니다. 반환 된 표시 여부 상태에 따라 달라 집니다 자동 숨기기 모드의 활성화 여부의 값은 [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) 속성입니다.  
  
 도킹 가능한 창 자동 숨기기 모드에 있으면 및 `IsHideInAutoHideMode` 반환 `FALSE` 표시 여부 상태는 항상 `FALSE`입니다.  
  
 도킹 가능한 창 자동 숨기기 모드에 있으면 및 `IsHideInAutoHideMode` 반환 `TRUE` 표시 여부 상태 관련된 자동 숨기기 도구 모음의 표시 여부 상태에 따라 달라 집니다.  
  
 표시 여부 상태에 따라 결정 됩니다 도킹 가능한 창 자동 숨기기 모드에 없는 경우는 [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) 메서드.  
  
##  <a name="a-namembdisableanimationa--cdockablepanembdisableanimation"></a><a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 도킹 가능한 창 자동 숨기기 애니메이션 되지 않는지 여부를 지정 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="a-namembhideinautohidemodea--cdockablepanembhideinautohidemode"></a><a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 창 자동 숨기기 모드일 때 창 동작을 결정 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>주의  
 이 값에 응용 프로그램에서 모든 도킹 창을 영향을 줍니다.  
  
 이 멤버를 설정 하는 경우 `TRUE`, 도킹 가능 창을 숨겨지거나를 호출할 때가 자동 숨기기 관련된 도구 모음과 단추 함께 표시 되는 [CDockablePane::ShowPane](#showpane)합니다.  
  
 이 멤버를 설정 하는 경우 `FALSE`, 도킹 가능 창을 활성화 또는 비활성화를 호출할 때 [CDockablePane::ShowPane](#showpane)합니다.  
  
##  <a name="a-namemnslidestepsa--cdockablepanemnslidesteps"></a><a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 자동 숨기기 모드일 때 창 애니메이션 속도 지정 합니다.  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>주의  
 더 빠른 애니메이션 효과 위해이 값을 줄입니다. 느린 애니메이션 효과 위해이 값을 늘리십시오.  
  
##  <a name="a-nameonafterchangeparenta--cdockablepaneonafterchangeparent"></a><a name="onafterchangeparent"></a>CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndOldParent`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonafterdockfromminiframea--cdockablepaneonafterdockfromminiframe"></a><a name="onafterdockfromminiframe"></a>CDockablePane::OnAfterDockFromMiniFrame  
 프레임 창에는 부동 도킹 모음 도킹 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다.  
  
##  <a name="a-nameonbeforechangeparenta--cdockablepaneonbeforechangeparent"></a><a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 프레임 워크는 창의 부모를 변경 하기 전에이 메서드를 호출 합니다.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndNewParent`  
 새 부모 창에 대 한 포인터입니다.  
  
 [in] `bDelay`  
 `BOOL`경우에 창은 도킹 된 도킹 레이아웃의 다시 계산을 지연 시키는 여부를 지정 합니다. 자세한 내용은 참조 [CDockablePane::UndockPane](#undockpane)합니다.  
  
### <a name="remarks"></a>주의  
 창이 도킹 되어 있는 새 부모 도킹을 허용 하지 않는 경우이 메서드 창에서 도킹 해제 합니다.  
  
 탭된 문서 창에서 변환 되는,이 메서드는 최근의 도킹 위치를 저장 합니다. 최근 도킹 위치를 사용 하 여 도킹 된 상태로 변환 될 때 창 위치를 복원 하는 프레임 워크입니다.  
  
##  <a name="a-nameonbeforefloata--cdockablepaneonbeforefloat"></a><a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 프레임 워크는 창 하기 전에이 메서드 전환 움직이는 상태로 호출 합니다.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectFloat`  
 부동 상태일 때 창의 크기와 위치를 지정 합니다.  
  
 [in] `dockMethod`  
 도킹 방법을 지정합니다. 참조 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) 가능한 값의 목록에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 수 놓을지; 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 float로에 대 한이 되 면 프레임 워크에 의해 호출 됩니다. 창에서 표시 하기 전에 처리를 수행 하려는 경우이 메서드는 파생된 클래스에서 재정의할 수 있습니다.  
  
##  <a name="a-nameonpressbuttonsa--cdockablepaneonpressbuttons"></a><a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 사용자가 아닌 다른 캡션 단추를 누를 때 호출 된 `AFX_HTCLOSE` 및 `AFX_HTMAXBUTTON` 단추입니다.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHit`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창 캡션에 사용자 지정 단추를 추가 하는 경우 사용자가 단추를 누를 때 알림을 받으려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameonslidea--cdockablepaneonslide"></a><a name="onslide"></a>CDockablePane::OnSlide  
 창 자동 숨기기 모드일 때 애니메이션 효과를 주는 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSlideOut`  
 `TRUE`창을 표시 하려면 `FALSE` 창을 숨기려면 합니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 자동 숨기기 효과 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-nameremovefromdefaultpanedividiera--cdockablepaneremovefromdefaultpanedividier"></a><a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 프레임 워크는 창 고정 해제 되는 경우이 메서드를 호출 합니다.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>주의  
 이 메서드를 기본 창 구분선 설정 `NULL` 창에서 해당 컨테이너에서 제거 합니다.  
  
##  <a name="a-namereplacepanea--cdockablepanereplacepane"></a><a name="replacepane"></a>CDockablePane::ReplacePane  
 창을 지정 된 창으로 바꿉니다.  
  
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
 경우 `TRUE`, 새 창의 부모 항목의 이전 창 도킹 관리자에 등록 됩니다. 새 창은 도킹 관리자에 의해 유지 관리 되는 창의 목록에서 이전 창의 인덱스에 삽입 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`교체에 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namerestoredefaultpanedividera--cdockablepanerestoredefaultpanedivider"></a><a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 창을 deserialize 되 면 프레임 워크는 기본 창 구분선을 복원 하려면이 메서드를 호출 합니다.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>주의  
 복원 된 기본 창 구분선 있는 경우 현재 기본 창 구분선을 대체 합니다.  
  
##  <a name="a-namesetautohidemodea--cdockablepanesetautohidemode"></a><a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 표시 사이의 도킹 창 설정/해제 하 고 자동 숨기기 모드입니다.  
  
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
 현재 자동 숨기기 도구 모음에 대 한 포인터입니다. 수 `NULL`합니다.  
  
 [in] `bUseTimer`  
 창 자동 숨기기 모드로 전환할 때 자동 숨기기 효과 사용 하 여 또는 즉시 창을 숨기려면 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 자동 숨기기 모드로 전환할 경우 결과로 생성 된 자동 숨기기 도구 모음 또는 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창 자동 숨기기 모드로 일반 도킹 모드로 전환할 수 있는 핀 단추를 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.  
  
 도킹 가능한 창 자동 숨기기 모드로 전환할 프로그래밍 방식으로이 메서드를 호출 합니다. 창을 주 프레임 창에 도킹할 수 해야 ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) 에 대 한 유효한 포인터를 반환 해야는 [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="a-namesetautohideparentsa--cdockablepanesetautohideparents"></a><a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 자동 숨기기 단추와 창 자동 숨기기 도구 모음을 설정합니다.  
  
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
  
##  <a name="a-namesetlastpercentinpanecontainera--cdockablepanesetlastpercentinpanecontainer"></a><a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 창을 해당 컨테이너에서 차지 하는 공간의 백분율을 설정 합니다.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `n`  
 `int` 창에서 해당 컨테이너에서 차지 하는 공간의 백분율을 지정 하는 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 창 레이아웃 다시 계산할 때 새 값을 사용 하 여 조정 합니다.  
  
##  <a name="a-namesetrestoreddefaultpanedividera--cdockablepanesetrestoreddefaultpanedivider"></a><a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 복원 된 기본 창 구분선을 설정합니다.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hRestoredSlider`  
 창 구분선 (슬라이더)에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 복원 된 기본 창 구분선 창을 deserialize 될 때 얻습니다. 자세한 내용은 참조 [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)합니다.  
  
##  <a name="a-namesettabbedpanertca--cdockablepanesettabbedpanertc"></a><a name="settabbedpanertc"></a>CDockablePane::SetTabbedPaneRTC  
 두 개의 창이 함께 도킹할 때 생성 되는 탭된 창에 대 한 런타임 클래스 정보를 설정 합니다.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRTC`  
 탭된 창에 대 한 런타임 클래스 정보입니다.  
  
### <a name="remarks"></a>주의  
 동적으로 생성 하는 탭된 창에 대 한 런타임 클래스 정보를 설정 하려면이 메서드를 호출 합니다. 사용자가 하나의 창이 다른 창 캡션의 끌면 또는 호출 하는 경우 발생할 수 있습니다는 [CDockablePane::AttachToTabWnd](#attachtotabwnd) 메서드를 프로그래밍 방식으로 두 개의 도킹 가능한 창에서 탭된 창 만들기.  
  
 기본 런타임 클래스에 따라 설정 되는 `dwTabbedStyle` 의 매개 변수 [CDockablePane::Create](#create) 및 [CDockablePane::CreateEx](#createex)합니다. 새 탭된 창으로 사용자 지정 하려면 다음 클래스 중 하나에서 클래스를 파생 합니다.  
  
- [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)  
  
- [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
 그런 다음이 메서드는 런타임 클래스 정보에 대 한 포인터를 호출 합니다.  
  
##  <a name="a-nameshowpanea--cdockablepaneshowpane"></a><a name="showpane"></a>CDockablePane::ShowPane  
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
 `TRUE`도킹 레이아웃; 조정 지연 `FALSE` 즉시 도킹 레이아웃을 조정할 수 있습니다.  
  
 [in] `bActivate`  
 `TRUE`표시 될 때 창 활성화 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 대신이 메서드를 호출 하는 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) 도킹 가능한 창 숨기기 또는 표시 하는 경우.  
  
##  <a name="a-nameslidea--cdockablepaneslide"></a><a name="slide"></a>CDockablePane::Slide  
 자동 숨기기 모드에 있는 창 애니메이션을 적용 합니다.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSlideOut`  
 `TRUE`창을 표시 하려면 `FALSE` 창을 숨기려면 합니다.  
  
 [in] `bUseTimer`  
 `TRUE`자동 숨기기 효과; 창 표시 / 숨기기를 `FALSE` 표시 하거나 즉시 창을 숨길 수 있습니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 자동 숨기기 모드에 있는 창에 애니메이션을 적용 하려면이 메서드를 호출 합니다.  
  
 이 메서드는 사용 된 `CDockablePane::m_nSlideDefaultTimeOut` 슬라이드 효과 대 한 시간 초과 확인 하는 값입니다. 시간 제한의 기본값은 1입니다. 자동 숨기기 알고리즘을 사용자 지정 하는 경우 제한 시간을 변경 하려면이 멤버를 수정 합니다.  
  
##  <a name="a-nametoggleautohidea--cdockablepanetoggleautohide"></a><a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 창 항상 표시 및 자동 숨김 모드를 전환합니다.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>주의  
 이 메서드를 호출 하 여 창의 자동 숨기기 모드를 전환 [CDockablePane::SetAutoHideMode](#setautohidemode)합니다.  
  
##  <a name="a-nameundockpanea--cdockablepaneundockpane"></a><a name="undockpane"></a>CDockablePane::UndockPane  
 창을 주 프레임 창 또는 미니 프레임 창 컨테이너에서 도킹 해제 합니다.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDelay`  
 `TRUE`도킹 레이아웃; 계산을 지연 `FALSE` 를 도킹 레이아웃을 즉시 다시 계산 합니다.  
  
### <a name="remarks"></a>주의  
 주 프레임 창 또는 다중 미니 프레임 창 컨테이너 (단일 미니 프레임 창을 다른 창에 부동 창)에서 창을 도킹 해제 하려면이 메서드를 호출 합니다.  
  
 해야 고정을 해제 한 창에서 수행 되지 않는 하는 모든 외부 작업을 수행 하기 전에 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)합니다. 예를 들어 이동할 프로그래밍 방식으로 한 위치에서 다른 창을 고정을 해제 해야 합니다.  
  
 프레임 워크 소멸 되기 전에 창이 자동으로 도킹 해제 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane 클래스](../../mfc/reference/cpane-class.md)

