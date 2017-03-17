---
title: "CMFCOutlookBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBar class
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
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
ms.openlocfilehash: ff58cf786e4979d64aa2b5d7ad4d1a32b96bec3d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar 클래스
Microsoft Outlook 2000 또는 Outlook 2003의 **탐색 창** 과 시각적으로 유사한 탭 창입니다. `CMFCOutlookBar` 개체를 포함 한 [CMFCOutlookBarTabCtrl 클래스](../../mfc/reference/cmfcoutlookbartabctrl-class.md) 개체와 일련의 탭 합니다. 탭 수 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체 또는 `CWnd`-파생 개체입니다. Outlook 표시줄은 사용자에게 일련의 단추와 표시 영역으로 나타납니다. 사용자가 단추를 클릭하면 해당 컨트롤 또는 단추 창이 표시됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|기본 생성자입니다.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|가 빈 탭된 창을 소멸 될 수 있는지 여부를 지정 합니다. (재정의 [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|다른 창을 Outlook 표시줄 창에 도킹할 수 수 있는지 여부를 결정 합니다. (CDockablePane::CanAcceptPane 무시 합니다.)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|탭된 창에 대 한 캡션을 활성 탭으로 동일한 텍스트를 표시 하는지 여부를 결정 합니다. (재정의 [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Outlook 표시줄 컨트롤을 만듭니다.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|사용자 지정 Outlook 표시줄 탭을 만듭니다.|  
|`CMFCOutlookBar::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|사용자가 Outlook 표시줄의 외부 가장자리에 있는 컨트롤 막대를 고정할 수 있는지 여부를 결정 합니다.|  
|[CMFCOutlookBar::FloatTab](#floattab)|창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다. (재정의 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Outlook 표시줄의 단추에는 텍스트의 글꼴을 반환합니다.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Outlook 표시줄에서 크기와 탭 영역의 위치를 반환합니다. (재정의 [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Outlook 표시줄의 동작을 모방 (설명 참조) Microsoft Office Outlook 2003의 여부를 결정 합니다.|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|에 의해 호출 [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 애니메이션을 사용 하 여 활성 탭을 설정 합니다.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|에 의해 호출 [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 탭 하기 전에 페이지 애니메이션을 사용 하 여 활성 탭으로 설정 됩니다.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|위로 또는 아래로 Outlook 표시줄 스크롤 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|사용자 지정 Outlook 표시줄 탭을 제거합니다.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Outlook 표시줄의 단추에는 텍스트의 글꼴을 설정합니다.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Outlook 표시줄의 동작을 모방 Outlook 2003 (설명 참조)의 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 Outlook 표시줄의 예를 들어 참조는 [OutlookDemo 샘플: MFC OutlookDemo 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
## <a name="implementing-the-outlook-bar"></a>Outlook 표시줄 구현  
 응용 프로그램에서 `CMFCOutlookBar` 컨트롤을 사용하려면 다음 단계를 수행합니다.  
  
1.  `CMFCOutlookBar` 개체를 주 프레임 창 클래스에 포함합니다.  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  처리 하는 경우는 `WM_CREATE` 주 프레임을 호출 하는 메시지는 [CMFCOutlookBar::Create](#create) Outlook 표시줄 탭 컨트롤을 만드는 메서드를 합니다.  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  기본에 대 한 포인터를 가져올 `CMFCOutlookBarTabCtrl` 를 사용 하 여 [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)합니다.  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  만들기는 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md) 단추가 포함 된 각 탭에 대 한 개체입니다.  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  호출 [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 각 새 탭을 추가 합니다. 설정의 `bDetachable` 매개 변수를 `FALSE` 분리 가능한 아닌 페이지를 만듭니다. 또는 사용 하 여 [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) 분리 가능한 페이지를 추가 합니다.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  추가 하는 `CWnd`-파생 컨트롤 (예를 들어 [CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md))는 탭 컨트롤 및 호출을 만들기 [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Outlook 표시줄에 추가 합니다.  
  
> [!NOTE]
>  각 고유 컨트롤 Id를 사용 해야 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체 및 각 `CWnd`-파생 개체입니다.  
  
 동적으로 추가 하거나 삭제할 런타임에 새 페이지를 사용 하 여 [CMFCOutlookBar::CreateCustomPage](#createcustompage) 및 [CMFCOutlookBar::RemoveCustomPage](#removecustompage)합니다.  
  
## <a name="outlook-2003-mode"></a>Outlook 2003 모드  
 Outlook 2003 모드에서 탭 단추 Outlook 표시줄 창 맨 아래에 배치 됩니다. 단추를 표시할 수 있는 충분 한 공간이 없을 때의 창 하단 도구 모음 같은 영역에 아이콘으로 표시 됩니다.  
  
 사용 하 여 [CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003 모드를 사용 하도록 합니다. 사용 하 여 [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) Outlook 표시줄의 아래쪽에 표시 되는 아이콘이 포함 된 비트맵을 설정할 수 있습니다. 비트맵에 있는 아이콘을 탭 인덱스 별로 정렬 되어야 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxoutlookbar.h  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 가 빈 탭된 창을 소멸 될 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 비어 있는 경우 창 소멸 될 수 있습니다. 그렇지 않으면 `FALSE`합니다. 기본 구현에서는 항상 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>주의  
 가 빈 탭된 창을 소멸 될 수 없으므로, 하는 경우 프레임 워크를 숨기고 대신 합니다.  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 다른 창을 Outlook 표시줄 창에 도킹할 수 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 이 창에 도킹 되 고 다른 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다른 창에 Outlook 표시줄 창에 도킹할 수 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 Outlook 표시줄 Outlook 2003 모드에 있으면 도킹은 지원 되지 않으므로 반환 값은 `FALSE`합니다.  
  
 하는 경우는 `pBar` 매개 변수는 `NULL`,이 메서드는 반환 `FALSE`합니다.  
  
 그렇지 않으면이 메서드는 기본 방법으로 동작 [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)점을 제외 하 고 Outlook 표시줄 다른 Outlook 표시줄 위로 도킹할 수를 계속 사용할 수 있습니다 도킹을 사용 하지 않는 경우에 합니다.  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 탭된 창에 대 한 캡션을 활성 탭으로 동일한 텍스트를 표시 하는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`Outlook 표시줄 창 캡션의 활성 탭;의 텍스트를 자동으로 설정 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) 사용 하도록 설정 하거나이 기능을 사용 하지 않도록 설정 합니다.  
  
 Outlook 2003 모드에서이 설정은 항상 설정 됩니다.  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Outlook 표시줄 컨트롤을 만듭니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszCaption`  
 창 캡션을 지정합니다.  
  
 [in] `pParentWnd`  
 부모 창에 대 한 포인터를 지정합니다. NULL이 아니어야 합니다.  
  
 [in] `rect`  
 Outlook 표시줄 크기와 위치 (픽셀) 지정합니다.  
  
 [in] `nID`  
 컨트롤 ID를 지정 합니다. 다른 컨트롤을 응용 프로그램에서 사용 되는 Id 구별 되어야 합니다.  
  
 [in] `dwStyle`  
 원하는 컨트롤 막대 스타일을 지정합니다. 가능한 값에 대 한 참조 [창 스타일](../../mfc/reference/window-styles.md)합니다.  
  
 [in] `dwControlBarStyle`  
 특별 한 라이브러리 정의 된 스타일을 지정합니다.  
  
 [in] `pContext`  
 컨텍스트를 만듭니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CMFCOutlookBar` 두 단계에서는 개체입니다. 먼저 생성자를 호출 하 고 다음 `Create`, outlook bar 컨트롤을 만들고에 연결 하는 `CMFCOutlookBar` 개체입니다.  
  
 참조 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) 을 지정할 수는 사용 가능한 라이브러리 정의 된 스타일의 목록은 `dwControlBarStyle`합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Create` 의 메서드는 `CMFCOutlookBar` 클래스입니다. 이 코드 조각은의 일부인는 [Outlook 다중 보기 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews #&1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews #&2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
 사용자 지정 Outlook 표시줄 탭을 만듭니다.  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszPageName`  
 페이지 레이블입니다.  
  
 [in] `bActivatePage`  
 경우 `TRUE`, 페이지를 만들 때 활성화 됩니다.  
  
 [in] `dwEnabledDocking`  
 페이지 분리 되 면 활성화 된 도킹 측면을 지정 하는 CBRS_ALIGN_ 플래그의 조합입니다.  
  
 [in] `bEnableTextLabels`  
 경우 `TRUE`, 페이지에 있는 단추에 대 한 텍스트 레이블을 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 페이지에 대 한 포인터 또는 `NULL` 생성에 실패 하는 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 사용자 지정 Outlook 표시줄 페이지를 사용자가 사용할 수 있도록 합니다. 응용 프로그램 당 최대 100 개의 페이지를 만들 수 있습니다. 페이지 컨트롤 Id 0xf000 시작합니다. 사용자 지정 Outlook 표시줄 페이지의 총 100을 초과 하는 경우 만들기가 실패 합니다.  
  
 사용 하 여 [CMFCOutlookBar::RemoveCustomPage](#removecustompage) 사용자 지정 페이지를 삭제 합니다.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 사용자가 Outlook 표시줄의 외부 가장자리에 창 도킹할 수 있는지 여부를 지정 합니다.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 호출의 `DoesAllowDynInsertBefore` 메서드를 동적 창 도킹 위치를 찾습니다. 함수가 반환 하는 경우 `FALSE`, 프레임 워크 창 외부 가장자리에 모든 동적 창의 도킹을 허용 하지 않습니다.  
  
 일반적으로 정적 비 부동 컨트롤로 Outlook 표시줄을 만듭니다. 파생된 클래스에서이 함수를 재정의 하 고 반환 `TRUE` 이 동작을 변경할 수 있습니다.  
  
> [!NOTE]
>  동적 창 상태 정적 도킹 된 창 도킹 하는 경우를 확인 하기 때문에 가능 하면 항상 정적 창 후 동적 창을 도킹할 해야 있습니다.  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 창을 배치 됩니다.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 Float로의 창에 대 한 포인터입니다.  
  
 [in] `nTabID`  
 Float로 탭의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `dockMethod`  
 창을 분리 하는 데 사용할 방법을 지정 합니다.  자세한 내용은 참조 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)합니다.  
  
 [in] `bHide`  
 `TRUE`창을 부동; 전에 숨기려면 그렇지 않으면 `FALSE`합니다. 이 메서드의 기본 클래스 버전 달리이 매개 변수 없는 기본 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 확장 되 면; 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 방법은 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) 제외 하 고 float로 Outlook 표시줄 컨트롤에 대해 마지막으로 남은 탭을 사용 하지 않습니다.  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 Outlook 표시줄의 단추 탭 페이지에는 텍스트의 글꼴을 반환합니다.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>반환 값  
 페이지 단추 탭 표시줄 Outlook에 텍스트를 표시 하는 데 사용 되는 글꼴 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 Outlook 페이지 단추 탭에 텍스트를 표시 하는 데 사용 되는 글꼴을 검색 하려면이 함수를 사용 합니다. 호출 하 여 글꼴을 설정할 수 있습니다 [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)합니다.  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 Outlook 표시줄에 있는 탭 영역의 위치와 크기를 결정합니다.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectTabAreaTop`  
 함수가 반환 될 때 탭 위쪽 영역 (클라이언트 좌표로) 위치와 크기를 포함 합니다.  
  
 [out] `rectTabAreaBottom`  
 함수가 반환 될 때 탭 아래쪽 영역 (클라이언트 좌표로) 위치와 크기를 포함 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 대상 창에 도킹 유형을 확인 하려면이 메서드를 호출 합니다. 프레임 워크를 대상 창 탭 영역 위로 도킹 창 끌으로 파악 하는 경우 대상 창의 새 탭으로 첫 번째 창에 추가 하려고 합니다. 그렇지 않은 경우에 적절 한 쪽의 대상 창에서 첫 번째 창 도킹 가져오려고 시도 합니다. 프레임 워크 추가 도킹 된 창에 맞게 슬라이더로 새 컨테이너를 만듭니다.  
  
 기본 구현은 `GetTabArea` Outlook 표시줄에 있는 정적; 이면 Outlook 표시줄의 전체 클라이언트 영역을 반환 합니다. Outlook 표시줄 부동 소수점 수 없는 경우. 그렇지 않으면 페이지 단추에서 위쪽 및 아래쪽 Outlook bar 컨트롤을 사용 하는 영역을 반환 합니다.  
  
 파생 된 클래스에서이 메서드를 재정의 `CMFCOutlookBar` 이 동작을 변경할 수 있습니다.  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Outlook 표시줄의 동작을 모방 Microsoft Office Outlook 2003의 여부를 지정 합니다.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Outlook 표시줄은 Microsoft Office 2003 모드에서 실행 중인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여이 모드를 사용할 수 있습니다 [CMFCOutlookBar::SetMode2003](#setmode2003)합니다.  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 에 의해 호출 [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 애니메이션을 사용 하 여 활성 탭을 설정 합니다.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nPage`  
 활성 설정한 탭 페이지의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 활성 탭 설정의 시각 효과 애니메이션 설정 여부에 따라 달라 집니다. 자세한 내용은 참조 [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)합니다.  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 에 의해 호출 [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 탭 하기 전에 페이지 애니메이션을 사용 하 여 활성 탭으로 설정 됩니다.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nPage`  
 활성 설정 하는 탭 페이지의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 새 활성 탭 설정에 애니메이션을 사용 하는 경우 또는 `FALSE` 애니메이션 사용 하지 않도록 설정 해야 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 위로 또는 아래로 Outlook 표시줄 스크롤 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDown`  
 `TRUE`Outlook 표시줄 아래로 스크롤 하는 경우 또는 `FALSE` 위로 스크롤 하는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 사용자 지정 Outlook 표시줄 탭 페이지를 제거합니다.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiPage`  
 부모 Outlook 창에 있는 페이지의&0;부터 시작 인덱스입니다.  
  
 [in] `pTargetWnd`  
 Pointerto 부모 Outlook 창입니다.  
  
### <a name="return-value"></a>반환 값  
 사용자 지정 페이지 성공적으로 제거 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 페이지를 삭제 하려면이 함수를 호출 합니다. 페이지가 제거 될 때 해당 컨트롤 ID는 사용 가능한 Id의 풀에 반환 됩니다.  
  
 에 대 한 포인터를 제공 해야 [CMFCOutlookBarTabCtrl 클래스](../../mfc/reference/cmfcoutlookbartabctrl-class.md) 페이지를 현재 제거할 수 있는 개체입니다. 다른 Outlook 막대 사이의 사용자 분리 가능한 페이지를 이동할 수 있지만 사용자 지정 페이지에 대 한 정보를 호출한 Outlook 표시줄 개체에 있는 [CMFCOutlookBar::CreateCustomPage](#createcustompage)합니다.  
  
 사용 하 여 [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) Outlook 창에 대 한 포인터를 얻을 수 있습니다.  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Outlook 표시줄의 단추에는 텍스트의 글꼴을 설정합니다.  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFont`  
 새 글꼴을 지정합니다.  
  
 [in] `bRedraw`  
 경우 `TRUE`, Outlook 표시줄 다시 그려집니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 outlook 탭 페이지 단추에 표시 되는 텍스트 글꼴을 설정 합니다.  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Outlook 표시줄의 동작을 모방 Outlook 2003의 여부를 지정 합니다.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bMode2003`  
 True 인 경우, Office 2003 모드가 사용 됩니다.  
  
### <a name="remarks"></a>주의  
 Office 2003 모드를 사용할지 여부를이 함수를 사용 합니다. 이 모드에서는 Outlook 표시줄에는 사용자 지정 단추는 추가 도구 모음을 있습니다. Outlook 표시줄의 동작은 Microsoft Office 2003에서 Outlook 표시줄의 동작을 따릅니다.  
  
 기본적으로이 모드는 사용할 수 없습니다.  
  
> [!NOTE]
>  이 함수를 호출 하기 전에 해야 [CMFCOutlookBar::Create](#create)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl 클래스](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md)

