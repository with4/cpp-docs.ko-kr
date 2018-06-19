---
title: CTabbedPane 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
dev_langs:
- C++
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6c42a4203fb1d0224f5f31e4123dca9a6fad65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373816"
---
# <a name="ctabbedpane-class"></a>CTabbedPane 클래스
분리 가능한 탭이 포함된 창의 기능을 구현합니다.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>구문  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CTabbedPane::CTabbedPane`|기본 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTabbedPane::DetachPane](#detachpane)|(재정의 [cbasetabbedpane:: Detachpane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|  
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|탭의 자동 색 지정을 사용하거나 사용하지 않도록 설정합니다.|  
|[CTabbedPane::FloatTab](#floattab)|창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다. (재정의 [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CTabbedPane::GetTabArea](#gettabarea)|탭 창 내 탭 영역의 크기와 위치를 반환합니다.|  
|[CTabbedPane::GetTabWnd](#gettabwnd)||  
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|탭 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다. (재정의 [cbasetabbedpane:: Hasautohidemode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|  
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|탭이 창의 맨 아래에 있는지 여부를 결정합니다.|  
|[CTabbedPane::ResetTabs](#resettabs)|모든 탭 창을 기본 상태로 다시 설정합니다.|  
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|자동 색 기능이 사용되는 경우 사용할 수 있는 사용자 지정 색 목록을 설정합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|응용 프로그램에서 탭의 기본 위치입니다.|  
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|사용자 지정 `CMFCTabCtrl` 파생 개체에 대한 런타임 클래스 정보입니다.|  
  
## <a name="remarks"></a>설명  
 사용자가 두 번째 창의 캡션을 가리켜서 한 창을 다른 창에 연결하는 경우 프레임워크에서 자동으로 이 클래스의 인스턴스를 만듭니다. 프레임워크에서 만든 모든 탭 창의 ID는 -1입니다.  
  
 Outlook 스타일 탭 대신 일반 탭을 지정 하려면 전달 된 `AFX_CBRS_REGULAR_TABS` 스타일을 [cdockablepane:: Createex](../../mfc/reference/cdockablepane-class.md#createex) 메서드.  
  
 분리 가능한 탭을 포함하는 탭 창을 만드는 경우 프레임워크에서 자동으로 창을 제거할 수 있으므로 포인터를 저장하면 안 됩니다. 탭 창에 대한 포인터를 가져오려면 `CBasePane::GetParentTabbedPane` 메서드를 호출합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `CTabbedPane` 개체를 만듭니다. 다음으로, 사용 [cbasetabbedpane:: Addtab](../../mfc/reference/cbasetabbedpane-class.md#addtab) 추가 탭을 연결 합니다.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),  
    TRUE, 
 (UINT) -1,  
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
    WS_CLIPCHILDREN | CBRS_LEFT |    
    CBRS_FLOAT_MULTI)) 
{  
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create  
}  
 
pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```  
  
## <a name="example"></a>예제  
 탭된 컨트롤 막대 개체를 만드는 또 다른 방법은 사용 하는 것 [CDockablePane::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd)합니다. `AttachToTabWnd` 메서드 설정한 런타임 클래스 정보를 사용 하 여 탭된 창 개체를 동적으로 만듭니다 [cdockablepane:: Settabbedpanertc](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)합니다.  
  
 이 예제에서는 탭 창을 동적으로 만들고 두 탭을 연결한 다음 두 번째 탭을 분리 불가능하게 만듭니다.  
  
```  
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxTabbedPane.h  
  
##  <a name="detachpane"></a>  CTabbedPane::DetachPane  

  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 [in] `bHide`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="enabletabautocolor"></a>  CTabbedPane::EnableTabAutoColor  
 탭의 자동 색 지정을 사용하거나 사용하지 않도록 설정합니다.  
  
```  
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE` 탭;의 자동 색 지정을 사용 하도록 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 정적 메서드를 사용 하 여 응용 프로그램에서 모든 탭된 창에서 탭의 자동 색 지정을 사용 합니다. 이 기능을 사용 하는 경우 각 탭은 고유한 색으로 채워집니다. 호출 하 여 탭 색에 사용 되는 색 목록을 찾을 수 있습니다는 [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) 메서드.  
  
 호출 하 여 탭에 대해 사용할 수 있는 색 목록을 지정할 수 있습니다 [CTabbedPane::SetTabAutoColors](#settabautocolors)합니다.  
  
 기본적으로이 옵션은 사용할 수 없습니다.  
  
##  <a name="floattab"></a>  CTabbedPane::FloatTab  

  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 [in] `nTabID`  
 [in] `dockMethod`  
 [in] `bHide`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettabarea"></a>  CTabbedPane::GetTabArea  
 탭된 창에 크기와 탭 영역의 위치를 반환합니다.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectTabAreaTop`  
 크기와 화면 좌표에서 최상위 탭 영역의 위치를 포함합니다.  
  
 [out] `rectTabAreaBottom`  
 크기와 화면 좌표에서 아래쪽 탭 영역의 위치를 포함합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는 사용자가 끌고 있는 창을 도킹 하는 방법을 결정 하려면이 메서드를 호출 합니다. 대상 창 탭 영역 위로 창을 끌 때 프레임 워크 대상 창에 새 테이블로 추가 하려고 시도 합니다. 그렇지 않으면 두 창을 구분 하는 창 구분선으로 새 창 컨테이너를 만드는 작업이 포함 된 대상 창 옆쪽에 창을 도킹할 하려고 합니다.  
  
 이 메서드를 재정의 한 `CTabbedPane`-이 동작을 변경 하는 클래스를 파생 합니다.  
  
##  <a name="gettabwnd"></a>  CTabbedPane::GetTabWnd  

  
```  
CMFCTabCtrl* GetTabWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="hasautohidemode"></a>  CTabbedPane::HasAutoHideMode  

  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="istablocationbottom"></a>  CTabbedPane::IsTabLocationBottom  
 탭이 창의 맨 아래에 있는지 여부를 결정합니다.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 탭 영역의 탭 창의 맨 아래에 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_btabsalwaystop"></a>  CTabbedPane::m_bTabsAlwaysTop  
 응용 프로그램에서 탭의 기본 위치입니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;  
```  
  
### <a name="remarks"></a>설명  
 이 정적 멤버를 설정 `TRUE` 강제로 탭된 창 위쪽에 표시할 응용 프로그램에 있는 모든 탭 합니다.  
  
 탭된 창 생성 되기 전에이 값을 설정 해야 합니다.  
  
 기본값은 `FALSE`입니다.  
  
##  <a name="m_ptabwndrtc"></a>  CTabbedPane::m_pTabWndRTC  
 사용자 지정 `CMFCTabCtrl` 파생 개체에 대한 런타임 클래스 정보입니다.  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;  
```  
  
### <a name="remarks"></a>설명  
 이 정적 멤버 변수의 런타임 클래스 정보에 대 한 포인터를 설정 하는 `CMFCTabCtrl`-파생 된 개체는 탭된 창 내 탭된 창 사용자 지정을 사용 하는 경우.  
  
##  <a name="resettabs"></a>  CTabbedPane::ResetTabs  
 모든 탭 창을 기본 상태로 다시 설정합니다.  
  
```  
static void ResetTabs();
```  
  
### <a name="remarks"></a>설명  
 모든 탭된 창을 기본 상태로 되돌리려면이 메서드를 호출 합니다. 호출 되 면이 메서드 테두리 크기와의 모든 탭된 창이 자동 색 상태 다시 설정 합니다.  
  
##  <a name="settabautocolors"></a>  CTabbedPane::SetTabAutoColors  
 자동 색 기능이 사용 하도록 설정한 경우 사용 되는 사용자 지정 색 목록을 설정 합니다.  
  
```  
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `arColors`  
 설정 하는 색 배열에 포함 되어 있습니다.  
  
### <a name="remarks"></a>설명  
 자동 색 기능이 사용 하도록 설정한 경우 사용 되는 색 목록을 사용자 지정 하려면이 메서드를 사용 합니다. 정적 함수 이므로 응용 프로그램에서 모든 탭된 창에 영향을 줍니다.  
  
 사용 하 여 [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) 자동 색 기능이 사용 하지 않도록 설정 하거나 설정 하려면.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)   
 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)
