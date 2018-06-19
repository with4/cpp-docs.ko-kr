---
title: CPaneFrameWnd 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
dev_langs:
- C++
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6846f50b0e89193992a42ea50e785009f31e6d19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378789"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd 클래스
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 하나의 창이 포함된 미니 프레임 창을 구현합니다. 창은 창의 클라이언트 영역을 채웁니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPaneFrameWnd::AddPane](#addpane)|창을 추가합니다.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|전역 목록에서 창을 추가하거나 제거합니다.|  
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|미니 프레임 창의 레이아웃을 조정합니다.|  
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||  
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|미니 프레임 창의 테두리 크기를 계산합니다.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹된 창의 예상 사각형을 계산합니다.|  
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.|  
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.|  
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|창을 탭된 문서로 변환합니다.|  
|[CPaneFrameWnd::Create](#create)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|  
|[CPaneFrameWnd::CreateEx](#createex)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|  
|[CPaneFrameWnd::DockPane](#dockpane)|창을 도킹합니다.|  
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.|  
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|사용자가 제공한 지점을 포함하는 미니 프레임 창을 찾습니다.|  
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|미니 프레임 창 캡션의 높이를 반환합니다.|  
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|미니 프레임 창 캡션의 경계 사각형을 계산합니다.|  
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|캡션 텍스트를 반환합니다.|  
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||  
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|도킹 모드를 반환합니다.|  
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.|  
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||  
|[CPaneFrameWnd::GetPane](#getpane)|미니 프레임 창에 포함된 창을 반환합니다.|  
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|미니 프레임 창에 포함된 창 수를 반환합니다.|  
|[CPaneFrameWnd::GetParent](#getparent)||  
|[CPaneFrameWnd::GetPinState](#getpinstate)||  
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||  
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|미니 프레임 창에 포함된 표시 창 수를 반환합니다.|  
|[CPaneFrameWnd::HitTest](#hittest)|미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.|  
|[CPaneFrameWnd::IsCaptured](#iscaptured)||  
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||  
|[CPaneFrameWnd::IsRollDown](#isrolldown)|미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.|  
|[CPaneFrameWnd::IsRollUp](#isrollup)|미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.|  
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|도킹 타이머를 중지합니다.|  
|[CPaneFrameWnd::LoadState](#loadstate)|레지스트리에서 창의 상태를 로드합니다.|  
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|도킹 가능한지 여부를 결정합니다.|  
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|가장 최근 위치에 미니 프레임 창을 도킹합니다.|  
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|롤업 타이머를 중지합니다.|  
|[CPaneFrameWnd::OnMovePane](#onmovepane)|지정된 오프셋만큼 미니 프레임 창을 이동합니다.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|포함된 창의 레이아웃을 조정합니다.|  
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|롤업 타이머를 설정합니다.|  
|[CPaneFrameWnd::OnShowPane](#onshowpane)|미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.|  
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.|  
|[CPaneFrameWnd::Pin](#pin)||  
|`CPaneFrameWnd::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) Windows 함수로 디스패치되기 전에 [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) 클래스가 이 메시지를 해석하는 데 사용됩니다.|  
|[CPaneFrameWnd::RedrawAll](#redrawall)|모든 미니 프레임 창을 다시 그립니다.|  
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.|  
|[CPaneFrameWnd::RemovePane](#removepane)|미니 프레임 창에서 창을 제거합니다.|  
|[CPaneFrameWnd::ReplacePane](#replacepane)|한 창을 다른 창으로 대체합니다.|  
|[CPaneFrameWnd::SaveState](#savestate)|레지스트리에 창의 상태를 저장합니다.|  
|`CPaneFrameWnd::Serialize`|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.|  
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|캡션 단추를 설정합니다.|  
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||  
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||  
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|도킹 타이머를 설정합니다.|  
|[CPaneFrameWnd::SetDockState](#setdockstate)|도킹 상태를 설정합니다.|  
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||  
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.|  
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|포함된 창과 크기가 같도록 미니 프레임 창의 크기를 조정합니다.|  
|[CPaneFrameWnd::StartTearOff](#starttearoff)|메뉴를 분리합니다.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|미니 프레임 창의 테두리를 그립니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|`CS_SAVEBITS` 클래스 스타일을 사용하여 창 클래스를 등록할지 여부를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 창이 도킹된 상태에서 부동 상태로 전환되면 프레임워크에서 자동으로 `CPaneFrameWnd` 개체를 만듭니다.  
  
 내용을 표시(즉시 도킹)하거나 끌기 사각형을 사용하여(표준 도킹) 미니 프레임 창을 끌 수 있습니다. 미니 프레임 컨테이너 창의 도킹 모드에 따라 미니 프레임의 끌기 동작이 결정됩니다. 자세한 내용은 참조 [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)합니다.  
  
 미니 프레임 창에 포함된 창 스타일에 따라 캡션에 단추가 표시됩니다. 창을 닫을 수 있는 경우 ( [cbasepane:: Canbeclosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), 닫기 단추를 표시 합니다. 창에 `AFX_CBRS_AUTO_ROLLUP` 스타일이 있는 경우 핀이 표시됩니다.  
  
 `CPaneFrameWnd`에서 클래스를 파생하는 경우 프레임워크에 만드는 방법을 알려야 합니다. 재정의 하 여 클래스를 만들거나 [cpane:: Createdefaultminiframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), 설정 또는 `CPane::m_pMiniFrameRTC` 멤버를 클래스에 대 한 런타임 클래스 정보를 가리킵니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>  CPaneFrameWnd::AddPane  
 창을 추가합니다.  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 추가할 창입니다.  
  
##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList  
 전역 목록에서 창을 추가하거나 제거합니다.  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 추가 또는 제거 하는 창입니다.  
  
 [in] `bAdd`  
 0이 아닌 경우 창에 추가 합니다. 0 인 경우, 창을 제거 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout  
 미니 프레임 창의 레이아웃을 조정합니다.  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize  
 미니 프레임 창의 테두리 크기를 계산합니다.  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectBorderSize`  
 미니 프레임 창의 테두리를 픽셀 단위로 크기를 포함합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 미니 프레임 창의 테두리의 크기를 계산 하기 위해 프레임 워크에서 호출 됩니다. 미니 프레임 창 도구 모음 포함 인지에 따라 달라 집니다 반환 되는 크기 [CDockablePane](../../mfc/reference/cdockablepane-class.md)합니다.  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect  
 도킹된 창의 예상 사각형을 계산합니다.  
  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndToDock`  
 도킹 창에 대 한 포인터입니다.  
  
 [in] `ptMouse`  
 마우스 위치입니다.  
  
 [out] `rectResult`  
 계산 된 사각형입니다.  
  
 [out] `bDrawTab`  
 경우 `TRUE`, 탭을 그립니다. 경우 `FALSE`, 탭 그리지 않습니다.  
  
 [out] `ppTargetBar`  
 대상 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자로 지정 된 지점에 창을 끌 경우는 창이 차지 하는 사각형을 계산 `ptMouse` 있습니다 도킹 하 고 있습니다.  
  
##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached  
 현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창에서 다른 창이 나 프레임 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane  
 미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDockingBar`  
 창입니다.  
  
### <a name="return-value"></a>반환 값  
 미니 프레임에 도킹할 수 있는 경우 0이 아닌 `pDockingBar`그렇지 않으면 0입니다.  
  
##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument  
 창을 탭된 문서로 변환합니다.  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>  CPaneFrameWnd::Create  
 미니 프레임 창을 만들고에 연결 된 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszWindowName`  
 미니 프레임 창에 표시할 텍스트를 지정 합니다.  
  
 [in] `dwStyle`  
 창 스타일을 지정합니다. 자세한 내용은 참조 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.  
  
 [in] `rect`  
 초기 크기와 미니 프레임 창의 위치를 지정합니다.  
  
 [in] [out] `pParentWnd`  
 미니 프레임 창의 부모 프레임을 지정합니다. 이 값이 아니어야 `NULL`합니다.  
  
 [in] [out] `pContext`  
 사용자 정의 컨텍스트를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창 성공적으로 만들어진 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 미니 프레임 창은 두 단계에서 만들어집니다. 첫째, 프레임 워크 만듭니다는 `CPaneFrameWnd` 개체입니다. 둘째, 호출 `Create` Windows 미니 프레임 창을 만들고에 연결 하는 `CPaneFrameWnd` 개체입니다.  
  
##  <a name="createex"></a>  CPaneFrameWnd::CreateEx  
 미니 프레임 창을 만들고에 연결 된 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwStyleEx`  
 확장된 창 스타일을 지정합니다. 자세한 내용은 참조 [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
 [in] `lpszWindowName`  
 미니 프레임 창에 표시할 텍스트를 지정 합니다.  
  
 [in] `dwStyle`  
 창 스타일을 지정합니다. 자세한 내용은 참조 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.  
  
 [in] `rect`  
 초기 크기와 미니 프레임 창의 위치를 지정합니다.  
  
 [in] [out] `pParentWnd`  
 미니 프레임 창의 부모 프레임을 지정합니다. 이 값이 아니어야 `NULL`합니다.  
  
 [in] [out] `pContext`  
 사용자 정의 컨텍스트를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창 성공적으로 만들어진 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 미니 프레임 창은 두 단계에서 만들어집니다. 첫째, 프레임 워크 만듭니다는 `CPaneFrameWnd` 개체입니다. 둘째, 호출 `Create` Windows 미니 프레임 창을 만들고에 연결 하는 `CPaneFrameWnd` 개체입니다.  
  
##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane  
 창을 도킹합니다.  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `bWasDocked`  
 `TRUE` 창이 도킹 있는 경우가 이미 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 작업에 성공 하면는 `CDockablePane` 하 고, 그렇지 않으면 창에서 도킹 되어 있는지 `NULL`합니다.  
  
##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID  
 부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 찾을 창의 컨트롤 ID를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 컨트롤 ID; 인 창 그렇지 않으면 `NULL`없는 창 포함 하는 지정 된 컨트롤 id입니다.  
  
##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint  
 지정된 된 지점이 포함 된 미니 프레임 창을 찾습니다.  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pt`  
 화면 좌표 점입니다.  
  
 [in] `nSensitivity`  
 이 크기에 따라 미니 프레임 창의 검색 영역을 늘립니다. 미니 프레임 창이 지정된 된 점을 증가 된 영역에 해당 하는 경우 검색 조건을 충족 합니다.  
  
 [in] `pFrameToExclude`  
 검색에서 제외할 미니 프레임 창을 지정 합니다.  
  
 [in] `bFloatMultiOnly`  
 경우 `TRUE`만 있는 미니 프레임 창을 검색는 `CBRS_FLOAT_MULTI` 스타일입니다. 경우 `FALSE`, 모든 미니 프레임 창을 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 포함 된 미니 프레임 창에 대 한 포인터 `pt`고, 그렇지 않으면 `NULL`합니다.  
  
##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight  
 미니 프레임 창 캡션의 높이를 반환합니다.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 미니 프레임 창을 픽셀 단위로 높이입니다.  
  
### <a name="remarks"></a>설명  
 미니 프레임 창의 높이 확인 하려면이 메서드를 호출 합니다. 기본적으로는 높이가 설정 `SM_CYSMCAPTION`합니다. 자세한 내용은 참조 [GetSystemMetrics 함수](http://msdn.microsoft.com/library/windows/desktop/ms724385)합니다.  
  
##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect  
 미니 프레임 창 캡션의 경계 사각형을 계산합니다.  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectCaption`  
 크기와 화면 좌표에 미니 프레임 창 캡션의 위치를 포함합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 미니 프레임 창 캡션의 경계 사각형을 계산 하기 위해 프레임 워크에서 호출 됩니다.  
  
##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText  
 캡션 텍스트를 반환합니다.  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>반환 값  
 미니 프레임 창의 캡션 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 캡션 텍스트를 표시 하는 경우이 메서드는 프레임 워크에서 호출 됩니다.  
  
##  <a name="getdockingmanager"></a>  CPaneFrameWnd::GetDockingManager  

  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdockingmode"></a>  CPaneFrameWnd::GetDockingMode  
 도킹 모드를 반환합니다.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도킹 모드입니다. 다음 값 중 하나입니다.  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane  
 미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 미니 프레임 창에서 첫 번째 창 또는 `NULL` 경우 미니 프레임 창에 창이 없습니다.  
  
##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint  

  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpane"></a>  CPaneFrameWnd::GetPane  
 미니 프레임 창에 포함된 창을 반환합니다.  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 미니 프레임에 포함 된 창을 또는 `NULL` 경우 미니 프레임 창에 창이 없습니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount  
 미니 프레임 창에 포함된 창 수를 반환합니다.  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 미니 프레임 창의 창 수를 지정 합니다. 이 값은 0 일 수 있습니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getparent"></a>  CPaneFrameWnd::GetParent  

  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpinstate"></a>  CPaneFrameWnd::GetPinState  

  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getrecentfloatingrect"></a>  CPaneFrameWnd::GetRecentFloatingRect  

  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getvisiblepanecount"></a>  CPaneFrameWnd::GetVisiblePaneCount  
 미니 프레임 창에 포함된 표시 창 수를 반환합니다.  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 표시 창 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="hittest"></a>  CPaneFrameWnd::HitTest  
 미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 테스트 지점입니다.  
  
 [in] `bDetectCaption`  
 경우 `TRUE`, 캡션에 대해 지점을 확인 합니다. 경우 `FALSE`, 캡션을 무시 합니다.  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
|값|의미|  
|-----------|-------------|  
|`HTNOWHERE`|미니 프레임 창 외부에서는 지점이입니다.|  
|`HTCLIENT`|클라이언트 영역에 점이 의미 합니다.|  
|`HTCAPTION`|캡션을 점은입니다.|  
|`HTTOP`|점은 위쪽에 있습니다.|  
|`HTTOPLEFT`|점은 왼쪽 위에 있습니다.|  
|`HTTOPRIGHT`|오른쪽 상단에 점이 의미 합니다.|  
|`HTLEFT`|점은 왼쪽에 있습니다.|  
|`HTRIGHT`|점은 오른쪽에 있습니다.|  
|`HTBOTTOM`|점은 맨 아래에 있습니다.|  
|`HTBOTTOMLEFT`|점은 왼쪽 아래에 있습니다.|  
|`HTBOTTOMRIGHT`|점은 오른쪽 아래에 있습니다.|  
  
##  <a name="iscaptured"></a>  CPaneFrameWnd::IsCaptured  

  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isdelayshow"></a>  CPaneFrameWnd::IsDelayShow  

  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isrolldown"></a>  CPaneFrameWnd::IsRollDown  
 미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 미니 프레임 창을; 아래로 떨어질 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 미니 프레임 창을 롤 다운 되어야 하는지 여부를 결정 하는 프레임 워크에서 호출 됩니다. 포함 된 하나 이상의 창이 포함 된 미니 프레임 창에 대 한에서는 롤업/롤 다운 기능이 사용 되는 `AFX_CBRS_AUTO_ROLLUP` 플래그입니다. 이 플래그는 창 만들어질 때 설정 됩니다. 자세한 내용은 참조 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex)합니다.  
  
 기본적으로 프레임 워크는 창이 롤 다운 있는지 여부를 확인 하기 위해 미니 프레임 창 경계 사각형 안에 마우스 포인터 인지 확인 합니다. 파생된 클래스에서이 동작을 재정의할 수 있습니다.  
  
##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp  
 미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 미니 프레임 창을; 롤포워드해야 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 확인 여부 미니 프레임 창이 롤업 되어야 하는 프레임 워크에서 호출 됩니다. 포함 된 하나 이상의 창이 포함 된 미니 프레임 창에 대 한에서는 롤업/롤 다운 기능이 사용 되는 `AFX_CBRS_AUTO_ROLLUP` 플래그입니다. 이 플래그는 창 만들어질 때 설정 됩니다. 자세한 내용은 참조 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex)합니다.  
  
 기본적으로 프레임 워크는 겹쳐서 창에 있는지 여부를 결정 하는 미니 프레임 창 경계 사각형 안에 마우스 포인터 인지 확인 합니다. 파생된 클래스에서이 동작을 재정의할 수 있습니다.  
  
##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer  
 도킹 타이머를 중지합니다.  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState  
 레지스트리에서 창의 상태를 로드합니다.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `uiID`  
 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창 상태를 성공적으로 로드 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits  
 창 클래스를 등록할지 여부를 지정 된 `CS_SAVEBITS` 클래스 스타일입니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>설명  
 이 정적 멤버를 설정 `TRUE` 있는 미니 프레임 창 클래스를 등록 하는 `CS_SAVEBITS` 스타일입니다. 사용자가 미니 프레임 창을 끌 때 깜빡임 줄이기 하는 데 도움이 될 수 있습니다.  
  
##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock  
 도킹 가능한지 여부를 결정합니다.  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 도킹 하는 것이 가능 합니다. 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState  
 미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 미니 프레임 창 위로 또는 아래로 롤오버 되어야 하는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.  
  
 기본적으로 프레임 워크에서 호출 [CPaneFrameWnd::IsRollUp](#isrollup) 및 [CPaneFrameWnd::IsRollDown](#isrolldown) 하 고 방금 확장 또는 미니 프레임 창을 복원 합니다. 다른 시각적 효과 사용 하는 파생된 클래스에서이 메서드를 재정의할 수 있습니다.  
  
##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos  
 가장 최근 위치에 미니 프레임 창을 도킹합니다.  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder  
 미니 프레임 창의 테두리를 그립니다.  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 테두리를 그리는 데 사용 되는 장치 컨텍스트.  
  
### <a name="remarks"></a>설명  
 이 메서드는 미니 프레임 창의 테두리를 그리는 프레임 워크에서 호출 됩니다.  
  
##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer  
 롤업 타이머를 중지합니다.  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane  
 지정된 오프셋만큼 미니 프레임 창을 이동합니다.  
  
```  
virtual void OnMovePane(
    CPane* pBar,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 (무시 됨) 창에 대 한 포인터입니다.  
  
 [in] `ptOffset`  
 창을 이동 하는 기준인 오프셋입니다.  
  
##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout  
 미니 프레임 창 안에 창 레이아웃을 조정합니다.  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>설명  
 미니 프레임 창 안에 창 레이아웃을 조정 해야 하는 경우이 메서드를 호출 하는 프레임 워크입니다.  
  
 기본적으로는 창에 미니 프레임 창의 전체 클라이언트 영역을 채우는 데 배치 됩니다.  
  
##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer  
 롤업 타이머를 설정합니다.  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane  
 미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 되는 창 표시 또는 숨겨집니다.  
  
 [in] `bShow`  
 `TRUE` 창; 표시 됨 `FALSE` 창에서이 숨겨진 경우.  
  
### <a name="remarks"></a>설명  
 미니 프레임 창에 창 크기를 표시 하거나 숨길 때 프레임 워크에서 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="pin"></a>  CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bPin`  
  
### <a name="remarks"></a>설명  
  
##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint  
 미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 지점 화면 좌표에서 사용자가 클릭 합니다.  
  
 [in] `nSensitivity`  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] `bCheckVisibility`  
 `TRUE` 표시 창에만 반환 되어야 함을;를 지정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 사용자를 클릭 하는 창 또는 `NULL` 없는 창 해당 위치에 있는 경우.  
  
### <a name="remarks"></a>설명  
 지정된 된 점을 포함 하는 창을 가져오려면이 메서드를 호출 합니다.  
  
##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll  
 모든 미니 프레임 창을 다시 그립니다.  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 하 여 모든 미니 프레임 창을 업데이트 [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) 각 창에 대 한 합니다.  
  
##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes  
 잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane  
 미니 프레임 창에서 창을 제거합니다.  
  
```  
virtual void RemovePane(
    CBasePane* pWnd,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 제거 하 고 창에 대 한 포인터입니다.  
  
 [in] `bDestroy`  
 미니 프레임 창을 처리 방식을 지정 합니다. 경우 `bDestroy` 은 `TRUE`,이 메서드는 미니 프레임 창을 즉시 삭제 합니다. 이 경우 `FALSE`,이 메서드는 특정 지연 후 미니 프레임 창을 삭제 합니다.  
  
 [in] `bNoDelayedDestroy`  
 경우 `TRUE`지연 된, 소멸을 사용할 수 없습니다. 경우 `FALSE`지연 된, 소멸 사용 하도록 설정 합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는 즉시 또는 특정 지연 후 미니 프레임 창을 손상 될 수 있습니다. 미니 프레임 창 소멸을 연기 하려는 경우 전달 `FALSE` 에 `bNoDelayedDestroy` 매개 변수입니다. 지연 된 소멸 프레임 워크를 처리할 때이 발생 하는 `AFX_WM_CHECKEMPTYMINIFRAME` 메시지입니다.  
  
##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane  
 한 창을 다른 창으로 대체합니다.  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBarOrg`  
 원래 창에 대 한 포인터입니다.  
  
 [in] `pBarReplaceWith`  
 원래 창을 대체 하는 창에 대 한 포인터입니다.  
  
##  <a name="savestate"></a>  CPaneFrameWnd::SaveState  
 레지스트리에 창의 상태를 저장합니다.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `uiID`  
 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창 상태를 성공적으로 저장 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons  
 캡션 단추를 설정합니다.  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwButtons`  
 다음 값의 비트 OR 조합 합니다.  
  
- `AFX_CAPTION_BTN_CLOSE`  
  
- `AFX_CAPTION_BTN_PIN`  
  
- `AFX_CAPTION_BTN_MENU`  
  
- `AFX_CAPTION_BTN_CUSTOMIZE`  
  
##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDelayShow`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pManager`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer  
 도킹 타이머를 설정합니다.  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTimeOut`  
 제한 시간 값 (밀리초)입니다.  
  
##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState  
 도킹 상태를 설정합니다.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDockManager`  
 도킹 관리자에 대 한 포인터입니다.  
  
##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ptNew`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState  
 사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `preDockState`  
 가능한 값:  
  
- `PDS_NOTHING`,  
  
- `PDS_DOCK_REGULAR`,  
  
- `PDS_DOCK_TO_TAB`  
  
 [in] `pBarToDock`  
 도킹 창에 대 한 포인터입니다.  
  
 [in] `dockMethod`  
 도킹 메서드입니다. (이 매개 변수가 무시 됩니다.)  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 미니 프레임 창이 도킹; 되지 않은 경우 `FALSE` 고정 되어 있는 경우.  
  
##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent  
 포함 된 창에 해당 하는 미니 프레임 창의 크기를 조정 합니다.  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>설명  
 포함 된 창 크기에 미니 프레임 창의 크기를 조정 하려면이 메서드를 호출 합니다.  
  
##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff  
 메뉴를 분리합니다.  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenu`  
 메뉴에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공했으면 `TRUE`이고, 실패했으면 `FALSE`입니다.  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
  
### <a name="remarks"></a>설명  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDockingBar`  
 [in] `pTabbedBar`  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)
