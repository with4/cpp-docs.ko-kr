---
title: CMFCAutoHideBar 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9c60ee3601cd4055e963997a6cd4f8bbd48b14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar 클래스
`CMFCAutoHideBar` 클래스는 자동 숨기기 기능을 구현하는 특수 도구 모음 클래스입니다.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>구문  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu`를 재정의합니다.)|  
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCAutoHideBar::Create](#create)|컨트롤 막대를 만들고 연결 하는 [CPane](../../mfc/reference/cpane-class.md) 개체입니다. (재정의 [cpane:: Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|특수 창 메뉴를 표시하려고 할 때 프레임워크에서 호출됩니다. (재정의 [cpane:: Onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(재정의 [cpane:: Setactiveingroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|창을 가로 또는 세로로 확장합니다. (재정의 [cbasepane:: Stretchpane](../../mfc/reference/cbasepane-class.md#stretchpane).)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|사용자 위에 마우스 커서를 배치 하는 경우는 순간 사이의 지연 시간을 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md) 프레임 워크 연결된 된 창이 표시 되 면 순간과 합니다.|  
  
## <a name="remarks"></a>설명  
 사용자가 도킹 창을 자동 숨기기 모드로 전환하면 프레임워크에서 자동으로 `CMFCAutoHideBar` 개체를 만듭니다. 또한 필요한 만듭니다 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 및 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) 개체입니다. 각 `CAutoHideDockSite` 개체는 개별 `CMFCAutoHideButton`에 연결됩니다.  
  
 `CMFCAutoHideBar` 클래스는 사용자의 마우스로 `CMFCAutoHideButton`을 가리킬 때 `CAutoHideDockSite`의 표시를 구현합니다. 도구 모음에서 WM_MOUSEMOVE 메시지를 받으면 `CMFCAutoHideBar`에서 타이머를 시작합니다. 타이머가 완료되면 도구 모음에 WM_TIMER 이벤트 알림을 보냅니다. 도구 모음은 마우스 포인터가 타이머가 시작될 때 배치되었던 것과 동일한 자동 숨기기 단추에 배치되었는지 확인하여 이 이벤트를 처리합니다. 그럴 경우 연결된 `CAutoHideDockSite`가 표시됩니다.  
  
 `m_nShowAHWndDelay`를 설정하여 타이머의 지연 길이를 제어할 수 있습니다. 기본값은 400ms입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCAutoHideBar` 개체를 생성하고 해당 `GetDockSiteRow` 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxautohidebar.h  
  
##  <a name="addautohidewindow"></a>  CMFCAutoHideBar::AddAutoHideWindow  
 자동으로 숨길 수 있도록 하는 기능을 `CDockablePane` 창에 추가합니다.  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pAutoHideWnd`  
 숨기려는 창입니다.  
  
 [in] `dwAlignment`  
 응용 프로그램 창에 자동 숨기기 단추의 맞춤을 지정하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 `dwAlignment` 매개 변수는 자동 숨기기 단추가 응용 프로그램에 있음을 나타냅니다. 이 매개 변수는 다음 값 중 하나가 될 수 있습니다.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="allowshowonpanemenu"></a>  CMFCAutoHideBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="calcfixedlayout"></a>  CMFCAutoHideBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="cmfcautohidebar"></a>  CMFCAutoHideBar::CMFCAutoHideBar  
 CMFCAutoHideBar 개체를 생성합니다.  
  
```  
CMFCAutoHideBar();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="create"></a>  CMFCAutoHideBar::Create  

  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszClassName`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `nID`  
 [in] `dwControlBarStyle`  
 [in] `pContext`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getfirstahwindow"></a>  CMFCAutoHideBar::GetFirstAHWindow  
 응용 프로그램의 첫 번째 자동 숨기기 창에 대한 포인터를 반환합니다.  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램의 첫 번째 자동 숨기기 창이거나, 없는 경우 NULL입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getvisiblecount"></a>  CMFCAutoHideBar::GetVisibleCount  
 표시되는 자동 숨기기 단추 수를 가져옵니다.  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>반환 값  
 표시되는 자동 숨기기 단추 수를 반환합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_nshowahwnddelay"></a>  CMFCAutoHideBar::m_nShowAHWndDelay  
 사용자 위에 마우스 커서를 배치 하는 경우는 순간 사이의 지연 시간을 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md) 프레임 워크 연결된 된 창이 표시 되 면 순간과 합니다.  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>설명  
 사용자 위에 마우스 커서를 배치 하는 경우는 `CMFCAutoHideButton`, 프레임 워크에 연결된 된 창이 표시 되기 전에 약간의 지연이 있습니다. 이 매개 변수 (밀리초)에 해당 지연의 길이 결정합니다.  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCAutoHideBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CPoint`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="removeautohidewindow"></a>  CMFCAutoHideBar::RemoveAutoHideWindow  
 자동 숨기기 창을 제거하고 삭제합니다.  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 CDockablePane * `pAutoHideWnd`  
 제거할 자동 숨기기 창입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 TRUE이고, 실패하면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setactiveingroup"></a>  CMFCAutoHideBar::SetActiveInGroup  
 자동 숨기기 막대에 활성으로 플래그를 지정합니다.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] BOOL `bActive`  
 활성으로 설정하려면 TRUE이고, 그러지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 참조 [cpane:: Setactiveingroup](../../mfc/reference/cpane-class.md#setactiveingroup)합니다.  
  
##  <a name="setrecentvisiblestate"></a>  CMFCAutoHideBar::SetRecentVisibleState  

  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bState`  
  
### <a name="remarks"></a>설명  
  
##  <a name="showautohidewindow"></a>  CMFCAutoHideBar::ShowAutoHideWindow  
 자동 숨기기 창을 표시합니다.  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] CDockablePane * `pAutoHideWnd`  
 [in] BOOL `bShow`  
 창을 표시하려면 TRUE입니다.  
  
 [in] BOOL `bDelay`  
 이 매개 변수는 무시됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 TRUE이고, 실패하면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="stretchpane"></a>  CMFCAutoHideBar::StretchPane  
 
      
    `CMFCAutoHideButton` 개체에 맞게 자동 숨기기 막대의 크기를 축소된 상태로 조정합니다.  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nLength`  
 값이 기본 구현에서 사용되지 않습니다. 파생된 구현에서는 이 값을 사용하여 크기 조정된 창의 길이를 나타냅니다.  
  
 [in] `bVert`  
 값이 기본 구현에서 사용되지 않습니다. 파생 된 구현에서 사용 하 여 `TRUE` 자동 숨기기 막대가 세로로 축소 되는 경우를 처리 하 고 `FALSE` 자동 숨기기 막대가 가로로 축소 되는 경우에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 크기 조정된 창의 결과 크기입니다.  
  
### <a name="remarks"></a>설명  
 파생된 클래스는 이 메서드를 재정의하여 동작을 사용자 지정할 수 있습니다.  
  
##  <a name="unsetautohidemode"></a>  CMFCAutoHideBar::UnSetAutoHideMode  
 자동 숨기기 막대의 그룹에 대해 자동 숨기기 모드를 사용하지 않도록 설정합니다.  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] pFirstBarInGroup  
 그룹의 첫 번째 자동 숨기기 막대에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="updatevisiblestate"></a>  CMFCAutoHideBar::UpdateVisibleState  
 자동 숨기기 막대를 다시 그려야 할 때 프레임워크에서 호출됩니다.  
  
```  
void UpdateVisibleState();
```  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane 클래스](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite 클래스](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md)
