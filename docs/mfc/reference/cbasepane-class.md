---
title: "CBasePane 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
dev_langs:
- C++
helpviewer_keywords:
- get_accState method
- get_accHelp method
- CBasePane class
- accLocation method
- accHitTest method
- get_accDescription method
- get_accDefaultAction method
- get_accName method
- get_accFocus method
- get_accRole method
- get_accValue method
- get_accChild method
- accSelect method
- get_accKeyboardShortcut method
- get_accChildCount method
- Serialize method
- PreTranslateMessage method
- get_accParent method
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
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
ms.openlocfilehash: 0444c0647d83a1e9b431dd0c5bdb369da213b91b
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cbasepane-class"></a>CBasePane 클래스
MFC의 모든 창에 대 한 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CBasePane::CBasePane`|기본 생성자입니다.|  
|`CBasePane::~CBasePane`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CBasePane::accHitTest`|화면의 지정된 지점에서 자식 요소나 자식 개체를 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CBasePane::accLocation`|지정된 된 개체에 대 한 현재 화면 위치를 검색 하는 프레임 워크에서 호출 됩니다. (재정의 [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane`이 메서드를 사용 하지 않습니다.|  
|`CBasePane::accSelect`|선택 영역을 수정하거나 지정된 개체의 키보드 포커스를 이동하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|창을 도킹 관리자에 게 추가 합니다.|  
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|도킹 레이아웃을 조정 하려면 도킹 관리자에 대 한 호출을 리디렉션합니다.|  
|[CBasePane::AdjustLayout](#adjustlayout)|창 내부 레이아웃을 조정 해야 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|컨트롤 막대의 가로 크기를 계산합니다.|  
|[CBasePane::CanAcceptPane](#canacceptpane)|다른 창에서 창으로 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanAutoHide](#canautohide)|창 자동 숨기기 모드를 지원 하는지 여부를 결정 합니다.|  
|[CBasePane::CanBeAttached](#canbeattached)|창에서 다른 창으로 고정 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeClosed](#canbeclosed)|창을 닫을 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeDocked](#canbedocked)|창에서 다른 창으로 고정 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeResized](#canberesized)|창 크기를 조정할 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|창에서 MDI 탭된 문서 변환할 수 있는지 여부를 지정 합니다.|  
|[CBasePane::CanFloat](#canfloat)|창에서 부동 상태로 있을 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanFocus](#canfocus)|창에서 포커스를 받을 수 있는지 여부를 지정 합니다.|  
|[CBasePane::CopyState](#copystate)|지정 된 창의 상태를 복사합니다.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|창에서 배치할 수 있는 경우 미니 프레임 창을 만듭니다.|  
|[CBasePane::CreateEx](#createex)|창 컨트롤을 만듭니다.|  
|[CBasePane::DockPane](#dockpane)|창을 다른 창 또는 프레임 창에 도킹합니다.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|런타임 형식 정보를 사용 하 여 창에서 도킹 합니다.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|도킹 가능한 창 프레임을 도킹합니다.|  
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|이 창 및 부모 프레임 간에 다른 창을 동적으로 삽입할 수 있는지 여부를 결정 합니다.|  
|[CBasePane::EnableDocking](#enabledocking)|수 있도록 창의 주 프레임에 도킹 합니다.|  
|[CBasePane::EnableGripper](#enablegripper)|위치 조정 막대를 사용 하지 않도록 설정 하거나 사용 합니다. 위치 조정 막대를 사용 하는 경우 사용자는 창 위치를 변경 하려면 끌 수 있습니다.|  
|`CBasePane::FillWindowRect`|내부적으로 사용 합니다.|  
|[CBasePane::FloatPane](#floatpane)|창에 배치 됩니다.|  
|`CBasePane::get_accChild`|지정된 자식의 `IDispatch` 인터페이스 주소를 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|이 개체에 속한 자식의 수를 검색 하는 프레임 워크에서 호출 됩니다. (재정의 [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|개체에 대 한 기본 동작을 설명 하는 문자열을 검색 하는 프레임 워크에서 호출 됩니다. (재정의 [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|지정한 개체의 모양을 설명하는 문자열을 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|키보드 포커스가 있는 개체를 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|개체에 대 한 도움말 속성 문자열을 검색 하는 프레임 워크에서 호출 됩니다. (재정의 [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|지정된 된 개체와 연관 된 WinHelp 파일의 전체 경로 및 해당 파일에서 해당 항목의 식별자를 검색 하는 프레임 워크에서 호출 됩니다. (재정의 [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|개체에 대 한 지정 된 바로 가기 키를 검색 하는 프레임 워크에서 호출 됩니다. (재정의 [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|지정된 개체의 이름을 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|검색 하는 프레임 워크에서 호출 된 `IDispatch` 개체의 부모에 대 한 인터페이스입니다. (재정의 [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|지정된 개체의 역할을 설명하는 정보를 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|이 개체의 선택된 자식 개체를 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|지정된 개체의 현재 상태를 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|지정된 개체의 값을 검색하기 위해 프레임워크에서 호출됩니다. (재정의 [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[CBasePane::GetCaptionHeight](#getcaptionheight)|캡션 높이를 반환합니다.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|컨트롤 막대 스타일을 반환합니다.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|현재 창 맞춤을 반환합니다.|  
|[CBasePane::GetDockingMode](#getdockingmode)|창에 대 한 현재 도킹 모드를 반환합니다.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|도크 사이트의 창에 대 한 창에 대 한 포인터를 반환 합니다.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|창에 적용 되는 CBRS_ALIGN_ 스타일을 반환 합니다.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|MFC에 관련 창 스타일을 반환합니다.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|창 아이콘에 대 한 핸들을 반환합니다.|  
|`CBasePane::GetPaneRect`|내부적으로 사용 합니다.|  
|[CBasePane::GetPaneRow](#getpanerow)|에 대 한 포인터를 반환 된 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)있는 창이 도킹 되어 있는 개체입니다.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|창 스타일을 반환 합니다.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|부모 도킹 사이트에 대 한 포인터를 반환합니다.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|부모 미니 프레임 창에 대 한 포인터를 반환합니다.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|부모 탭된 창에 대 한 포인터를 반환합니다.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|탭 내에 있는 부모 창에 대 한 포인터를 반환 합니다.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|프레임 워크는 창 보관에서 복원 되 면이 메서드를 호출 합니다.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|창에서 인쇄 미리 보기에서 숨겨져 있는지 여부를 지정 합니다.|  
|[CBasePane::InsertPane](#insertpane)|지정 된 창 도킹 관리자에 등록합니다.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|창에서 Active Accessibility 지원 하는지 여부를 지정 합니다.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|창 자동 숨기기 모드 인지 여부를 결정 합니다.|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|창 대화 상자 컨트롤 인지를 지정 합니다.|  
|[CBasePane::IsDocked](#isdocked)|창 도킹 되는지 여부를 결정 합니다.|  
|[CBasePane::IsFloating](#isfloating)|창이 부동 창인 있는지 여부를 결정 합니다.|  
|[CBasePane::IsHorizontal](#ishorizontal)|창에서 가로로 도킹 되는지 여부를 결정 합니다.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|다중 창 프레임 창에는 창이 되는지 여부를 지정 합니다.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|창에서 탭 문서로 MDI 자식 창에 추가 되어 있는지 확인 합니다.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|지정 여부는 `WS_VISIBLE` 의 창에 플래그를 설정 합니다.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|도킹 사이트 근처에 지정된 된 지점 인지 확인 합니다.|  
|[CBasePane::IsResizable](#isresizable)|창 크기를 조정할 수 있는지 여부를 결정 합니다.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|창 레지스트리에서 복원 되 고 있는지 여부를 결정 합니다.|  
|[CBasePane::IsTabbed](#istabbed)|창에서 탭 컨트롤의 탭된 창에 삽입 되었는지 여부를 결정 합니다.|  
|`CBasePane::IsTooltipTopmost`|내부적으로 사용 합니다.|  
|[CBasePane::IsVisible](#isvisible)|창이 표시 되는지를 결정 합니다.|  
|[CBasePane::LoadState](#loadstate)|레지스트리에서 창 상태를 로드합니다.|  
|[CBasePane::MoveWindow](#movewindow)|창으로 이동합니다.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|부모 창의 변경 된 경우에 프레임 워크에서 호출 합니다.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|창에서 해당 부모 창 변경 직전에 프레임 워크에 의해 호출 됩니다.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|프레임 워크는 캡션을 그릴 때이 메서드를 호출 합니다.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|이 메서드는 현재 사용 되지 않습니다.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|창의 목록에 있는 메뉴를 빌드할 때에 프레임 워크에서 호출 합니다.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|창을 부모 미니 프레임 창에서 제거 되는 프레임 워크에서 호출 합니다.|  
|[CBasePane::OnSetAccData](#onsetaccdata)|`CBasePane`이 메서드를 사용 하지 않습니다.|  
|`CBasePane::OnUpdateCmdUI`|내부적으로 사용 합니다.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|지정 된 지점이 포함 된 창을 반환 합니다.|  
|`CBasePane::PreTranslateMessage`|클래스에서 사용 하는 [CWinApp](../../mfc/reference/cwinapp-class.md) 으로 디스패치 되기 전에 창 메시지를 변환 하는 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. (재정의 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane`이 메서드를 사용 하지 않습니다.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 등록을 취소 하 고 도킹 관리자의 목록에서 제거 합니다.|  
|[CBasePane::SaveState](#savestate)|레지스트리에 창의 상태를 저장합니다.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|지정 된 장치 컨텍스트에 대 한 기본 글꼴을 선택합니다.|  
|`CBasePane::Serialize`|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다. (재정의 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|컨트롤 막대 스타일을 가져오거나 설정 합니다.|  
|[CBasePane::SetDockingMode](#setdockingmode)|창 도킹 모드를 설정합니다.|  
|`CBasePane::SetMDITabbed`|내부적으로 사용 합니다.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|창에 대 한 맞춤을 설정합니다.|  
|`CBasePane::SetPaneRect`|내부적으로 사용 합니다.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|창 스타일을 설정합니다.|  
|`CBasePane::SetRestoredFromRegistry`|내부적으로 사용 합니다.|  
|[CBasePane::SetWindowPos](#setwindowpos)|크기, 위치 및 창의 Z 순서를 변경합니다.|  
|[CBasePane::ShowPane](#showpane)|표시 창을 표시 하거나 숨깁니다.|  
|[CBasePane::StretchPane](#stretchpane)|창을 가로 또는 세로로 확장합니다.|  
|[CBasePane::UndockPane](#undockpane)|창에서 도킹 사이트, 기본 슬라이더 또는 미니 프레임 창의 현재 도킹 된 위치에서 제거 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|창의 배경을 채웁니다.|  
  
## <a name="remarks"></a>주의  
 파생 해야 MFC에서 사용할 수 있는 확장 된 도킹 기능을 지 원하는 창 클래스를 만들려는 경우 `CBasePane` 또는 [CPane 클래스](../../mfc/reference/cpane-class.md)합니다.  
  
## <a name="customization-tips"></a>사용자 지정 팁  
 다음 사용자 지정 팁 관련이 `CBasePane Class` 에서 상속 하는 클래스:  
  
-   창을 만들 때 몇 가지 새로운 스타일을 적용할 수 있습니다.  
  
    - `AFX_CBRS_FLOAT`창 부동 소수점을 만듭니다.  
  
    - `AFX_CBRS_AUTOHIDE`자동 숨김 모드로 사용 하도록 설정 합니다.  
  
    - `AFX_CBRS_CLOSE`창을 (숨김) 닫을 수 있습니다.  
  
     이 비트 OR 작업으로 결합할 수 있는 플래그입니다.  
  
 `CBasePane`이러한 플래그를 반영 하도록 다음 가상 부울 메서드를 구현: [CBasePane::CanBeClosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat)합니다. 동작을 사용자 지정 하는 파생된 클래스에서 재정의할 수 있습니다.  
  
-   재정의 하 여 도킹 동작을 사용자 지정할 수 있습니다 [CBasePane::CanAcceptPane](#canacceptpane)합니다. 반환 하 여 창이 `FALSE` 다른 창에 도킹 되지 않도록 하려면이 메서드로부터 합니다.  
  
-   만들려는 배치할 수 없음 및 다른 창 도킹 앞에서 금지 하는 정적 창 (Outlook 표시줄 OutlookDemo 예제에서와 유사), 비 부동으로 만들어야 하 고 재정의 [CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) 반환할 `FALSE`합니다. 기본 구현에서는 반환 `FALSE` 없이 창을 만드는 경우는 `AFX_CBRS_FLOAT` 스타일입니다.  
  
-   -1이 아닌 Id를 가진 모든 창 만들기  
  
-   창 표시 여부를 확인 하려면 사용 [CBasePane::IsVisible](#isvisible)합니다. 표시 여부 상태를 올바르게 처리의 탭 및 자동 숨김 모드입니다.  
  
-   비 부동 크기 조정 가능한 창 만들려는 만듭니다 없이 `AFX_CBRS_FLOAT` 스타일 및 호출 [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)합니다.  
  
-   창을 도킹 레이아웃에서 제외 하거나 해당 도킹 모음에서 도구 모음을 제거 하려면 호출 [CBasePane::UndockPane](#undockpane)합니다. 자동 숨김 모드에서 창 또는 탭 창 탭에 있는 창에 대 한이 메서드를 호출 하지 마십시오.  
  
-   자동 숨김 모드로 설정 되어 있는 창을 도킹을 해제 하거나 float 하려면를 호출 해야 [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) 와 `FALSE` 호출 하기 전에 첫 번째 인수로 [CBasePane::FloatPane](#floatpane) 또는 [CBasePane::UndockPane](#undockpane)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CBasePane` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 창을 검색 하는 방법을 보여 줍니다는 `CFrameWndEx` 클래스와 도킹 모드, 창 정렬 및 창 스타일을 설정 하는 방법입니다. 이 코드는는 [워드 패드 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_WordPad #&2;](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxbasepane.h  
  
##  <a name="accnotifyobjectfocusevent"></a>CBasePane::AccNotifyObjectFocusEvent  
 `CBasePane`이 메서드를 사용 하지 않습니다.  
  
```  
virtual void AccNotifyObjectFocusEvent(int);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `int`  
 사용되지 않습니다.  
  
##  <a name="addpane"></a>CBasePane::AddPane  
 창을 도킹 관리자에 게 추가 합니다.  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 추가 하는 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이것이 창을 도킹 관리자에 추가 하는 편리한 방법입니다. 이 메서드를 사용 하 여 상위 프레임의 형식을 분석 하는 코드를 작성할 필요가 없습니다.  
  
 자세한 내용은 참조 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 및 [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane)합니다.  
  
##  <a name="adjustdockinglayout"></a>CBasePane::AdjustDockingLayout  
 도킹 레이아웃을 조정 하려면 도킹 관리자에 대 한 호출을 리디렉션합니다.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `hdwp`  
 여러 창 위치를 포함 하는 구조체에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이것이 도킹 레이아웃을 조정 하는 편리한 방법입니다. 이 메서드를 사용 하 여 상위 프레임의 형식을 분석 하는 코드를 작성할 필요가 없습니다.  
  
 자세한 내용은 참조 [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>CBasePane::AdjustLayout  
 창의 내부 레이아웃을 조정 하려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>주의  
 프레임 워크는 창 내부 레이아웃을 조정 해야 하는 경우이 메서드를 호출 합니다. 기본 구현은 아무 작업도 수행합니다.  
  
##  <a name="calcfixedlayout"></a>CBasePane::CalcFixedLayout  
 컨트롤 막대의 가로 크기를 계산합니다.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bStretch`  
 모음을 프레임의 크기를 확장할 수 있는지 여부를 나타냅니다. `bStretch` 매개 변수는 0이 아닌 막대는 도킹 모음 (도킹 사용할 수 없음) 아니며 경우 0이 도킹 또는 부동 (도킹에 대 한 사용 가능) 하는 경우.  
  
 [in] `bHorz`  
 막대 방향을 가로 또는 세로로 임을 나타냅니다. `bHorz` 막대는 가로 방향 인지 하 고 0은 세로 방향 인지 하는 경우 매개 변수는 0이 아닌 값입니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대 크기 (픽셀)의 한 `CSize` 개체입니다.  
  
### <a name="remarks"></a>주의  
 에 주의 섹션을 참조 [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>CBasePane::CanAcceptPane  
 다른 창에서 창으로 도킹 될 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 도킹 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다른 창을 수락할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에 지정 된 창 도킹 하기 전에이 메서드를 호출 `pBar` 현재 창에 있습니다.  
  
 이 메서드를 사용 하 여 및 [CBasePane::CanBeDocked](#canbedocked) 창 응용 프로그램에 있는 다른 창에 도킹 하는 방법을 제어 하려면 메서드.  
  
 기본 구현은 `FALSE`를 반환합니다.  
  
##  <a name="canautohide"></a>CBasePane::CanAutoHide  
 창 자동 숨기기 모드를 지원 하는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 창 자동 숨기기 모드;를 지원 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크의 창 자동 숨기기 모드를 지원 하는지 확인 하려면이 함수를 호출 합니다.  
  
 생성 되는 동안 전달 하 여이 기능을 설정할 수 있습니다는 `AFX_CBRS_AUTOHIDE` 플래그를 [CBasePane::CreateEx](#createex)합니다.  
  
 기본 구현에 대 한 확인 하는 `AFX_CBRS_AUTOHIDE` 플래그입니다. 이 동작을 사용자 지정 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="canbeattached"></a>CBasePane::CanBeAttached  
 창에서 다른 창이 나 프레임 창에 도킹할 수 있는 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 다른 창이 나 프레임 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 `FALSE`를 반환합니다. 이 메서드를 호출 하지 않고 도킹 하는 기능을 사용할지 파생된 클래스에서 재정의 [CBasePane::EnableDocking](#enabledocking)합니다.  
  
##  <a name="canbeclosed"></a>CBasePane::CanBeClosed  
 창을 닫을 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창을 닫을 수 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 창을 닫을 수 있는지 여부를 확인 하려면이 메서드를 호출 합니다. 메서드에서 반환 되 면 `TRUE`, **닫기** 단추가 창의 제목 표시줄에 추가 되어 또는 미니 프레임 창의 제목 표시줄에,는 창이 부동 창인 경우.  
  
 생성 되는 동안 전달 하 여이 기능을 설정할 수 있습니다는 `AFX_CBRS_CLOSE` 플래그를 [CBasePane::CreateEx](#createex)합니다.  
  
 기본 구현에 대 한 확인 하는 `AFX_CBRS_CLOSE` 플래그입니다.  
  
##  <a name="canbedocked"></a>CBasePane::CanBeDocked  
 창에서 다른 창으로 고정 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDockBar`  
 다른 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 창을 다른 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에 지정 된 창 도킹 하기 전에이 메서드를 호출 `pDockBar` 현재 창에 있습니다.  
  
 이 메서드를 사용 하 여 및 [CBasePane::CanAcceptPane](#canacceptpane) 창 응용 프로그램에 있는 다른 창에 도킹 하는 방법을 제어 하려면 메서드.  
  
 기본 구현은 `FALSE`를 반환합니다.  
  
##  <a name="canberesized"></a>CBasePane::CanBeResized  
 창 크기를 조정할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 창 크기를 조정할 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 확인 하는 `AFX_CBRS_RESIZE` 에서 기본적으로 지정 하는 플래그 `CBasePane::OnCreate`합니다. 이 플래그를 지정 하지 않으면 도킹 관리자 플래그의 창 도킹 하는 대신 내부적으로 불가능 합니다.  
  
##  <a name="canbetabbeddocument"></a>CBasePane::CanBeTabbedDocument  
 창에서 MDI 탭된 문서 변환할 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 탭 문서로 변환할 수 있는 경우 그렇지 않으면 `FALSE`합니다. `CBasePane::CanBeTabbedDocument`는 항상 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 특정 개체에만 `CBasePane`-와 같은 파생 된 형식이 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md), 문서 탭된으로 변환 될 수 있습니다.  
  
##  <a name="canfloat"></a>CBasePane::CanFloat  
 창에서 부동 상태로 있을 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 창에서 부동 상태로 있을 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크의 창 부동 상태로 있을 수 있는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
 생성 되는 동안 전달 하 여이 기능을 설정할 수 있습니다는 `AFX_CBRS_FLOAT` 플래그를 [CBasePane::CreateEx](#createex)합니다.  
  
> [!NOTE]
>  프레임 워크에서는 비 부동 창 정적이 고 도킹 상태로 변경할 수 없습니다 가정 합니다. 따라서 프레임 워크는 비 부동 창으로 도킹 상태를 저장 하지 않습니다.  
  
 기본 구현에 대 한 확인 하는 `AFX_CBRS_FLOAT` 스타일입니다.  
  
##  <a name="canfocus"></a>CBasePane::CanFocus  
 창에서 포커스를 받을 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 포커스를 받을 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 포커스를 제어 하는 파생된 클래스에서이 메서드를 재정의 합니다. 예를 들어 도구 모음으로 포커스를 받을 수 없는 때문에이 메서드가 반환 `FALSE` 도구 모음 개체에 호출 됩니다.  
  
 프레임 워크는 창 도킹 되거나 확장 되 면 되 면 입력된 포커스를 설정 하려고 시도 합니다.  
  
##  <a name="copystate"></a>CBasePane::CopyState  
 지정 된 창의 상태를 복사합니다.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOrgBar`  
 다른 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 상태에서 복사 `pOrgBar` 이 창으로 합니다.  
  
##  <a name="createdefaultminiframe"></a>CBasePane::CreateDefaultMiniframe  
 창에서 배치할 수 있는 경우이 메서드를 미니 프레임 창을 만듭니다.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectInitial`  
 미니 프레임 창의 초기 좌표를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 새 미니 프레임 창에 대 한 포인터 또는 `NULL` 생성에 실패 하는 경우.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 창 움직이는 상태로 전환 될 때이 메서드를 호출 합니다. 메서드는 미니 프레임 창을 만들고이 창에는 창을 연결 합니다.  
  
 기본 구현은 `NULL`를 반환합니다.  
  
##  <a name="createex"></a>CBasePane::CreateEx  
 창 컨트롤을 만듭니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle=0,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwStyleEx`  
 확장된 스타일 (참조 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) 에 대 한 자세한 내용은).  
  
 [in] `lpszClassName`  
 창 클래스 이름입니다.  
  
 [in] `lpszWindowName`  
 창 이름입니다.  
  
 [in] `dwStyle`  
 창 스타일 (참조 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).  
  
 [in] `rect`  
 초기 사각형입니다.  
  
 [in] `pParentWnd`  
 부모 창에 대 한 포인터입니다.  
  
 [in] `nID`  
 창 ID를 지정 합니다. 고유 해야 합니다.  
  
 [in] `dwControlBarStyle`  
 창에 대 한 스타일 플래그입니다.  
  
 [in] `pContext`  
 에 대 한 포인터`CcreateContext`  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 성공적으로 만들어지면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 클래스의 창을 만듭니다 `lpszClassName`합니다. 지정 하는 경우 `WS_CAPTION`,이 메서드는 `WS_CAPTION` 스타일 비트가 및 집합 `CBasePane::m_bHasCaption` 를 `TRUE`라이브러리는 캡션이 있는 창을 지원 하지 않으므로.  
  
 자식 창 스타일 및 MFC 컨트롤 막대 (CBRS_) 스타일의 모든 조합을 사용할 수 있습니다.  
  
 창에 대 한 몇 가지 새로운 스타일을 추가 하는 라이브러리입니다. 다음 표에서 새로운 스타일을 보여 줍니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|창에서 부동 상태로 있을 수 있습니다.|  
|`AFX_CBRS_AUTOHIDE`|창 자동 숨기기 모드를 지원합니다.|  
|`AFX_CBRS_RESIZE`|창 크기를 조정할 수 있습니다. **중요:** 이 스타일 구현 되지 않았습니다.|  
|`AFX_CBRS_CLOSE`|창에서 닫을 수 있습니다.|  
|`AFX_CBRS_AUTO_ROLLUP`|창 부동 때 롤업 될 수 있습니다.|  
|`AFX_CBRS_REGULAR_TABS`|하나의 창이이 스타일이 적용 된 다른 창으로 도킹, 일반 탭된 창 생성 됩니다. (자세한 내용은 참조 [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md).)|  
|`AFX_CBRS_OUTLOOK_TABS`|하나의 창이이 스타일이 적용 된 다른 창으로 도킹, Outlook 스타일 탭된 창이 생성 됩니다. (자세한 내용은 참조 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 새 스타일을 사용 하려면에 지정 `dwControlBarStyle`합니다.  
  
##  <a name="dockpane"></a>CBasePane::DockPane  
 창을 다른 창 또는 프레임 창에 도킹합니다.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDockBar`  
 다른 창에 대 한 포인터입니다.  
  
 [in] `lpRect`  
 대상 사각형을 지정합니다.  
  
 [in] `dockMethod`  
 도킹 방법을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`컨트롤 막대 성공적으로 고정 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 창을 다른 창 또는 도킹 모음을 도킹 하려면이 함수를 호출 ( [CDockSite 클래스](../../mfc/reference/cdocksite-class.md))에 지정 된 `pDockBar`, 하거나 주 프레임 경우 `pDockBar` 는 `NULL`합니다.  
  
 `dockMethod`창 도킹 되는 방법을 지정 합니다. 참조 [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) 가능한 값의 목록에 대 한 합니다.  
  
##  <a name="dockpaneusingrtti"></a>CBasePane::DockPaneUsingRTTI  
 런타임 형식 정보를 사용 하 여 창에서 도킹 합니다.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bUseDockSite`  
 경우 `TRUE`, 도킹 사이트에 도킹 합니다. 경우 `FALSE`, 부모 프레임에 도킹 합니다.  
  
##  <a name="docktoframewindow"></a>CBasePane::DockToFrameWindow  
 도킹 가능한 창 프레임을 도킹합니다.  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 창에 도킹 하려면 부모 프레임 부분입니다.  
  
 [in] `lpRect`  
 원하는 크기입니다.  
  
 [in] `dwDockFlags`  
 무시됩니다.  
  
 [in] `pRelativeBar`  
 무시됩니다.  
  
 [in] `nRelativeIndex`  
 무시됩니다.  
  
 [in] `bOuterEdge`  
 경우 `TRUE` 로 지정 된 측면에 도킹 가능한 창과 다른 되며 `dwAlignment`, 창에서 다른 창 외부에 도킹 될 상위 프레임의 가장자리에 더 가깝게 합니다. 경우 `FALSE`, 창에서 클라이언트 영역의 가운데에 가깝게 도킹 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 실패 하는 경우 창 구분선 ( [CPaneDivider 클래스](../../mfc/reference/cpanedivider-class.md))를 만들 수 없습니다. 항상 그렇지 `TRUE`합니다.  
  
##  <a name="doesallowdyninsertbefore"></a>CBasePane::DoesAllowDynInsertBefore  
 이 창 및 부모 프레임 간에 다른 창을 동적으로 삽입할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다른 창; 삽입할 수는 있지만 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 사용자 전에이 창의 창을 동적으로 삽입할 수 있는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
 예를 들어, 응용 프로그램 (예: Outlook 표시줄) 프레임의 왼쪽에 도킹 창을 만듭니다. 첫 번째 창 왼쪽에 도킹 되는 다른 창에서 사용자를 방지 하려면이 메서드를 재정의 하 고 반환 `FALSE`합니다.  
  
 이 메서드를 재정의 하 고 반환 하는 것이 좋습니다 `FALSE` 비 부동 창에서 파생 된 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)합니다.  
  
 기본 구현은 `TRUE`를 반환합니다.  
  
##  <a name="dopaint"></a>CBasePane::DoPaint  
 창의 배경을 채웁니다.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 배경을 채울 현재 비주얼 관리자를 호출 하는 기본 구현 ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="enabledocking"></a>CBasePane::EnableDocking  
 수 있도록 창의 주 프레임에 도킹 합니다.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 사용할 수 있도록 도킹 맞춤을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 주 프레임에 도킹 맞춤을 사용 하도록 설정 하려면이 메서드를 호출 합니다. 조합에 전달할 수 있습니다 `CBRS_ALIGN_` 플래그 (자세한 내용은 참조 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking`내부 플래그를 설정 `CBasePane::m_dwEnabledAlignment` 프레임 워크는 창 도킹 한 경우이 플래그를 확인 합니다.  
  
 호출 [CBasePane::GetEnabledAlignment](#getenabledalignment) 는 창에 대 한 도킹 방식을 결정할 수 있습니다.  
  
##  <a name="enablegripper"></a>CBasePane::EnableGripper  
 위치 조정 막대를 사용 하지 않도록 설정 하거나 사용 합니다. 위치 조정 막대를 사용 하는 경우 사용자는 창 위치를 변경 하려면 끌 수 있습니다.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`위치 조정 막대;를 사용 하도록 설정 하려면 `FALSE` 사용 하지 않도록 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에서이 메서드를 사용 하 여 사용 하는 대신 위치 조정 막대를 사용 하도록 설정 하는 `WS_CAPTION` 스타일입니다.  
  
##  <a name="floatpane"></a>CBasePane::FloatPane  
 창에 배치 됩니다.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectFloat`  
 부동 창 나타나는 화면 좌표를 지정 합니다.  
  
 [in] `dockMethod`  
 창에서 float를 사용 하 여 도킹 메서드를 지정 합니다.  
  
 [in] `bShow`  
 부동 창 표시 되는지 여부를 지정 합니다 ( `TRUE`) 또는 숨겨진 ( `FALSE`).  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 성공적으로 확장 되 면 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 창에서 지정한 화면 위치에 배치 하려면이 메서드를 호출 `rectFloat`합니다.  
  
##  <a name="get_acchelptopic"></a>CBasePane::get_accHelpTopic  
 전체 경로 검색 하려면이 메서드를 호출 하는 프레임 워크는 `WinHelp` 지정된 된 개체와 해당 파일에서 해당 항목의 식별자와 연결 된 파일입니다.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszHelpFile`  
 주소에 `BSTR` 의 전체 경로 수신 하는 `WinHelp` 있는 경우 지정된 된 개체와 연결 된 파일.  
  
 [in] `varChild`  
 도움말 항목을 검색할 개체 또는 개체의 자식 요소 중 하나 인지를 지정 합니다. 이 매개 변수 수 `CHILDID_SELF` (개체에 대 한 도움말 항목 얻으려고) 또는 자식 ID (개체의 요소 자식 중 하나에 대 한 도움말 항목을 얻기).  
  
 [in] `pidTopic`  
 식별 된 `Help` 지정된 된 개체와 연결 된 파일 항목입니다.  
  
### <a name="return-value"></a>반환 값  
 `CBasePane`이 메서드를 구현 하지 않습니다. 따라서 `CBasePane::get_accHelpTopic` 항상 반환 `S_FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 MFC의 Active Accessibility 지원의 일부입니다. 개체에 대 한 도움말 정보를 제공 하기 위해 파생된 클래스에서이 함수를 재정의 합니다.  
  
##  <a name="get_accselection"></a>CBasePane::get_accSelection  
 프레임 워크는이 개체의 선택된 된 자식 개체를 검색 하려면이 메서드를 호출 합니다.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pvarChildren`  
 선택된 된 자식 개체를 식별 하는 정보를 받습니다.  
  
### <a name="return-value"></a>반환 값  
 `CBasePane`이 메서드를 구현 하지 않습니다. `pvarChildren`이(가) `NULL`이면 이 메서드는 `E_INVALIDARG`을(를) 반환합니다. 그렇지 않으면이 메서드가 반환 `DISP_E_MEMBERNOTFOUND`합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 MFC의 Active Accessibility 지원의 일부입니다. 창 없는 ActiveX 컨트롤 이외의 비 창 사용자 인터페이스 요소를 설정한 경우에 파생된 클래스에서이 함수를 재정의 합니다.  
  
##  <a name="getcaptionheight"></a>CBasePane::GetCaptionHeight  
 캡션 높이를 반환합니다.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 캡션 높이입니다.  
  
##  <a name="getcontrolbarstyle"></a>CBasePane::GetControlBarStyle  
 컨트롤 막대 스타일을 반환합니다.  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>반환 값  
 AFX_CBRS_ 플래그의 비트 OR 조합입니다.  
  
### <a name="remarks"></a>주의  
 반환 값은 다음 값의 조합입니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|컨트롤 막대 float를 만듭니다.|  
|`AFX_CBRS_AUTOHIDE`|자동 숨김 모드로 사용 하도록 설정 합니다.|  
|`AFX_CBRS_RESIZE`|컨트롤 막대의 크기 조정 수 있습니다. 이 플래그를 설정 하는 경우 컨트롤 막대는 도킹 가능한 창에 배치할 수 있습니다.|  
|`AFX_CBRS_CLOSE`|컨트롤 막대의 숨기기를 사용 하도록 설정 합니다.|  
  
##  <a name="getcurrentalignment"></a>CBasePane::GetCurrentAlignment  
 현재 창 맞춤을 반환합니다.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대의 현재 맞춤입니다. 다음 표에서 가능한 값을 보여 줍니다.  
  
|값|맞춤|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|왼쪽된 맞춤입니다.|  
|`CBRS_ALIGN_RIGHT`|오른쪽 맞춤 합니다.|  
|`CBRS_ALIGN_TOP`|위쪽 맞춤입니다.|  
|`CBRS_ALIGN_BOTTOM`|아래쪽 맞춤입니다.|  
  
##  <a name="getdockingmode"></a>CBasePane::GetDockingMode  
 창에 대 한 현재 도킹 모드를 반환합니다.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 창에서 끌어 경우 DT_STANDARD 끌기 사각형으로 화면에 표시 됩니다. 창의 내용을 끈 경우 DT_IMMEDIATE 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 창의 현재 도킹 모드를 확인 하려면이 메서드를 호출 합니다.  
  
 경우 `CBasePane::m_dockMode` 는 도킹 모드는 전역 도킹 모드에서 가져온 다음 (DT_UNDEFINED) 정의 되지 않았습니다 ( `AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 설정 하 여 `m_dockMode` 재정의 또는 `GetDockingMode` 각 창에 대 한 도킹 모드를 제어할 수 있습니다.  
  
##  <a name="getdocksiteframewnd"></a>CBasePane::GetDockSiteFrameWnd  
 에 대 한 포인터를 반환 된 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)있는 창이 도킹 되어 있는 개체입니다.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 창 도킹 사이트에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 창 도킹 사이트에 대 한 포인터를 검색 하려면이 메서드를 호출 합니다. 도크 사이트의 창이 부동 창인 경우 창에서 주 프레임에 고정 되어 있는 경우 주 프레임 창 또는 미니 프레임 창을 수 있습니다.  
  
##  <a name="getenabledalignment"></a>CBasePane::GetEnabledAlignment  
 창에 적용 되는 CBRS_ALIGN_ 스타일을 반환 합니다.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>반환 값  
 CBRS_ALIGN_ 스타일의 조합입니다. 다음 표에서 가능한 스타일을 보여 줍니다.  
  
|플래그|활성화 된 맞춤|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|왼쪽입니다.|  
|`CBRS_ALIGN_RIGHT`|권한입니다.|  
|`CBRS_ALIGN_TOP`|맨 위로.|  
|`CBRS_ALIGN_BOTTOM`|아래쪽입니다.|  
|`CBRS_ALIGN_ANY`|모든 플래그의 조합입니다.|  
  
### <a name="remarks"></a>주의  
 창에 대 한 활성화 된 맞춤을 확인 하려면이 메서드를 호출 합니다. 활성화 된 맞춤에 창을 도킹할 수 있는 주 프레임 창의 양쪽을 의미 합니다.  
  
 사용 하 여 도킹 맞춤을 사용 하도록 설정 [CBasePane::EnableDocking](#enabledocking)합니다.  
  
##  <a name="getmfcstyle"></a>CBasePane::GetMFCStyle  
 MFC에 관련 된 창 스타일을 반환 합니다.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 라이브러리 (AFX_CBRS_) 창 스타일의 조합입니다.  
  
##  <a name="getpaneicon"></a>CBasePane::GetPaneIcon  
 창 아이콘에 대 한 핸들을 반환합니다.  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bBigIcon`  
 32 픽셀 아이콘으로 32 픽셀을 지정 하는 경우 `TRUE`; 16 픽셀 아이콘으로 16 픽셀을 지정 하는 경우 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 창 아이콘에 대 한 핸들입니다. 실패할 경우 반환 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현 호출 하 여 [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon)합니다.  
  
##  <a name="getpanerow"></a>CBasePane::GetPaneRow  
 에 대 한 포인터를 반환 된 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)있는 창이 도킹 되어 있는 개체입니다.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터 `CDockingPanesRow` 창에서 고정 되어 있는 경우 또는 `NULL` 부동 창인 것입니다.  
  
### <a name="remarks"></a>주의  
 창을 도킹 될 위치 행에 액세스 하려면이 메서드를 호출 합니다. 예를 들어 특정 행에서 창을 정렬 하려면 호출 `GetPaneRow` 다음 호출 [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes)합니다.  
  
##  <a name="getpanestyle"></a>CBasePane::GetPaneStyle  
 창 스타일을 반환 합니다.  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대 스타일 (스타일 CBRS_ 포함)에 의해 설정 된의 조합 된 [CBasePane::SetPaneStyle](#setpanestyle) 메서드를 만들 때.  
  
##  <a name="getparentdocksite"></a>CBasePane::GetParentDockSite  
 부모 도킹 사이트에 대 한 포인터를 반환합니다.  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>반환 값  
 부모 도킹 사이트입니다.  
  
##  <a name="getparentminiframe"></a>CBasePane::GetParentMiniFrame  
 부모 미니 프레임 창에 대 한 포인터를 반환합니다.  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bNoAssert`  
 경우 `TRUE`, 유효 하지 않은 포인터에 대 한이 메서드를 확인 하지 않습니다. 응용 프로그램이 끝날 때이 메서드를 호출 하는 경우이 매개 변수를 설정 `TRUE`합니다.  
  
### <a name="return-value"></a>반환 값  
 부모 미니 프레임 창은 창이 부동 창인;에 대 한 유효한 포인터입니다. 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 부모 미니 프레임 창에 대 한 포인터를 검색 하려면이 함수를 호출 합니다. 이 메서드는 모든 부모를 반복 하 고에서 파생 된 개체에 대 한 검사 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)합니다.  
  
 사용 하 여 `GetParentMiniFrame` 하는 창이 부동 창인 있는지 여부를 결정 합니다.  
  
##  <a name="getparenttabbedpane"></a>CBasePane::GetParentTabbedPane  
 부모 탭된 창에 대 한 포인터를 반환합니다.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 특성이 있으면; 부모 탭된 창에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
##  <a name="getparenttabwnd"></a>CBasePane::GetParentTabWnd  
 탭 내에 있는 부모 창에 대 한 포인터를 반환 합니다.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `hWndTab`  
 반환 값에는 없는 경우 `NULL`,이 매개 변수 부모 탭된 창에 대 한 핸들을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 부모에 대 한 유효한 포인터를 탭 창 또는 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 부모 탭된 창에 대 한 포인터를 검색 합니다. 없는 경우도 호출 하는 충분 한 `GetParent`창을 도킹 래퍼 내에 있을 수 있으므로 ( [CDockablePaneAdapter 클래스](../../mfc/reference/cdockablepaneadapter-class.md)) 창 어댑터 내에서 또는 ( [CDockablePaneAdapter 클래스](../../mfc/reference/cdockablepaneadapter-class.md)). 사용 하 여 `GetParentTabWnd` (부모 탭된 창 이라고 가정) 이러한 경우에 대 한 유효한 포인터를 검색할 수 있습니다.  
  
##  <a name="getrecentvisiblestate"></a>CBasePane::GetRecentVisibleState  
 프레임 워크는 창 보관에서 복원 되 면이 메서드를 호출 합니다.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `BOOL` 최근 표시 되는 상태를 지정 하는 합니다. 경우 `TRUE`, 창이 표시 될 때 serialize 되 고 복원 하는 경우에 표시 되어야 합니다. 경우 `FALSE`, 직렬화 되 고 복원 하는 경우 숨겨야 하는 경우 창에서 숨겨져 있습니다.  
  
##  <a name="hideinprintpreviewmode"></a>CBasePane::HideInPrintPreviewMode  
 창에서 인쇄 미리 보기에서 숨겨져 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 인쇄 미리 보기에 표시 되지 않는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본 창 인쇄 미리 보기에 표시 되지 않습니다. 따라서이 메서드는 항상 반환 `TRUE`합니다.  
  
##  <a name="insertpane"></a>CBasePane::InsertPane  
 지정 된 창 도킹 관리자에 등록합니다.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 삽입 하 고 창에 대 한 포인터입니다.  
  
 [in] `pTarget`  
 인접 한 창에 대 한 포인터입니다.  
  
 [in] `bAfter`  
 경우 `TRUE`, `pControlBar` 뒤에 삽입 되어 `pTarget`합니다. 경우 `FALSE`, `pControlBar` 앞에 삽입 된 `pTarget`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면, `FALSE` 그렇지 않은 경우.  
  
##  <a name="isaccessibilitycompatible"></a>CBasePane::IsAccessibilityCompatible  
 창에서 Active Accessibility 지원 하는지 여부를 지정 합니다.  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 Active Accessibility; 지원 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isautohidemode"></a>CBasePane::IsAutoHideMode  
 창 자동 숨기기 모드 인지 여부를 결정 합니다.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 자동 숨기기; 모드인 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본 창 없습니다 자동 숨기기. 이 메서드는 항상 `FALSE`을 반환합니다.  
  
##  <a name="isdialogcontrol"></a>CBasePane::IsDialogControl  
 창 대화 상자 컨트롤 인지를 지정 합니다.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서이 대화 상자 컨트롤입니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 모든 창에 대 한 레이아웃 일관성을 유지 하는 프레임 워크입니다.  
  
##  <a name="isdocked"></a>CBasePane::IsDocked  
 창 도킹 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`부모 창의 미니 프레임 없는 경우 또는 다른 창; 미니 프레임에는 창 부동 창인 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isfloating"></a>CBasePane::IsFloating  
 창이 부동 창인 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 부동 창인; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환의 반대 값 [CBasePane::IsDocked](#isdocked)합니다.  
  
##  <a name="ishorizontal"></a>CBasePane::IsHorizontal  
 창에서 가로로 도킹 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 가로로; 고정 되어 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 확인에 대 한 현재 도킹 맞춤 `CBRS_ORIENT_HORZ`합니다.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CBasePane::IsInFloatingMultiPaneFrameWnd  
 다중 창 프레임 창에는 창 인지를 지정 ( [CMultiPaneFrameWnd 클래스](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창이 다중 창 프레임 창의 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 도킹 가능한 창과 다중 창 프레임 창에서 부동 상태로 있을 수 있습니다. 따라서 `CBasePane::IsInFloatingMultiPaneFrameWnd` 항상 반환 `FALSE`합니다.  
  
##  <a name="ismditabbed"></a>CBasePane::IsMDITabbed  
 창에서 탭 문서로 MDI 자식 창에 추가 되어 있는지 확인 합니다.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 탭 문서로 MDI 자식 창에 추가 된 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="ispanevisible"></a>CBasePane::IsPaneVisible  
 지정 여부는 `WS_VISIBLE` 의 창에 플래그를 설정 합니다.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 `WS_VISIBLE` 설정 하 고, 그렇지 않으면, `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 [CBasePane::IsVisible](#isvisible) 창 표시 여부를 확인 하려면.  
  
##  <a name="ispointneardocksite"></a>CBasePane::IsPointNearDockSite  
 도킹 사이트 근처에 지정된 된 지점 인지 확인 합니다.  
  
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
 중요 한 점은 가까운 가장자리를 지정 합니다. 가능한 값은 `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, 및`CBRS_ALIGN_BOTTOM`  
  
 [out] `bOuterEdge`  
 `TRUE`도킹 사이트;의 외부 테두리 주변 포인터가 있는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도킹 사이트; 근처 포인터가 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 요점은 도킹 사이트 근처의 민감도 도킹 관리자에서 설정 내에 없을 때입니다. 구분 기본값은 15 픽셀입니다.  
  
##  <a name="isresizable"></a>CBasePane::IsResizable  
 창 크기를 조정할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`사용자가 창 크기를 조정할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 창 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md) 크기를 조정할 수 있습니다.  
  
 상태 표시줄 ( [CMFCStatusBar 클래스](../../mfc/reference/cmfcstatusbar-class.md)) 및 도킹 모음 ( [CDockSite 클래스](../../mfc/reference/cdocksite-class.md)) 크기를 조정할 수 없습니다.  
  
##  <a name="isrestoredfromregistry"></a>CBasePane::IsRestoredFromRegistry  
 창 레지스트리에서 복원 되 고 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 레지스트리;에서 복원 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="istabbed"></a>CBasePane::IsTabbed  
 창에서 탭 컨트롤의 탭된 창에 삽입 되었는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`컨트롤 막대 탭 창의 탭에 삽입 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 직계 부모에 대 한 포인터를 검색 하 고 부모 런타임 클래스 인지 여부를 확인 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md)합니다.  
  
##  <a name="isvisible"></a>CBasePane::IsVisible  
 창이 표시 되는지를 결정 합니다.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 창의 표시 여부를 확인 하려면이 메서드를 사용 합니다. 사용 하지 않는 `::IsWindowVisible`합니다.  
  
 창에서 탭 하지는 경우 (참조 [CBasePane::IsTabbed](#istabbed)),이 메서드를 확인 하는 `WS_VISIBLE` 스타일입니다. 창에서 탭은이 메서드는 부모 탭된 창의 표시 여부를 확인 합니다. 부모 창을 표시 하지 않은 경우 함수 사용 하 여 창 탭의 표시 여부를 확인 하는 [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible)합니다.  
  
##  <a name="loadstate"></a>CBasePane::LoadState  
 레지스트리에서 창의 상태를 로드합니다.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `nIndex`  
 프로필 인덱스입니다.  
  
 [in] `uiID`  
 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 상태를 성공적으로 로드 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 레지스트리에서 창 상태를 로드 하려면이 메서드를 호출 합니다. 에 의해 저장 되는 추가 정보를 로드 하려면 파생된 클래스에서 재정의 [CBasePane::SaveState](#savestate)합니다.  
  
##  <a name="movewindow"></a>CBasePane::MoveWindow  
 창으로 이동합니다.  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 새 위치와 창의 크기를 지정 하는 사각형입니다.  
  
 [in] `bRepaint`  
 경우 `TRUE`, 창에서 다시 그려집니다. 경우 `FALSE`, 창 하지 다시 그려집니다.  
  
 [in] `hdwp`  
 지연 된 창 위치 구조에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 지연 된 창 위치 구조에 대 한 핸들 또는 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 전달 하는 경우 `NULL` 으로 `hdwp` 매개 변수를이 메서드는 창을 정상적으로 이동 합니다. 핸들을 전달 하는 경우이 메서드는 지연 된 창을 이동을 수행 합니다. 호출 하 여 핸들을 가져올 수 있습니다 [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) 또는이 메서드에 대 한 이전 호출의 반환 값을 저장 합니다.  
  
##  <a name="onafterchangeparent"></a>CBasePane::OnAfterChangeParent  
 프레임 워크의 창 부모 변경 된 후 호출 합니다.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndOldParent`  
 이전 부모에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크의 창 부모 변경 되 면, 일반적으로 도킹 또는 부동 소수점 작업으로 인해이 메서드를 호출 합니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="onbeforechangeparent"></a>CBasePane::OnBeforeChangeParent  
 창에서 해당 부모 창 변경 직전에 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndNewParent`  
 새 부모 창에 대 한 포인터입니다.  
  
 [in] `bDelay`  
 레이아웃 조정을 지연 해야 하는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 도킹, 부동 또는 자동 숨기기 작업으로 인해 일반적으로 창의 부모 변경 하기 바로 전에이 메서드를 호출 합니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="ondrawcaption"></a>CBasePane::OnDrawCaption  
 프레임 워크는 캡션을 그릴 때이 메서드를 호출 합니다.  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 없는 기능에 대 한는 `CBasePane` 클래스입니다.  
  
##  <a name="onmovepanedivider"></a>CBasePane::OnMovePaneDivider  
 이 메서드는 현재 사용 되지 않습니다.  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CPaneDivider*`  
 사용되지 않습니다.  
  
##  <a name="onpanecontextmenu"></a>CBasePane::OnPaneContextMenu  
 창의 목록에 있는 메뉴를 빌드할 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentFrame`  
 상위 프레임에 대 한 포인터입니다.  
  
 [in] `point`  
 바로 가기 메뉴의 위치를 지정합니다.  
  
### <a name="remarks"></a>주의  
 `OnPaneContextMenu`현재 프레임 창에 속하는 창의 목록을 유지 관리 하는 도킹 관리자를 호출 합니다. 이 메서드는 창 이름을 추가 하 고 바로 가기 메뉴를 표시 합니다. 메뉴에 있는 명령을 표시 하거나 개별 창을 숨깁니다.  
  
 이 동작을 사용자 지정 하려면이 메서드를 재정의 합니다.  
  
##  <a name="onremovefromminiframe"></a>CBasePane::OnRemoveFromMiniFrame  
 창을 부모 미니 프레임 창에서 제거 되는 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMiniFrame`  
 창에서 제거 되는 미니 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 창을 도킹, 예를 들어) (결과로 부모 미니 프레임 창에서 제거 될 때이 메서드를 호출 하는 프레임 워크입니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="onsetaccdata"></a>CBasePane::OnSetAccData  
 `CBasePane`이 메서드를 사용 하지 않습니다.  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lVal`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 항상 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="panefrompoint"></a>CBasePane::PaneFromPoint  
 지정 된 지점이 포함 된 창을 반환 합니다.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 포인트를 확인 하려면 화면 좌표에서 지정 합니다.  
  
 [in] `nSensitivity`  
 검색 영역에이 용량을 늘립니다. 주어진된 지점 증가 된 영역에 해당 하는 경우 창에서 검색 조건을 만족 합니다.  
  
 [in] `bExactBar`  
 `TRUE`무시 하려면는 `nSensitivity` 매개 변수 이거나, `FALSE`합니다.  
  
 [in] `pRTCBarType`  
 그렇지 않은 경우 `NULL`, 메서드는 지정 된 형식의 창만 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 `CBasePane`-파생 된 지정 된 지점을 포함 하는 개체 또는 `NULL` 없는 창을 찾을 수 없으면 합니다.  
  
##  <a name="recalclayout"></a>CBasePane::RecalcLayout  
 `CBasePane`이 메서드를 사용 하지 않습니다.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>CBasePane::RemovePaneFromDockManager  
 창을 등록을 취소 하 고 도킹 관리자의 목록에서 제거 합니다.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 제거할 창에 대 한 포인터입니다.  
  
 [in] `bDestroy`  
 경우 `TRUE`, 제거 창 소멸 됩니다.  
  
 [in] `bAdjustLayout`  
 경우 `TRUE`, 즉시 도킹 레이아웃을 조정 합니다.  
  
 [in] `bAutoHide`  
 경우 `TRUE`, 도킹 레이아웃은 자동 숨기기 모음 목록 관련이 있습니다. 경우 `FALSE`, 도킹 레이아웃은 일반 창의 목록 관련이 있습니다.  
  
 [in] `pBarReplacement`  
 제거 창을 대체 하는 창에 대 한 포인터입니다.  
  
##  <a name="savestate"></a>CBasePane::SaveState  
 레지스트리에 창의 상태를 저장합니다.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `nIndex`  
 프로필 인덱스입니다.  
  
 [in] `uiID`  
 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`상태는 성공적으로 저장 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크의 창 상태를 레지스트리에 저장할 때이 메서드를 호출 합니다. 재정의 `SaveState` 추가 정보를 저장 하는 파생된 클래스에 있습니다.  
  
##  <a name="selectdefaultfont"></a>CBasePane::SelectDefaultFont  
 지정 된 장치 컨텍스트에 대 한 기본 글꼴을 선택합니다.  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 기본값에 대 한 포인터 [CFont 클래스](../../mfc/reference/cfont-class.md) 개체입니다.  
  
##  <a name="setcontrolbarstyle"></a>CBasePane::SetControlBarStyle  
 컨트롤 막대 스타일을 가져오거나 설정 합니다.  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwNewStyle`  
 다음과 같은 가능한 값의 비트 OR 조합입니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|컨트롤 막대 float를 만듭니다.|  
|`AFX_CBRS_AUTOHIDE`|자동 숨김 모드로 사용 하도록 설정 합니다.|  
|`AFX_CBRS_RESIZE`|컨트롤 막대의 크기 조정 수 있습니다. 이 플래그를 설정 하는 경우 컨트롤 막대는 도킹 가능한 창에 배치할 수 있습니다.|  
|`AFX_CBRS_CLOSE`|컨트롤 막대의 숨기기를 사용 하도록 설정 합니다.|  
  
##  <a name="setdockingmode"></a>CBasePane::SetDockingMode  
 창 도킹 모드를 설정합니다.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dockModeNew`  
 창에 대 한 새 도킹 모드를 지정합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에는 두 가지 도킹 모드 지원: 표준 및 직접 실행 합니다.  
  
 표준 도킹 모드에서 끌기 사각형을 사용 하 여 창 및 미니 프레임 창을 이동 됩니다. 즉시 도킹 모드에서 컨트롤 막대 및 미니 프레임 창을 이동 즉시 해당 컨텍스트와 함께 합니다.  
  
 처음에 도킹 모드에서 전역적으로 정의 된 [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal)합니다. 개별적으로 사용 하 여 각 창에 대 한 도킹 모드를 설정할 수는 `SetDockingMode` 메서드.  
  
##  <a name="setpanealignment"></a>CBasePane::SetPaneAlignment  
 창에 대 한 맞춤을 설정합니다.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwAlignment`  
 새 맞춤을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 프레임 워크는 다른 창을 주 프레임의 한 쪽에서 도킹 한 경우이 메서드를 호출 합니다.  
  
 다음 표에서 사용할 수 있는 값을 보여 줍니다. `dwAlignment`:  
  
|값|맞춤|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|왼쪽된 맞춤입니다.|  
|`CBRS_ALIGN_RIGHT`|오른쪽 맞춤 합니다.|  
|`CBRS_ALIGN_TOP`|위쪽 맞춤입니다.|  
|`CBRS_ALIGN_BOTTOM`|아래쪽 맞춤입니다.|  
  
##  <a name="setpanestyle"></a>CBasePane::SetPaneStyle  
 창 스타일을 설정합니다.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwNewStyle`  
 설정할 새 스타일을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 Afxres.h에 정의 되어 있는 CBRS_ 스타일 중 하나를 설정 하려면이 메서드를 사용할 수 있습니다. 창 스타일과 창 맞춤 함께 저장 되기 때문에 다음과 같이 현재 맞춤와 결합 하 여 새 스타일을 설정 합니다.  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="setwindowpos"></a>CBasePane::SetWindowPos  
 크기, 위치 및 창의 Z 순서를 변경합니다.  
  
```  
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndInsertAfter`  
 식별 된 `CWnd` 이 앞에 있는 개체 `CWnd` Z 순서에서 개체입니다. 자세한 내용은 참조 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)합니다.  
  
 [in] `x`  
 창 왼쪽의 위치를 지정합니다.  
  
 [in] `y`  
 창의 위쪽 위치를 지정합니다.  
  
 [in] `cx`  
 창의 너비를 지정합니다.  
  
 [in] `cy`  
 창의 높이 지정합니다.  
  
 [in] `nFlags`  
 크기 및 위치 옵션을 지정합니다. 자세한 내용은 참조 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)합니다.  
  
 [in] `hdwp`  
 하나 이상의 창에 대 한 크기 및 위치 정보를 포함 하는 구조에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 지연 된 업데이트 된 창 위치 구조에 대 한 핸들 또는 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 경우 `pWndInsertAfter` 는 `NULL`,이 메서드는 호출 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)합니다. 경우 `pWndInsertAfter` 이 아닌 `NULL`,이 메서드는 호출 `DeferWindowPos`합니다.  
  
##  <a name="showpane"></a>CBasePane::ShowPane  
 표시 창을 표시 하거나 숨깁니다.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 표시 여부를 지정 합니다 ( `TRUE`) 또는 숨기기 ( `FALSE`)는 창입니다.  
  
 [in] `bDelay`  
 경우 `TRUE`, 도킹 레이아웃을 다시 계산 지연 됩니다.  
  
 [in] `bActivate`  
 경우 `TRUE`, 창 표시 되었을 때 활성화 됩니다.  
  
### <a name="remarks"></a>주의  
 이 메서드 하거나 창을 숨깁니다. 대신이 메서드를 사용 하 여 `ShowWindow` 하므로이 메서드는 변경의 창 표시 여부에 대 한 관련 도킹 관리자에 알립니다.  
  
 사용 하 여 [CBasePane::IsVisible](#isvisible) 는 창의 현재 표시 여부를 확인 하려면.  
  
##  <a name="stretchpane"></a>CBasePane::StretchPane  
 창을 가로 또는 세로로 확장합니다.  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nLength`  
 창에서 확장에 사용 되는 길이입니다.  
  
 [in] `bVert`  
 경우 `TRUE`, 창에서 세로 방향으로 확장 합니다. 경우 `FALSE`, 창에서 가로 방향으로 확장 합니다.  
  
### <a name="return-value"></a>반환 값  
 확대 된 창의 크기를 지정 합니다.  
  
##  <a name="undockpane"></a>CBasePane::UndockPane  
 창에서 도킹 사이트, 기본 슬라이더 또는 미니 프레임 창의 현재 도킹 된 위치에서 제거 합니다.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDelay`  
 True 이면 도킹 레이아웃 즉시 재계산 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 창 상태를 조작 하거나 창에서 도킹 레이아웃에서 제외 하려면이 메서드를 호출 합니다.  
  
 이 창을 사용 하 여 계속 하려는 경우 중 하나를 호출 [CBasePane::DockPane](#dockpane) 또는 [CBasePane::FloatPane](#floatpane) 전에이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)

