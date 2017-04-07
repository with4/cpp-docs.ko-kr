---
title: "COleIPFrameWndEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AdjustDockingLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPaneLeftOf
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableAutoHidePanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableDocking
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnablePaneMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetActivePopup
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetContainerFrameWindow
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDefaultResId
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockingManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMainFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMenuBar
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetTearOffBars
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetToolbarButtonToolTipText
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InsertPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsMenuBarAvailable
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsPointNearDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::LoadFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseDockingPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnClosePopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCmdMsg
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuImage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuLogo
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMenuButtonToolHitTest
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMoveMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnSetPreviewMode
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowCustomizePane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnTearOffMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PaneFromPoint
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PreTranslateMessage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RecalcLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RemovePaneFromDockManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetDockState
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetupToolbarMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::ShowPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::WinHelpA
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InitUserToobars
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWndEx class
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
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
ms.openlocfilehash: 5eec8e3a9cc4ad71a1ee3de9f6d5f25cffef1242
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx 클래스
`COleIPFrameWndEx` 클래스는 MFC를 지원하는 OLE 컨테이너를 구현합니다. 응용 프로그램에 대 한 내부 프레임 창 클래스를 파생 해야는 `COleIPFrameWndEx` 클래스에서 파생 하는 대신는 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleIPFrameWndEx::AddDockSite](#adddocksite)||  
|[COleIPFrameWndEx::AddPane](#addpane)||  
|[COleIPFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)||  
|[COleIPFrameWndEx::DockPane](#dockpane)||  
|[COleIPFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)||  
|[COleIPFrameWndEx::EnableDocking](#enabledocking)||  
|[COleIPFrameWndEx::EnablePaneMenu](#enablepanemenu)||  
|[COleIPFrameWndEx::GetActivePopup](#getactivepopup)|현재 표시된 팝업 메뉴에 대한 포인터를 반환합니다.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](#getcontainerframewindow)||  
|[COleIPFrameWndEx::GetDefaultResId](#getdefaultresid)|창이 로드될 때 지정한 프레임 창의 리소스 ID를 반환합니다.|  
|[COleIPFrameWndEx::GetDockFrame](#getdockframe)||  
|[COleIPFrameWndEx::GetDockingManager](#getdockingmanager)||  
|[COleIPFrameWndEx::GetMainFrame](#getmainframe)||  
|[COleIPFrameWndEx::GetMenuBar](#getmenubar)|프레임 창에 연결된 메뉴 모음 개체에 대한 포인터를 반환합니다.|  
|[COleIPFrameWndEx::GetPane](#getpane)||  
|[COleIPFrameWndEx::GetTearOffBars](#gettearoffbars)|분리 상태에 있는 창 개체의 목록을 반환합니다.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|단추에 대한 도구 설명이 표시되기 전에 프레임워크에서 호출합니다.|  
|[COleIPFrameWndEx::InsertPane](#insertpane)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|메뉴 모음 개체에 대한 포인터가 `NULL`이 아닌지 여부를 확인합니다.|  
|[COleIPFrameWndEx::IsPointNearDockSite](#ispointneardocksite)||  
|[COleIPFrameWndEx::LoadFrame](#loadframe)|( `COleIPFrameWnd::LoadFrame`을 재정의합니다.)|  
|[COleIPFrameWndEx::OnCloseDockingPane](#onclosedockingpane)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)||  
|[COleIPFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnCmdMsg](#oncmdmsg)|( `CFrameWnd::OnCmdMsg`을 재정의합니다.)|  
|[COleIPFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|메뉴 항목과 연결된 이미지를 그릴 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|프레임 워크에서 호출 하면는 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)WM_PAINT 메시지를 처리 하는 개체입니다.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|프레임 워크에서 호출 하면는 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)WM_NCHITTEST 메시지를 처리 하는 개체입니다.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)||  
|[COleIPFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|응용 프로그램의 주 프레임 창을 인쇄 미리 보기 모드 내부 및 외부로 설정하려면 이 멤버 함수를 호출합니다. (재정의 [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode).)|  
|[COleIPFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)||  
|[COleIPFrameWndEx::OnShowPanes](#onshowpanes)||  
|[COleIPFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|팝업 메뉴가 활성화될 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnTearOffMenu](#ontearoffmenu)|분리 막대가 있는 메뉴가 활성화될 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::PaneFromPoint](#panefrompoint)||  
|[COleIPFrameWndEx::PreTranslateMessage](#pretranslatemessage)|( `COleIPFrameWnd::PreTranslateMessage`을 재정의합니다.)|  
|[COleIPFrameWndEx::RecalcLayout](#recalclayout)|( `COleIPFrameWnd::RecalcLayout`을 재정의합니다.)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)||  
|[COleIPFrameWndEx::SetDockState](#setdockstate)|프레임 창에 속해 있는 창에 지정된 도킹 상태를 적용합니다.|  
|[COleIPFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|더미 항목을 검색하고 지정된 사용자 정의 항목으로 대체하여 도구 모음 개체를 수정합니다.|  
|[COleIPFrameWndEx::ShowPane](#showpane)||  
|[COleIPFrameWndEx::WinHelpA](#winhelpa)|WinHelp 응용 프로그램 또는 상황에 맞는 도움말을 시작하기 위해 프레임워크에서 호출됩니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleIPFrameWndEx::InitUserToobars](#initusertoobars)|사용자 정의 도구 모음에 할당되는 컨트롤 ID의 범위를 초기화하도록 프레임워크에 지시합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `COleIPFrameWndEx` 클래스의 인스턴스를 하위 클래스로 지정하고 해당 메서드를 재정의하는 방법을 보여 줍니다. 이 예제에서는 `OnDestory` 메서드, `RepositionFrame` 메서드, `RecalcLayout` 메서드 및 `CalcWindowRect` 메서드를 재정의하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [워드 패드 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_WordPad #&1;](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxoleipframewndex.h  
  
##  <a name="adddocksite"></a>COleIPFrameWndEx::AddDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddDockSite();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="addpane"></a>COleIPFrameWndEx::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 [in] `bTail`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="adjustdockinglayout"></a>COleIPFrameWndEx::AdjustDockingLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hdwp`  
  
### <a name="remarks"></a>주의  
  
##  <a name="dockpane"></a>COleIPFrameWndEx::DockPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 [in] `nDockBarID`  
 [in] `lpRect`  
  
### <a name="remarks"></a>주의  
  
##  <a name="dockpaneleftof"></a>COleIPFrameWndEx::DockPaneLeftOf  
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
 포인터 원점으로 사용 되는 창입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 작업이 성공한 경우. 그렇지 않으면 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 미리 정의 된 순서에 여러 가지 창에서 개체를 고정 하려면이 메서드를 호출 합니다. 이 메서드는 지정 된 창 도킹 `pBar` 로 지정 된 창 왼쪽에 `pLeftOf`합니다.  
  
##  <a name="enableautohidepanes"></a>COleIPFrameWndEx::EnableAutoHidePanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="enabledocking"></a>COleIPFrameWndEx::EnableDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="enablepanemenu"></a>COleIPFrameWndEx::EnablePaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly = FALSE,  
    BOOL bViewMenuShowsToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 [in] `uiCustomizeCmd`  
 [in] `strCustomizeLabel`  
 [in] `uiViewToolbarsMenuEntryID`  
 [in] `bContextMenuShowsToolbarsOnly`  
 [in] `bViewMenuShowsToolbarsOnly`  
  
### <a name="remarks"></a>주의  
  
##  <a name="getactivepopup"></a>COleIPFrameWndEx::GetActivePopup  
 현재 표시 된 팝업 메뉴에 대 한 포인터를 반환합니다.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 활성화 된 팝업 메뉴;에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여에 대 한 포인터를 얻을 수는 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 현재 표시 되는 개체입니다.  
  
##  <a name="getcontainerframewindow"></a>COleIPFrameWndEx::GetContainerFrameWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getdefaultresid"></a>COleIPFrameWndEx::GetDefaultResId  
 프레임 창 메뉴를 로드할 때 있었던 메뉴 리소스 ID 지정 반환 합니다.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프레임 창에 메뉴 모음이 있으면 메뉴를 사용 하거나 0의 리소스 ID를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 호출 된 리소스 ID를 검색 하려면이 함수를 프레임 창을 호출 하 여 메뉴 리소스를 로드 하는 경우 지정 된 `COleIPFrameWndEx::LoadFrame`합니다.  
  
##  <a name="getdockframe"></a>COleIPFrameWndEx::GetDockFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetDockFrame();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getdockingmanager"></a>COleIPFrameWndEx::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getmainframe"></a>COleIPFrameWndEx::GetMainFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetMainFrame();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getmenubar"></a>COleIPFrameWndEx::GetMenuBar  
 프레임 창에 연결된 메뉴 모음 개체에 대한 포인터를 반환합니다.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 모음 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여에 속하는 메뉴 모음 개체에 대 한 포인터를 검색 하는 `COleIPFrameWndEx` 개체입니다.  
  
##  <a name="getpane"></a>COleIPFrameWndEx::GetPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="gettearoffbars"></a>COleIPFrameWndEx::GetTearOffBars  
 분리 상태에 있는 창 개체의 목록을 반환합니다.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 `CObList` 개체에 대 한 포인터 컬렉션을 포함 하는 [CBasePane 클래스](../../mfc/reference/cbasepane-class.md)-파생 개체입니다.  
  
### <a name="remarks"></a>주의  
 `COleIPFrameWndEx` 목록으로 분리 메뉴의 컬렉션을 유지 하는 개체 [CBasePane 클래스](../../mfc/reference/cbasepane-class.md)-파생 개체입니다. 이 메서드를 사용 하 여이 목록에 대 한 참조를 검색 합니다.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>COleIPFrameWndEx::GetToolbarButtonToolTipText  
 단추에 대한 도구 설명이 표시되기 전에 프레임워크에서 호출합니다.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 단추에 대 한 포인터입니다.  
  
 [in] `strTTText`  
 도구 설명 텍스트에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현에서는 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추에 대 한 도구 설명의 표시를 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="initusertoobars"></a>COleIPFrameWndEx::InitUserToobars  
 다양 한 제어 프레임 워크는 사용자 지정 도구 모음에 할당 하는 Id 지정 합니다.  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszRegEntry`  
 라이브러리 도구 모음 설정을 사용자를 저장 하는 위치는 레지스트리 항목입니다.  
  
 [in] `uiUserToolbarFirst`  
 컨트롤 ID를 첫 번째 사용자 지정 도구 모음에 할당 합니다.  
  
 [in] `uiUserToolbarLast`  
 마지막 사용자 지정 도구 모음에 할당 되는 컨트롤 ID입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 사용자가 동적으로 정의 하는 도구 모음에 할당 하기 위해 컨트롤 Id의 범위를 초기화 합니다. 매개 변수 `uiUserToolbarFirst` 및 `uiUserToolbarLast` 허용 되는 도구 모음 컨트롤 Id의 범위를 정의 합니다. 도구 모음 사용자 지정 만들기를 사용 하지 않으려면 설정 `uiUserToolbarFirst` 또는 `uiUserToolbarLast` 를-1입니다.  
  
##  <a name="insertpane"></a>COleIPFrameWndEx::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pControlBar`  
 [in] `pTarget`  
 [in] `bAfter`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="ismenubaravailable"></a>COleIPFrameWndEx::IsMenuBarAvailable  
 메뉴 모음 개체에 대 한 포인터 인지를 결정 합니다.`NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프레임 창에는 메뉴 모음; 있으면 0이 아닌 반환 값 그렇지 않으면 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 창 유지 관리 하는지 여부는 비-확인 하려면이 메서드를 호출 `NULL` 해당 메뉴 모음 개체에 대 한 포인터입니다.  
  
##  <a name="ispointneardocksite"></a>COleIPFrameWndEx::IsPointNearDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 [in] `dwBarAlignment`  
 [in] `bOuterEdge`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="loadframe"></a>COleIPFrameWndEx::LoadFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIDResource`  
 [in] `dwDefaultStyle`  
 [in] `pParentWnd`  
 [in] `pContext`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onclosedockingpane"></a>COleIPFrameWndEx::OnCloseDockingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane*);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CDockablePane*`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="oncloseminiframe"></a>COleIPFrameWndEx::OnCloseMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CPaneFrameWnd*`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onclosepopupmenu"></a>COleIPFrameWndEx::OnClosePopupMenu  
 활성 팝업 메뉴를 처리할 때 프레임 워크에 의해 호출 된 `WM_DESTROY` 메시지입니다.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPopup`  
 팝업 메뉴 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 알림을 수신 하려면이 메서드를 재정의 `CMFCPopupMenu` 개체를 처리할 때 `WM_DESTROY` 메시지입니다.  
  
##  <a name="oncmdmsg"></a>COleIPFrameWndEx::OnCmdMsg  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 [in] `nCode`  
 [in] `pExtra`  
 [in] `pHandlerInfo`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="ondrawmenuimage"></a>COleIPFrameWndEx::OnDrawMenuImage  
 메뉴 항목과 연결 된 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `pMenuButton`  
 메뉴 단추에 대 한 포인터입니다.  
  
 [in] `rectImage`  
 메뉴 항목과 연결 된 이미지입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 아무 작업도 수행 하 고 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 재정의 하 여 이미지에서 소유 하 고 메뉴 모음에 속하는 메뉴 항목에 대 한 그리기를 사용자 지정 하려는 경우는 `COleIPFrameWndEx`-파생 개체입니다.  
  
##  <a name="ondrawmenulogo"></a>COleIPFrameWndEx::OnDrawMenuLogo  
 프레임 워크 호출 때는 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)프로세스 개체를 `WM_PAINT` 메시지입니다.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `pMenu`  
 팝업 메뉴 개체에 대 한 포인터입니다.  
  
 [in] `rectLogo`  
 표시할 로고에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 메뉴 모음에서 소유와 관련 된 팝업 메뉴에 로고를 표시 하려면이 메서드를 재정의 `COleIPFrameWndEx`-파생 개체입니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="onmenubuttontoolhittest"></a>COleIPFrameWndEx::OnMenuButtonToolHitTest  
 프레임 워크 호출 때는 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)프로세스 개체를 `WM_NCHITTEST` 메시지입니다.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] pButton  
 메뉴 단추에 대 한 포인터입니다.  
  
 [out] pTI  
 `TOOLINFO` 구조체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 아무 작업도 수행 하 고 0을 반환 합니다. 구현 채워지면&0;이 아닌 값을 반환 해야는 `pTI` 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 특정 메뉴 항목에 대 한 도구 설명 정보를 제공 하려면이 메서드를 재정의 합니다.  
  
##  <a name="onmoveminiframe"></a>COleIPFrameWndEx::OnMoveMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrame`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsetpreviewmode"></a>COleIPFrameWndEx::OnSetPreviewMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bPreview`  
 [in] `pState`  
  
### <a name="remarks"></a>주의  
  
##  <a name="onshowcustomizepane"></a>COleIPFrameWndEx::OnShowCustomizePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPane`  
 [in] `uiToolbarID`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onshowpanes"></a>COleIPFrameWndEx::OnShowPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onshowpopupmenu"></a>COleIPFrameWndEx::OnShowPopupMenu  
 팝업 메뉴가 표시 될 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>매개 변수  
 `[in] pMenuPopup`  
 표시할 팝업 메뉴에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 아무 작업도 수행 하 고&0;이 아닌 값을 반환 합니다. 구현을 반환 해야 `FALSE` 팝업 메뉴를 표시할 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 팝업 메뉴의 표시를 사용자 지정 하려면이 메서드를 재정의 합니다. 예를 들어 색 메뉴 단추를 메뉴 단추를 변경 하거나 분리 막대를 초기화할 수 있습니다.  
  
##  <a name="ontearoffmenu"></a>COleIPFrameWndEx::OnTearOffMenu  
 사용자가 표시줄이 있는 분리 메뉴를 선택 하는 경우는 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuPopup`  
 사용자가 선택한 팝업 메뉴에 대 한 포인터입니다.  
  
 [in] `pBar`  
 메뉴를 호스팅하는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 워크에는 팝업 메뉴를 활성화 하려는 경우 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 분리 모음을 설치 하는 사용자 지정 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="panefrompoint"></a>COleIPFrameWndEx::PaneFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [in] `nSensitivity`  
 [in] `bExactBar`  
 [in] `pRTCBarType`  
 [in] `dwAlignment`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="pretranslatemessage"></a>COleIPFrameWndEx::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMsg`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="recalclayout"></a>COleIPFrameWndEx::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bNotify`  
  
### <a name="remarks"></a>주의  
  
##  <a name="removepanefromdockmanager"></a>COleIPFrameWndEx::RemovePaneFromDockManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [in] `bDestroy`  
 [in] `bAdjustLayout`  
 [in] `bAutoHide`  
 [in] `pBarReplacement`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setdockstate"></a>COleIPFrameWndEx::SetDockState  
 프레임 창에 속한 창에 지정된 된 도킹 상태를 적용 합니다.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `state`  
 도킹 상태를 지정합니다.  
  
### <a name="remarks"></a>주의  
 에 속한 창에 대 한 새 도킹 상태를 지정 하려면이 함수를 사용 하 여 `COleIPFrameWndEx` 개체입니다.  
  
##  <a name="setuptoolbarmenu"></a>COleIPFrameWndEx::SetupToolbarMenu  
 더미 항목을 검색하고 지정된 사용자 정의 항목으로 대체하여 도구 모음 개체를 수정합니다.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `menu`  
 에 대 한 참조는 [CMenu](../../mfc/reference/cmenu-class.md) 개체를 수정할 수 있습니다.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 첫 번째 사용자 지정 명령을 지정합니다.  
  
 [in] `uiViewUserToolbarCmdLast`  
 마지막 사용자 지정 명령을 지정합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="showpane"></a>COleIPFrameWndEx::ShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>주의  
  
##  <a name="winhelpa"></a>COleIPFrameWndEx::WinHelpA  
 WinHelp 응용 프로그램 또는 상황에 맞는 도움말을 시작하기 위해 프레임워크에서 호출됩니다.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] dwData  
 `nCmd`에 지정된 도움말의 형식에 필요한 대로 데이터를 지정합니다.  
  
 [in] `nCmd`  
 요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 `dwData` 매개 변수에 영향을 주는 방식에 대해서는 Windows SDK의 [WinHelp 함수](http://msdn.microsoft.com/library/windows/desktop/bb762267) (영문)를 참조하세요.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)

