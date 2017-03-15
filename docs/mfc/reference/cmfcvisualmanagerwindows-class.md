---
title: "CMFCVisualManagerWindows 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCVisualManagerWindows
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerWindows class
ms.assetid: 568b6e9e-8e67-4477-9a3d-2981cbd09861
caps.latest.revision: 46
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
ms.openlocfilehash: 7b5b6a81af56dfabf733fbd5c6b018f5355164c8
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcvisualmanagerwindows-class"></a>CMFCVisualManagerWindows 클래스
`CMFCVisualManagerWindows`Windows XP 또는 Vista 테마를 선택할 때 Microsoft Windows XP 또는 Microsoft Vista의 형태를 그대로 모방 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCVisualManagerWindows : public CMFCVisualManagerOfficeXP  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCVisualManagerWindows::CMFCVisualManagerWindows`|기본 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCVisualManagerWindows::AlwaysHighlight3DTabs](#alwayshighlight3dtabs)|프레임 워크는 응용 프로그램에서 항상 3D 탭을 강조 함 있는지 여부를 확인 하려면이 메서드를 호출 합니다. (재정의 [CMFCVisualManager::AlwaysHighlight3DTabs](../../mfc/reference/cmfcvisualmanager-class.md#alwayshighlight3dtabs).)|  
|[CMFCVisualManagerWindows::DrawComboBorderWinXP](#drawcomboborderwinxp)|(`CMFCVisualManager::DrawComboBorderWinXP`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::DrawComboDropButtonWinXP](#drawcombodropbuttonwinxp)|(재정의 [CMFCVisualManager::DrawComboDropButtonWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawcombodropbuttonwinxp).)|  
|[CMFCVisualManagerWindows::DrawPushButtonWinXP](#drawpushbuttonwinxp)|(재정의 [CMFCVisualManager::DrawPushButtonWinXP](../../mfc/reference/cmfcvisualmanager-class.md#drawpushbuttonwinxp).)|  
|[CMFCVisualManagerWindows::GetButtonExtraBorder](#getbuttonextraborder)|도구 모음 단추를 그릴 때이 메서드를 호출 하는 프레임 워크입니다. (재정의 [CMFCVisualManager::GetButtonExtraBorder](../../mfc/reference/cmfcvisualmanager-class.md#getbuttonextraborder).)|  
|[CMFCVisualManagerWindows::GetCaptionButtonExtraBorder](#getcaptionbuttonextraborder)|(재정의 [CMFCVisualManager::GetCaptionButtonExtraBorder](../../mfc/reference/cmfcvisualmanager-class.md#getcaptionbuttonextraborder).)|  
|[CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight](#getdockingpanecaptionextraheight)|(`CMFCVisualManager::GetDockingPaneCaptionExtraHeight`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor](#gethighlightedmenuitemtextcolor)|(`CMFCVisualManagerOfficeXP::GetHighlightedMenuItemTextColor`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::GetPopupMenuGap](#getpopupmenugap)|(`CMFCVisualManagerOfficeXP::GetPopupMenuGap`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::GetToolbarButtonTextColor](#gettoolbarbuttontextcolor)|(`CMFCVisualManagerOfficeXP::GetToolbarButtonTextColor`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::IsDefaultWinXPPopupButton](#isdefaultwinxppopupbutton)|(재정의 [CMFCVisualManager::IsDefaultWinXPPopupButton](../../mfc/reference/cmfcvisualmanager-class.md#isdefaultwinxppopupbutton).)|  
|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](#ishighlightwholemenuitem)|(`CMFCVisualManagerOfficeXP::IsHighlightWholeMenuItem`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::IsOfficeStyleMenus](#isofficestylemenus)||  
|[CMFCVisualManagerWindows::IsOfficeXPStyleMenus](#isofficexpstylemenus)|비주얼 관리자 Office XP 스타일의 메뉴를 구현 하는지 여부를 나타냅니다. (재정의 [CMFCVisualManager::IsOfficeXPStyleMenus](../../mfc/reference/cmfcvisualmanager-class.md#isofficexpstylemenus).)|  
|[CMFCVisualManagerWindows::IsWindowsThemingSupported](#iswindowsthemingsupported)|(`CMFCVisualManager::IsWindowsThemingSupported`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::IsWinXPThemeAvailable](#iswinxpthemeavailable)|Windows 테마를 사용할 수 있는지 여부를 나타냅니다. 테마에는 Windows XP 테마 수 또는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 테마입니다.|  
|[CMFCVisualManagerWindows::OnDrawBarGripper](#ondrawbargripper)|(`CMFCVisualManagerOfficeXP::OnDrawBarGripper`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawBrowseButton](#ondrawbrowsebutton)|(`CMFCVisualManagerOfficeXP::OnDrawBrowseButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawButtonBorder](#ondrawbuttonborder)|(`CMFCVisualManagerOfficeXP::OnDrawButtonBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawButtonSeparator](#ondrawbuttonseparator)|(`CMFCVisualManagerOfficeXP::OnDrawButtonSeparator`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButton](#ondrawcaptionbutton)|(`CMFCVisualManagerOfficeXP::OnDrawCaptionButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButtonIcon](#ondrawcaptionbuttonicon)|(`CMFCVisualManagerOfficeXP::OnDrawCaptionButtonIcon`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](#ondrawcheckboxex)|(재정의 [CMFCVisualManager::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcheckboxex).)|  
|[CMFCVisualManagerWindows::OnDrawComboBorder](#ondrawcomboborder)|(`CMFCVisualManagerOfficeXP::OnDrawComboBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawComboDropButton](#ondrawcombodropbutton)|(`CMFCVisualManagerOfficeXP::OnDrawComboDropButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawControlBorder](#ondrawcontrolborder)|(재정의 [CMFCVisualManager::OnDrawControlBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawcontrolborder).)|  
|[CMFCVisualManagerWindows::OnDrawEditBorder](#ondraweditborder)|(`CMFCVisualManagerOfficeXP::OnDrawEditBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawExpandingBox](#ondrawexpandingbox)|(재정의 [CMFCVisualManager::OnDrawExpandingBox](../../mfc/reference/cmfcvisualmanager-class.md#ondrawexpandingbox).)|  
|[CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder](#ondrawfloatingtoolbarborder)|(`CMFCVisualManagerOfficeXP::OnDrawFloatingToolbarBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder](#ondrawheaderctrlborder)|프레임 워크의 인스턴스 주위의 테두리를 그릴 때이 메서드를 호출는 [CMFCHeaderCtrl 클래스](../../mfc/reference/cmfcheaderctrl-class.md)합니다. (재정의 [CMFCVisualManager::OnDrawHeaderCtrlBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawheaderctrlborder).)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow](#ondrawheaderctrlsortarrow)|헤더 컨트롤의 정렬 화살표를 그릴 때이 함수를 호출 하는 프레임 워크입니다. (재정의 [CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../../mfc/reference/cmfcvisualmanager-class.md#ondrawheaderctrlsortarrow).)|  
|[CMFCVisualManagerWindows::OnDrawMenuBorder](#ondrawmenuborder)|(`CMFCVisualManagerOfficeXP::OnDrawMenuBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawMenuSystemButton](#ondrawmenusystembutton)|(`CMFCVisualManagerOfficeXP::OnDrawMenuSystemButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawMiniFrameBorder](#ondrawminiframeborder)|(`CMFCVisualManagerOfficeXP::OnDrawMiniFrameBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder](#ondrawoutlookpagebuttonborder)|Outlook 페이지 단추의 테두리를 그릴 때 프레임 워크에서 호출 합니다. (재정의 [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawoutlookpagebuttonborder).)|  
|[CMFCVisualManagerWindows::OnDrawPaneBorder](#ondrawpaneborder)|(`CMFCVisualManagerOfficeXP::OnDrawPaneBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawPaneCaption](#ondrawpanecaption)|(`CMFCVisualManagerOfficeXP::OnDrawPaneCaption`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder](#ondrawpopupwindowbuttonborder)|(`CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawScrollButtons](#ondrawscrollbuttons)|(`CMFCVisualManagerOfficeXP::OnDrawScrollButtons`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawSeparator](#ondrawseparator)|(`CMFCVisualManagerOfficeXP::OnDrawSeparator`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawSpinButtons](#ondrawspinbuttons)|(`CMFCVisualManagerOfficeXP::OnDrawSpinButtons`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder](#ondrawstatusbarpaneborder)|(`CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarProgress](#ondrawstatusbarprogress)|진행률 표시기 그릴 때이 메서드를 호출 프레임 워크는 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) 개체입니다. (재정의 [CMFCVisualManager::OnDrawStatusBarProgress](../../mfc/reference/cmfcvisualmanager-class.md#ondrawstatusbarprogress).)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](#ondrawstatusbarsizebox)|프레임 워크에 대 한 크기 상자를 그릴 때이 메서드 호출을 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)합니다. (재정의 [CMFCVisualManager::OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanager-class.md#ondrawstatusbarsizebox).)|  
|[CMFCVisualManagerWindows::OnDrawTab](#ondrawtab)|(`CMFCVisualManagerOfficeXP::OnDrawTab`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawTabCloseButton](#ondrawtabclosebutton)|(`CMFCVisualManagerOfficeXP::OnDrawTabCloseButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawTabsButtonBorder](#ondrawtabsbuttonborder)|(`CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawTask](#ondrawtask)|(`CMFCVisualManagerOfficeXP::OnDrawTask`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder](#ondrawtasksgroupareaborder)|(`CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupCaption](#ondrawtasksgroupcaption)|(`CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnDrawTearOffCaption](#ondrawtearoffcaption)|(`CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnErasePopupWindowButton](#onerasepopupwindowbutton)|(`CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnEraseTabsArea](#onerasetabsarea)|(`CMFCVisualManagerOfficeXP::OnEraseTabsArea`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnEraseTabsButton](#onerasetabsbutton)|(`CMFCVisualManagerOfficeXP::OnEraseTabsButton`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnEraseTabsFrame](#onerasetabsframe)|프레임 워크에서 프레임을 지울 때이 메서드를 호출는 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md)합니다. (재정의 [CMFCVisualManager::OnEraseTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#onerasetabsframe).)|  
|[CMFCVisualManagerWindows::OnFillBarBackground](#onfillbarbackground)|(`CMFCVisualManagerOfficeXP::OnFillBarBackground`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnFillButtonInterior](#onfillbuttoninterior)|(`CMFCVisualManagerOfficeXP::OnFillButtonInterior`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnFillCommandsListBackground](#onfillcommandslistbackground)|(`CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnFillMiniFrameCaption](#onfillminiframecaption)|(`CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnFillOutlookPageButton](#onfilloutlookpagebutton)|프레임 워크는 Outlook 페이지 단추의 내부를 채울 때이 메서드를 호출 합니다. (재정의 [CMFCVisualManager::OnFillOutlookPageButton](../../mfc/reference/cmfcvisualmanager-class.md#onfilloutlookpagebutton).)|  
|[CMFCVisualManagerWindows::OnFillTasksGroupInterior](#onfilltasksgroupinterior)|(`CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnFillTasksPaneBackground](#onfilltaskspanebackground)|프레임 워크의 배경을 채우는 경우이 메서드를 호출는 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 제어 합니다. (재정의 [CMFCVisualManager::OnFillTasksPaneBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfilltaskspanebackground).)|  
|[CMFCVisualManagerWindows::OnHighlightMenuItem](#onhighlightmenuitem)|(`CMFCVisualManagerOfficeXP::OnHighlightMenuItem`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems](#onhighlightrarelyusedmenuitems)|(`CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::OnUpdateSystemColors](#onupdatesystemcolors)|(`CMFCVisualManagerOfficeXP::OnUpdateSystemColors`를 재정의합니다.)|  
|[CMFCVisualManagerWindows::SetOfficeStyleMenus](#setofficestylemenus)||  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCVisualManagerWindows::m_b3DTabsXPTheme](#m_b3dtabsxptheme)|Windows XP 테마 3D 탭에 표시 되는지 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 사용 하는 `CMFCVisualManagerWindows` 현재 Windows XP를 모방 하기 위해 응용 프로그램의 모양을 변경 하는 클래스 또는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 응용 프로그램이 실행 되는 컴퓨터에는 테마입니다.  
  
 그러나 Windows 테마를 사용할 수 없습니다 응용 프로그램이 Windows XP 이전 버전의 Windows에서 실행 되는 경우 또는 사용자가 사용 하기 때문에 테마를 사용할 수 있는 경우는 **클래식** 보기. 응용 프로그램에 정의 된 기본 비주얼 관리자를 사용 하 여 없는 테마를 사용할 수 있는 경우 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다 `CMFCVisualManagerWindows`합니다. 이 코드 조각은의 일부인는 [바탕 화면 경고 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo #&10;](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagerwindows-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxvisualmanagerwindows.h  
  
##  <a name="a-namealwayshighlight3dtabsa--cmfcvisualmanagerwindowsalwayshighlight3dtabs"></a><a name="alwayshighlight3dtabs"></a>CMFCVisualManagerWindows::AlwaysHighlight3DTabs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AlwaysHighlight3DTabs() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namecmfcvisualmanagerwindowsa--cmfcvisualmanagerwindowscmfcvisualmanagerwindows"></a><a name="cmfcvisualmanagerwindows"></a>CMFCVisualManagerWindows::CMFCVisualManagerWindows  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCVisualManagerWindows(BOOL bIsTemporary = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bIsTemporary`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namedrawcomboborderwinxpa--cmfcvisualmanagerwindowsdrawcomboborderwinxp"></a><a name="drawcomboborderwinxp"></a>CMFCVisualManagerWindows::DrawComboBorderWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawComboBorderWinXP(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bDisabled`  
 [in] `bIsDropped`  
 [in] `bIsHighlighted`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namedrawcombodropbuttonwinxpa--cmfcvisualmanagerwindowsdrawcombodropbuttonwinxp"></a><a name="drawcombodropbuttonwinxp"></a>CMFCVisualManagerWindows::DrawComboDropButtonWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawComboDropButtonWinXP(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bDisabled`  
 [in] `bIsDropped`  
 [in] `bIsHighlighted`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namedrawpushbuttonwinxpa--cmfcvisualmanagerwindowsdrawpushbuttonwinxp"></a><a name="drawpushbuttonwinxp"></a>CMFCVisualManagerWindows::DrawPushButtonWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawPushButtonWinXP(
    CDC* pDC,  
    CRect rect,  
    CMFCButton* pButton,  
    UINT uiState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pButton`  
 [in] `uiState`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetbuttonextrabordera--cmfcvisualmanagerwindowsgetbuttonextraborder"></a><a name="getbuttonextraborder"></a>CMFCVisualManagerWindows::GetButtonExtraBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetButtonExtraBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcaptionbuttonextrabordera--cmfcvisualmanagerwindowsgetcaptionbuttonextraborder"></a><a name="getcaptionbuttonextraborder"></a>CMFCVisualManagerWindows::GetCaptionButtonExtraBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCaptionButtonExtraBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetdockingpanecaptionextraheighta--cmfcvisualmanagerwindowsgetdockingpanecaptionextraheight"></a><a name="getdockingpanecaptionextraheight"></a>CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetDockingPaneCaptionExtraHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegethighlightedmenuitemtextcolora--cmfcvisualmanagerwindowsgethighlightedmenuitemtextcolor"></a><a name="gethighlightedmenuitemtextcolor"></a>CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetHighlightedMenuItemTextColor(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetpopupmenugapa--cmfcvisualmanagerwindowsgetpopupmenugap"></a><a name="getpopupmenugap"></a>CMFCVisualManagerWindows::GetPopupMenuGap  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetPopupMenuGap() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettoolbarbuttontextcolora--cmfcvisualmanagerwindowsgettoolbarbuttontextcolor"></a><a name="gettoolbarbuttontextcolor"></a>CMFCVisualManagerWindows::GetToolbarButtonTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetToolbarButtonTextColor(
    CMFCToolBarButton* pButton,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 [in] `state`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisdefaultwinxppopupbuttona--cmfcvisualmanagerwindowsisdefaultwinxppopupbutton"></a><a name="isdefaultwinxppopupbutton"></a>CMFCVisualManagerWindows::IsDefaultWinXPPopupButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultWinXPPopupButton(CMFCDesktopAlertWndButton* pButton) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameishighlightwholemenuitema--cmfcvisualmanagerwindowsishighlightwholemenuitem"></a><a name="ishighlightwholemenuitem"></a>CMFCVisualManagerWindows::IsHighlightWholeMenuItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsHighlightWholeMenuItem();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisofficestylemenusa--cmfcvisualmanagerwindowsisofficestylemenus"></a><a name="isofficestylemenus"></a>CMFCVisualManagerWindows::IsOfficeStyleMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsOfficeStyleMenus() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisofficexpstylemenusa--cmfcvisualmanagerwindowsisofficexpstylemenus"></a><a name="isofficexpstylemenus"></a>CMFCVisualManagerWindows::IsOfficeXPStyleMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsOfficeXPStyleMenus() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameiswindowsthemingsupporteda--cmfcvisualmanagerwindowsiswindowsthemingsupported"></a><a name="iswindowsthemingsupported"></a>CMFCVisualManagerWindows::IsWindowsThemingSupported  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsWindowsThemingSupported() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameiswinxpthemeavailablea--cmfcvisualmanagerwindowsiswinxpthemeavailable"></a><a name="iswinxpthemeavailable"></a>CMFCVisualManagerWindows::IsWinXPThemeAvailable  
 Windows XP 여부를 확인 또는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 테마를 사용할 수 있습니다.  
  
```  
static BOOL IsWinXPThemeAvailible();
```  
  
### <a name="return-value"></a>반환 값  
 테마는 사용할 수 있습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 모두 Windows XP에 대 한 유효 및 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 테마입니다.  
  
 `IsWinXPThemeAvailable`동일 `CMFCVisualManagerWindows::IsWindowsThemingAvailable` 점을 제외 하 고 `IsWinXPThemeAvailable` 는 정적 메서드입니다. 따라서 존재 하지 않는 경우 임시 비주얼 관리자를 만듭니다.  
  
 `IsWinXPThemeAvailable`항상 Windows XP 이전 버전의 Windows에 대 한 0을 반환 합니다.  
  
##  <a name="a-namemb3dtabsxpthemea--cmfcvisualmanagerwindowsmb3dtabsxptheme"></a><a name="m_b3dtabsxptheme"></a>CMFCVisualManagerWindows::m_b3DTabsXPTheme  
 비주얼 관리자 3D 탭을 표시 하는지 여부를 결정 하는 부울 매개 변수입니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_b3DTabsXPTheme;  
```  
  
##  <a name="a-nameondrawbargrippera--cmfcvisualmanagerwindowsondrawbargripper"></a><a name="ondrawbargripper"></a>CMFCVisualManagerWindows::OnDrawBarGripper  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBarGripper(
    CDC* pDC,  
    CRect rectGripper,  
    BOOL bHorz,  
    CBasePane* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectGripper`  
 [in] `bHorz`  
 [in] `pBar`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawbrowsebuttona--cmfcvisualmanagerwindowsondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCVisualManagerWindows::OnDrawBrowseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    CMFCEditBrowseCtrl* pEdit,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pEdit`  
 [in] `state`  
 [in] `clrText`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawbuttonbordera--cmfcvisualmanagerwindowsondrawbuttonborder"></a><a name="ondrawbuttonborder"></a>CMFCVisualManagerWindows::OnDrawButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawButtonBorder(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `state`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawbuttonseparatora--cmfcvisualmanagerwindowsondrawbuttonseparator"></a><a name="ondrawbuttonseparator"></a>CMFCVisualManagerWindows::OnDrawButtonSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawButtonSeparator(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `state`  
 [in] `bHorz`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawcaptionbuttona--cmfcvisualmanagerwindowsondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a>CMFCVisualManagerWindows::OnDrawCaptionButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCaptionButton(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    BOOL bActive,  
    BOOL bHorz,  
    BOOL bMaximized,  
    BOOL bDisabled,  
    int nImageID = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pButton`  
 [in] `bActive`  
 [in] `bHorz`  
 [in] `bMaximized`  
 [in] `bDisabled`  
 [in] `nImageID`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawcaptionbuttonicona--cmfcvisualmanagerwindowsondrawcaptionbuttonicon"></a><a name="ondrawcaptionbuttonicon"></a>CMFCVisualManagerWindows::OnDrawCaptionButtonIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCaptionButtonIcon(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    CMenuImages::IMAGES_IDS id,  
    BOOL bActive,  
    BOOL bDisabled,  
    CPoint ptImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pButton`  
 [in] `id`  
 [in] `bActive`  
 [in] `bDisabled`  
 [in] `ptImage`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawcheckboxexa--cmfcvisualmanagerwindowsondrawcheckboxex"></a><a name="ondrawcheckboxex"></a>CMFCVisualManagerWindows::OnDrawCheckBoxEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCheckBoxEx(
    CDC* pDC,  
    CRect rect,  
    int nState,  
    BOOL bHighlighted,  
    BOOL bPressed,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `nState`  
 [in] `bHighlighted`  
 [in] `bPressed`  
 [in] `bEnabled`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawcombobordera--cmfcvisualmanagerwindowsondrawcomboborder"></a><a name="ondrawcomboborder"></a>CMFCVisualManagerWindows::OnDrawComboBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawComboBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bDisabled`  
 [in] `bIsDropped`  
 [in] `bIsHighlighted`  
 [in] `pButton`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawcombodropbuttona--cmfcvisualmanagerwindowsondrawcombodropbutton"></a><a name="ondrawcombodropbutton"></a>CMFCVisualManagerWindows::OnDrawComboDropButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawComboDropButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bDisabled`  
 [in] `bIsDropped`  
 [in] `bIsHighlighted`  
 [in] `pButton`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawcontrolbordera--cmfcvisualmanagerwindowsondrawcontrolborder"></a><a name="ondrawcontrolborder"></a>CMFCVisualManagerWindows::OnDrawControlBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawControlBorder(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndCtrl`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondraweditbordera--cmfcvisualmanagerwindowsondraweditborder"></a><a name="ondraweditborder"></a>CMFCVisualManagerWindows::OnDrawEditBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawEditBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsHighlighted,  
    CMFCToolBarEditBoxButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bDisabled`  
 [in] `bIsHighlighted`  
 [in] `pButton`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawexpandingboxa--cmfcvisualmanagerwindowsondrawexpandingbox"></a><a name="ondrawexpandingbox"></a>CMFCVisualManagerWindows::OnDrawExpandingBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawExpandingBox(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsOpened,  
    COLORREF colorBox);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsOpened`  
 [in] `colorBox`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawfloatingtoolbarbordera--cmfcvisualmanagerwindowsondrawfloatingtoolbarborder"></a><a name="ondrawfloatingtoolbarborder"></a>CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawFloatingToolbarBorder(
    CDC* pDC,  
    CMFCBaseToolBar* pToolBar,  
    CRect rectBorder,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pToolBar`  
 [in] `rectBorder`  
 [in] `rectBorderSize`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawheaderctrlbordera--cmfcvisualmanagerwindowsondrawheaderctrlborder"></a><a name="ondrawheaderctrlborder"></a>CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawHeaderCtrlBorder(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pCtrl`  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsPressed`  
 [in] `bIsHighlighted`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawheaderctrlsortarrowa--cmfcvisualmanagerwindowsondrawheaderctrlsortarrow"></a><a name="ondrawheaderctrlsortarrow"></a>CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawHeaderCtrlSortArrow(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsUp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pCtrl`  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsUp`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawmenubordera--cmfcvisualmanagerwindowsondrawmenuborder"></a><a name="ondrawmenuborder"></a>CMFCVisualManagerWindows::OnDrawMenuBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCPopu* pMenu,  
    CRect rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pMenu`  
 [in] `rect`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawmenusystembuttona--cmfcvisualmanagerwindowsondrawmenusystembutton"></a><a name="ondrawmenusystembutton"></a>CMFCVisualManagerWindows::OnDrawMenuSystemButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuSystemButton(
    CDC* pDC,  
    CRect rect,  
    UINT uiSystemCommand,  
    UINT nStyle,  
    BOOL bHighlight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `uiSystemCommand`  
 [in] `nStyle`  
 [in] `bHighlight`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawminiframebordera--cmfcvisualmanagerwindowsondrawminiframeborder"></a><a name="ondrawminiframeborder"></a>CMFCVisualManagerWindows::OnDrawMiniFrameBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMiniFrameBorder(
    CDC* pDC,  
    CPaneFrameWnd* pFrameWnd,  
    CRect rectBorder,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pFrameWnd`  
 [in] `rectBorder`  
 [in] `rectBorderSize`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawoutlookpagebuttonbordera--cmfcvisualmanagerwindowsondrawoutlookpagebuttonborder"></a><a name="ondrawoutlookpagebuttonborder"></a>CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawOutlookPageButtonBorder(
    CDC* pDC,  
    CRect& rectBtn,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectBtn`  
 [in] `bIsHighlighted`  
 [in] `bIsPressed`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawpanebordera--cmfcvisualmanagerwindowsondrawpaneborder"></a><a name="ondrawpaneborder"></a>CMFCVisualManagerWindows::OnDrawPaneBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPaneBorder(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rect`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawpanecaptiona--cmfcvisualmanagerwindowsondrawpanecaption"></a><a name="ondrawpanecaption"></a>CMFCVisualManagerWindows::OnDrawPaneCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pBar`  
 [in] `bActive`  
 [in] `rectCaption`  
 [in] `rectButtons`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawpopupwindowbuttonbordera--cmfcvisualmanagerwindowsondrawpopupwindowbuttonborder"></a><a name="ondrawpopupwindowbuttonborder"></a>CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPopupWindowButtonBorder(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectClient`  
 [in] `pButton`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawscrollbuttonsa--cmfcvisualmanagerwindowsondrawscrollbuttons"></a><a name="ondrawscrollbuttons"></a>CMFCVisualManagerWindows::OnDrawScrollButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawScrollButtons(
    CDC* pDC,  
    const CRect& rect,  
    const int nBorderSize,  
    int iImage,  
    BOOL bHilited);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `nBorderSize`  
 [in] `iImage`  
 [in] `bHilited`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawseparatora--cmfcvisualmanagerwindowsondrawseparator"></a><a name="ondrawseparator"></a>CMFCVisualManagerWindows::OnDrawSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rect`  
 [in] `bIsHoriz`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawspinbuttonsa--cmfcvisualmanagerwindowsondrawspinbuttons"></a><a name="ondrawspinbuttons"></a>CMFCVisualManagerWindows::OnDrawSpinButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawSpinButtons(
    CDC* pDC,  
    CRect rectSpin,  
    int nState,  
    BOOL bOrientation,  
    CMFCSpinButtonCtrl* pSpinCtrl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectSpin`  
 [in] `nState`  
 [in] `bOrientation`  
 [in] `pSpinCtrl`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawstatusbarpanebordera--cmfcvisualmanagerwindowsondrawstatusbarpaneborder"></a><a name="ondrawstatusbarpaneborder"></a>CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawStatusBarPaneBorder(
    CDC* pDC,  
    CMFCStatusBar* pBar,  
    CRect rectPane,  
    UINT uiID,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rectPane`  
 [in] `uiID`  
 [in] `nStyle`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawstatusbarprogressa--cmfcvisualmanagerwindowsondrawstatusbarprogress"></a><a name="ondrawstatusbarprogress"></a>CMFCVisualManagerWindows::OnDrawStatusBarProgress  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawStatusBarProgress(
    CDC* pDC,  
    CMFCStatusBar* pStatusBar,  
    CRect rectProgress,  
    int nProgressTotal,  
    int nProgressCurr,  
    COLORREF clrBar,  
    COLORREF clrProgressBarDest,  
    COLORREF clrProgressText,  
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pStatusBar`  
 [in] `rectProgress`  
 [in] `nProgressTotal`  
 [in] `nProgressCurr`  
 [in] `clrBar`  
 [in] `clrProgressBarDest`  
 [in] `clrProgressText`  
 [in] `bProgressText`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawstatusbarsizeboxa--cmfcvisualmanagerwindowsondrawstatusbarsizebox"></a><a name="ondrawstatusbarsizebox"></a>CMFCVisualManagerWindows::OnDrawStatusBarSizeBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawStatusBarSizeBox(
    CDC* pDC,  
    CMFCStatusBar* pStatBar,  
    CRect rectSizeBox);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pStatBar`  
 [in] `rectSizeBox`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtaba--cmfcvisualmanagerwindowsondrawtab"></a><a name="ondrawtab"></a>CMFCVisualManagerWindows::OnDrawTab  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectTab`  
 [in] `iTab`  
 [in] `bIsActive`  
 [in] `pTabWnd`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtabclosebuttona--cmfcvisualmanagerwindowsondrawtabclosebutton"></a><a name="ondrawtabclosebutton"></a>CMFCVisualManagerWindows::OnDrawTabCloseButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTabCloseButton(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pTabWnd`  
 [in] `bIsHighlighted`  
 [in] `bIsPressed`  
 [in] `bIsDisabled`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtabsbuttonbordera--cmfcvisualmanagerwindowsondrawtabsbuttonborder"></a><a name="ondrawtabsbuttonborder"></a>CMFCVisualManagerWindows::OnDrawTabsButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTabsButtonBorder(
    CDC* pDC,  
    CRect& rect,  
    CMFCButton* pButton,  
    UINT uiState,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pButton`  
 [in] `uiState`  
 [in] `pWndTab`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtaska--cmfcvisualmanagerwindowsondrawtask"></a><a name="ondrawtask"></a>CMFCVisualManagerWindows::OnDrawTask  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTask(
    CDC* pDC,  
    CMFCTasksPaneTask* pTask,  
    CImageList* pIcons,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pTask`  
 [in] `pIcons`  
 [in] `bIsHighlighted`  
 [in] `bIsSelected`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtasksgroupareabordera--cmfcvisualmanagerwindowsondrawtasksgroupareaborder"></a><a name="ondrawtasksgroupareaborder"></a>CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTasksGroupAreaBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE,  
    BOOL bNoTitle = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bSpecial`  
 [in] `bNoTitle`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtasksgroupcaptiona--cmfcvisualmanagerwindowsondrawtasksgroupcaption"></a><a name="ondrawtasksgroupcaption"></a>CMFCVisualManagerWindows::OnDrawTasksGroupCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTasksGroupCaption(
    CDC* pDC,  
    CMFCTasksPaneTaskGroup* pGroup,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE,  
    BOOL bCanCollapse = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pGroup`  
 [in] `bIsHighlighted`  
 [in] `bIsSelected`  
 [in] `bCanCollapse`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawtearoffcaptiona--cmfcvisualmanagerwindowsondrawtearoffcaption"></a><a name="ondrawtearoffcaption"></a>CMFCVisualManagerWindows::OnDrawTearOffCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTearOffCaption(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsActive);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsActive`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonerasepopupwindowbuttona--cmfcvisualmanagerwindowsonerasepopupwindowbutton"></a><a name="onerasepopupwindowbutton"></a>CMFCVisualManagerWindows::OnErasePopupWindowButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnErasePopupWindowButton(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectClient`  
 [in] `pButton`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonerasetabsareaa--cmfcvisualmanagerwindowsonerasetabsarea"></a><a name="onerasetabsarea"></a>CMFCVisualManagerWindows::OnEraseTabsArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pTabWnd`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonerasetabsbuttona--cmfcvisualmanagerwindowsonerasetabsbutton"></a><a name="onerasetabsbutton"></a>CMFCVisualManagerWindows::OnEraseTabsButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEraseTabsButton(
    CDC* pDC,  
    CRect rect,  
    CMFCButton* pButton,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pButton`  
 [in] `pWndTab`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonerasetabsframea--cmfcvisualmanagerwindowsonerasetabsframe"></a><a name="onerasetabsframe"></a>CMFCVisualManagerWindows::OnEraseTabsFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnEraseTabsFrame(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `pTabWnd`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfillbarbackgrounda--cmfcvisualmanagerwindowsonfillbarbackground"></a><a name="onfillbarbackground"></a>CMFCVisualManagerWindows::OnFillBarBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillBarBackground(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rectClient,  
    CRect rectClip,  
    BOOL bNCArea = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rectClient`  
 [in] `rectClip`  
 [in] `bNCArea`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfillbuttoninteriora--cmfcvisualmanagerwindowsonfillbuttoninterior"></a><a name="onfillbuttoninterior"></a>CMFCVisualManagerWindows::OnFillButtonInterior  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillButtonInterior(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `state`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfillcommandslistbackgrounda--cmfcvisualmanagerwindowsonfillcommandslistbackground"></a><a name="onfillcommandslistbackground"></a>CMFCVisualManagerWindows::OnFillCommandsListBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillCommandsListBackground(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsSelected`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfillminiframecaptiona--cmfcvisualmanagerwindowsonfillminiframecaption"></a><a name="onfillminiframecaption"></a>CMFCVisualManagerWindows::OnFillMiniFrameCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CPaneFrameWnd* pFrameWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectCaption`  
 [in] `pFrameWnd`  
 [in] `bActive`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfilloutlookpagebuttona--cmfcvisualmanagerwindowsonfilloutlookpagebutton"></a><a name="onfilloutlookpagebutton"></a>CMFCVisualManagerWindows::OnFillOutlookPageButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillOutlookPageButton(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsHighlighted`  
 [in] `bIsPressed`  
 [in] `clrText`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfilltasksgroupinteriora--cmfcvisualmanagerwindowsonfilltasksgroupinterior"></a><a name="onfilltasksgroupinterior"></a>CMFCVisualManagerWindows::OnFillTasksGroupInterior  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillTasksGroupInterior(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `bSpecial`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfilltaskspanebackgrounda--cmfcvisualmanagerwindowsonfilltaskspanebackground"></a><a name="onfilltaskspanebackground"></a>CMFCVisualManagerWindows::OnFillTasksPaneBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillTasksPaneBackground(
    CDC* pDC,  
    CRect rectWorkArea);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectWorkArea`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonhighlightmenuitema--cmfcvisualmanagerwindowsonhighlightmenuitem"></a><a name="onhighlightmenuitem"></a>CMFCVisualManagerWindows::OnHighlightMenuItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnHighlightMenuItem(
    CDC* pDC,  
    CMFCToolBarMenuButton* pButton,  
    CRect rect,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `clrText`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonhighlightrarelyusedmenuitemsa--cmfcvisualmanagerwindowsonhighlightrarelyusedmenuitems"></a><a name="onhighlightrarelyusedmenuitems"></a>CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnHighlightRarelyUsedMenuItems(
    CDC* pDC,  
    CRect rectRarelyUsed);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rectRarelyUsed`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonupdatesystemcolorsa--cmfcvisualmanagerwindowsonupdatesystemcolors"></a><a name="onupdatesystemcolors"></a>CMFCVisualManagerWindows::OnUpdateSystemColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetofficestylemenusa--cmfcvisualmanagerwindowssetofficestylemenus"></a><a name="setofficestylemenus"></a>CMFCVisualManagerWindows::SetOfficeStyleMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetOfficeStyleMenus(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bOn`  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager 클래스](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP 클래스](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

