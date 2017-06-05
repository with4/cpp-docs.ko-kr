---
title: "CMFCMenuBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuBar class
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
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
ms.openlocfilehash: ab2896f5ebab0df894f70e5ddb85bae3a5e1d5af
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar 클래스
도킹을 구현하는 메뉴 모음입니다.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(`CMFCToolBar::AdjustLocations`를 재정의합니다.)|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|도구 모음 단추에 이미지 아래 텍스트 레이블을 표시할 수 있는지 여부를 지정 합니다. (재정의 [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu`를 재정의합니다.)|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|도구 모음에서의 가로 크기를 계산합니다. (재정의 [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(`CMFCToolBar::CalcLayout`를 재정의합니다.)|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|도구 모음에서 단추의 최대 높이 계산합니다. (재정의 [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|사용자 도구 모음을 닫을 수 있는지 여부를 지정 합니다. (재정의 [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|여부를 시스템 후 복원할 수는 도구 모음을 원래 상태로 사용자 지정을 결정 합니다. (재정의 [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCMenuBar::Create](#create)|메뉴 컨트롤을 만들고 연결 하는 `CMFCMenuBar` 개체입니다.|  
|[CMFCMenuBar::CreateEx](#createex)|만듭니다는 `CMFCMenuBar` 추가 스타일 옵션이 포함 된 개체입니다.|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|초기화는 `CMFCMenuBar` 개체입니다. 허용 된 `HMENU` 으로 채워진에 대 한 템플릿 역할을 하는 매개 변수 `CMFCMenuBar`합니다.|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|사용 하면 한 **도움말** 메뉴 표시줄의 오른쪽에 있는 콤보 상자입니다.|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|팝업 메뉴에 대 한 그림자를 표시할 것인지를 지정 합니다.|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(재정의 [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|도구 모음 단추의 너비를 반환합니다. (재정의 [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|리소스 파일의 원래 메뉴에 대 한 핸들을 반환합니다.|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|리소스 파일의 원래 메뉴에 대 한 리소스 식별자를 반환합니다.|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|에 대 한 포인터를 반환 된 **도움말** 콤보 상자입니다.|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|에 연결 된 메뉴에 핸들을 반환 된 `CMFCMenuBar` 개체입니다.|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|메뉴 개체에 대 한 현재 글로벌 글꼴을 반환합니다.|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|제공 된 항목 인덱스와 연결 된 도구 모음 단추를 반환 합니다.|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|도구 모음 단추의 높이 반환합니다. (재정의 [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|비활성화 된 메뉴 항목이 강조 표시 하는지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|도구 모음 테두리 확장 단추를 표시할 수 있는지 여부를 결정 합니다. (재정의 [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|사용할 수 없는 항목이 강조 표시 하는지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|팝업 메뉴에 그림자를 그릴 있는지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|최근에 사용한 메뉴 명령을 메뉴 모음에 표시 되는지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|팝업 메뉴에서 모든 명령을 표시 여부를 나타냅니다.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|메뉴는 짧은 지연 후 모든 명령을 표시 여부를 나타냅니다.|  
|[CMFCMenuBar::LoadState](#loadstate)|상태를 로드는 `CMFCMenuBar` 레지스트리에서 개체입니다.|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|사용자가 도구 모음에서 단추를 선택 하는 경우 프레임 워크에서 호출 합니다. (재정의 [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|프레임 창 리소스 파일에서 기본 메뉴를 로드할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(`CMFCToolBar::OnSendCommand`를 재정의합니다.)|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|메뉴 사용자 지정 모드에 있고 사용자는 메뉴 항목의 텍스트를 변경 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(`CMFCToolBar::OnToolHitTest`를 재정의합니다.)|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(`CMFCToolBar::PreTranslateMessage`를 재정의합니다.)|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|메뉴 사용자 지정 모드에 있고 사용자가 선택 하는 경우에 프레임 워크에서 호출 **재설정** 메뉴 모음에 대 한 합니다.|  
|[CMFCMenuBar::SaveState](#savestate)|상태를 저장 된 `CMFCMenuBar` 레지스트리에 개체입니다.|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|리소스 파일에서 원래 메뉴를 설정합니다.|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|MDI 자식 창에는 디스플레이 모드를 변경 하는 경우 프레임 워크에서 호출 합니다. MDI 자식 창을 새로 최대화 되는 더 이상 최대화 경우이 메서드는 메뉴 모음을 업데이트 합니다.|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|사용자가 동적으로 메뉴 단추를 만들 때 생성 되는 런타임 클래스 정보를 설정 합니다.|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|응용 프로그램에서 모든 메뉴에 대 한 글꼴을 설정합니다.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|메뉴 모음 최근에 사용한 메뉴 명령이 표시 여부를 지정 합니다.|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|메뉴 모음 모든 명령을 표시 되는지 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCMenuBar` 클래스는 도킹 기능을 구현 하는 메뉴 모음입니다. 닫을 수 없습니다.-항상 표시 되 고 있지만 도구 모음을 비슷합니다.  
  
 `CMFCMenuBar`최근에 사용한 메뉴 항목 개체를 표시 하는 옵션을 지원 합니다. 이 옵션을 사용 하는 경우는 `CMFCMenuBar` 처음 볼 때만 사용할 수 있는 명령 중 일부를 표시 합니다. 그리고 나면 최근에 사용한 명령은 원래 명령 집합이 함께 표시 됩니다. 또한 사용자 수 항상 사용 가능한 모든 명령을 보려면 메뉴를 확장 합니다. 따라서 사용 가능한 각 명령에 지속적으로 표시 하거나 최근에 선택 된 경우에 표시 하도록 구성 됩니다.  
  
 사용 하는 `CMFCMenuBar` 개체, 주 창 프레임 개체에 포함 합니다. 처리 하는 경우는 `WM_CREATE` 메시지, 호출 `CMFCMenuBar::Create` 또는 `CMFCMenuBar::CreateEx`합니다. 함수를 만들 있는 관계 없이 사용 하 여, 주 프레임 창에 대 한 포인터에 전달 합니다. 다음 호출 하 여 도킹을 사용 하도록 설정 [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking)합니다. 이 메뉴를 호출 하 여 도킹 [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCMenuBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 창 스타일 설정, 사용자 지정 단추를 사용 하도록 설정, 도움말 상자를 사용 하도록 설정, 팝업 메뉴에서 그림자를 사용 하도록 설정 및 메뉴 표시줄을 업데이트 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [IE 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_IEDemo #&1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo #&3;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 `CMFCMenuBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmenubar.h  
  
##  <a name="adjustlocations"></a>CMFCMenuBar::AdjustLocations  
 메뉴 모음에서 메뉴 항목의 위치를 조정합니다.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="allowchangetextlabels"></a>CMFCMenuBar::AllowChangeTextLabels  
 메뉴 모음에서 이미지 아래 텍스트 레이블을 허용 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 경우 사용자 이미지 아래 텍스트 레이블을 표시 하도록 선택할 수 있습니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="allowshowonpanemenu"></a>CMFCMenuBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="calcfixedlayout"></a>CMFCMenuBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="calclayout"></a>CMFCMenuBar::CalcLayout  

  
```  
virtual CSize CalcLayout(
    DWORD dwMode,  
    int nLength = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwMode`  
 [in] `nLength`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="calcmaxbuttonheight"></a>CMFCMenuBar::CalcMaxButtonHeight  

  
```  
virtual int CalcMaxButtonHeight();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="canbeclosed"></a>CMFCMenuBar::CanBeClosed  

  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="canberestored"></a>CMFCMenuBar::CanBeRestored  

  
```  
virtual BOOL CanBeRestored() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="create"></a>CMFCMenuBar::Create  
 메뉴 컨트롤을 만들고 연결 하는 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체입니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 새 부모 창에 대 한 포인터 `CMFCMenuBar` 개체입니다.  
  
 [in] `dwStyle`  
 새 메뉴 표시줄의 스타일입니다.  
  
 [in] `nID`  
 메뉴 표시줄의 자식 창에 대 한 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 후 한 `CMFCMenuBar` 개체를 호출 해야 `Create`합니다. 이 메서드가 만드는 `CMFCMenuBar` 제어 하 고 연결 하는 `CMFCMenuBar` 개체입니다.  
  
 도구 모음 스타일에 대 한 자세한 내용은 참조 [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle)합니다.  
  
##  <a name="createex"></a>CMFCMenuBar::CreateEx  
 만듭니다는 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 확장된 스타일을 지정된 하 여 개체입니다.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    CRect rcBorders = CRect(1,
    1,
    1,
    1),  
    UINT nID =AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 새 부모 창에 대 한 포인터 `CMFCMenuBar` 개체입니다.  
  
 [in] `dwCtrlStyle`  
 새 메뉴 모음에 대 한 추가 스타일입니다.  
  
 [in] `dwStyle`  
 새 메뉴 표시줄의 기본 스타일입니다.  
  
 [in] `rcBorders`  
 A `CRect` 테두리에 대 한 크기를 지정 하는 매개 변수는 `CMFCMenuBar` 개체입니다.  
  
 [in] `nID`  
 메뉴 표시줄의 자식 창에 대 한 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 대신이 함수를 사용 해야 [CMFCMenuBar::Create](#create) 도구 모음 스타일 이외에 스타일을 지정 하려는 경우. 일부 자주 사용 되는 추가 스타일은 `TBSTYLE_TRANSPARENT` 및 `CBRS_TOP`합니다.  
  
 추가 스타일의 목록에 대 한 참조 [Toolbar 컨트롤 및 단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760439), [일반적인 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498), 및 [일반적인 창 스타일](http://msdn.microsoft.com/library/windows/desktop/ms632600)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `CreateEx` 의 메서드는 `CMFCMenuBar` 클래스입니다. 이 코드 조각은의 일부인는 [IE 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_IEDemo #&1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo #&2;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>CMFCMenuBar::CreateFromMenu  
 초기화는 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체입니다. 이 메서드 모델은 `CMFCMenuBar` 후 개체는 `HMENU` 매개 변수입니다.  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenu`  
 메뉴 리소스에 대 한 핸들입니다. `CreateFromMenu`이 리소스에 대 한 템플릿으로 사용 하 여 `CMFCMenuBar`합니다.  
  
 [in] `bDefaultMenu`  
 새 메뉴의 기본 메뉴 인지 여부를 나타내는 부울입니다.  
  
 [in] `bForceUpdate`  
 이 메서드는 메뉴 업데이트 강제 있는지 여부를 나타내는 부울입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 메뉴 리소스와 같은 메뉴 항목이 메뉴 제어 하려는 경우. 중 하나를 호출한 후에이 메서드를 호출 하면 [CMFCMenuBar::Create](#create) 또는 [CMFCMenuBar::CreateEx](#createex)합니다.  
  
##  <a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox  
 사용 하면 한 **도움말** 메뉴 표시줄의 오른쪽에 있는 콤보 상자입니다.  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 단추에 대 한 명령 ID는 **도움말** 콤보 상자입니다.  
  
 [in] `lpszPrompt`  
 텍스트 비어 있고 활성화 되지 않은 경우 콤보 상자에 표시 되는 프레임 워크를 포함 하는 문자열입니다. 예를 들어 "여기에 텍스트" 입력 합니다.  
  
 [in] `nComboBoxWidth`  
 너비 (픽셀)에 있는 콤보 상자에 대 한 단추입니다.  
  
### <a name="remarks"></a>주의  
 **도움말** 콤보 상자가 유사 하 게는 **도움말** 의 메뉴 모음에 콤보 상자 [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)]합니다.  
  
 이 메서드를 호출 하면 `uiID` 이 메서드는 콤보 상자 숨깁니다 0으로 설정 합니다. 그렇지 않으면이 메서드는 콤보 상자 자동으로 표시 됩니다 메뉴 표시줄의 오른쪽에 있습니다. 이 메서드를 호출한 후 호출 [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) 은 삽입에 대 한 포인터를 얻으려면 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체입니다.  
  
##  <a name="enablemenushadows"></a>CMFCMenuBar::EnableMenuShadows  
 팝업 메뉴에 대 한 그림자를 수 있습니다.  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 팝업 메뉴에 그림자를 활성화 해야 하는지 여부를 나타내는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하는 알고리즘에는 복잡 하며 속도가 느린 시스템 응용 프로그램의 성능이 저하 될 수 있습니다.  
  
##  <a name="getavailableexpandsize"></a>CMFCMenuBar::GetAvailableExpandSize  

  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getcolumnwidth"></a>CMFCMenuBar::GetColumnWidth  

  
```  
virtual int GetColumnWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getdefaultmenu"></a>CMFCMenuBar::GetDefaultMenu  
 원래 메뉴에 대 한 핸들을 검색합니다. 프레임 워크는 리소스 파일에서 원래 메뉴를 로드합니다.  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 리소스에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램 메뉴 사용자 지정 하는 경우 원래 메뉴에 대 한 핸들을 검색 하려면이 메서드를 사용할 수 있습니다.  
  
##  <a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId  
 기본 메뉴에 대 한 리소스 식별자를 검색합니다.  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 리소스 식별자입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 로드에 대 한 기본 메뉴는 `CMFCMenuBar` 리소스 파일에서 개체입니다.  
  
##  <a name="getfloatpopupdirection"></a>CMFCMenuBar::GetFloatPopupDirection  

  
```  
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getforcedownarrows"></a>CMFCMenuBar::GetForceDownArrows  

  
```  
BOOL GetForceDownArrows();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="gethelpcombobox"></a>CMFCMenuBar::GetHelpCombobox  
 에 대 한 포인터를 반환 된 **도움말** 콤보 상자입니다.  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 **도움말** 콤보 상자입니다. `NULL`하는 경우는 **도움말** 콤보 상자 숨기 거 나 사용할 수 없습니다.  
  
### <a name="remarks"></a>주의  
 **도움말** 콤보 상자는 메뉴 표시줄의 오른쪽에 있습니다. 메서드를 호출 [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) 이 콤보 상자를 사용 하도록 합니다.  
  
##  <a name="gethmenu"></a>CMFCMenuBar::GetHMenu  
 에 연결 된 메뉴에 대 한 핸들을 검색 된 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체입니다.  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="getmenufont"></a>CMFCMenuBar::GetMenuFont  
 현재 메뉴 글꼴을 가져옵니다.  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHorz`  
 가로 또는 세로 글꼴을 반환할 것인지 지정 하는 부울 매개 변수입니다. `TRUE`가로 글꼴을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CFont](../../mfc/reference/cfont-class.md) 현재 메뉴 표시줄 글꼴을 포함 하는 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 응용 프로그램에 대 한 글로벌 매개 변수입니다. 두 가지 전역 글꼴 모든 유지 관리 됩니다 `CMFCMenuBar` 개체입니다. 이러한 별도 글꼴 가로 및 세로 메뉴 모음에 사용 됩니다.  
  
##  <a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem  
 검색 한 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) 항목 인덱스에 따라 메뉴 모음에는 개체입니다.  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iItem`  
 반환할 메뉴 항목의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CMFCToolBarButton` 개체에 지정 된 인덱스와 일치 하는 `iItem`합니다. `NULL`인덱스가 잘못 되었습니다 하는 경우.  
  
##  <a name="getrowheight"></a>CMFCMenuBar::GetRowHeight  

  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getsystembutton"></a>CMFCMenuBar::GetSystemButton  

  
```  
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,  
    BOOL bByCommand = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiBtn`  
 [in] `bByCommand`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getsystembuttonscount"></a>CMFCMenuBar::GetSystemButtonsCount  

  
```  
int GetSystemButtonsCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getsystemmenu"></a>CMFCMenuBar::GetSystemMenu  

  
```  
CMFCToolBarSystemMenuButton* GetSystemMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="highlightdisableditems"></a>CMFCMenuBar::HighlightDisabledItems  
 프레임 워크 흐리게 표시 된 메뉴 항목을 강조 표시 하는지 여부를 제어 합니다.  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHighlight`  
 프레임 워크를 사용할 수 없는 메뉴 항목 강조 표시 하는지 여부를 나타내는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 프레임 워크 강조 표시 하지 않습니다 사용할 수 없는 메뉴 항목 위로 마우스 포인터를 놓을 때.  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="ishighlightdisableditems"></a>CMFCMenuBar::IsHighlightDisabledItems  
 프레임 워크를 사용할 수 없는 메뉴 항목 강조 표시 하는지 여부를 나타냅니다.  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`사용할 수 없는 메뉴 항목이; 강조 표시 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 프레임 워크 강조 표시 하지 않습니다 사용할 수 없는 메뉴 항목 위로 마우스 포인터를 놓을 때. 사용 된 [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) 이 기능을 사용 하도록 설정 하는 방법입니다.  
  
##  <a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows  
 프레임 워크 팝업 메뉴에 대 한 그림자를 그릴지 여부를 나타냅니다.  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 워크; 메뉴 그림자를 그리는 경우에 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) 메서드를 사용 하도록 설정 하거나이 기능을 사용 하지 않도록 합니다.  
  
##  <a name="isrecentlyusedmenus"></a>CMFCMenuBar::IsRecentlyUsedMenus  
 최근에 사용한 메뉴 명령을 메뉴 모음에 표시 되는지 여부를 나타냅니다.  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CMFCMenuBar` 개체 표시 최근에 사용한 메뉴 명령 하 고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 함수를 사용 하 여 [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) 메뉴 모음 최근에 표시 되는지 여부를 제어할 메뉴 명령을 사용 합니다.  
  
##  <a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllCommands  
 메뉴 명령을 모두 표시 하는지 여부를 나타냅니다.  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CMFCMenuBar` 모든 표시 명령을 하 고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 A `CMFCMenuBar` 개체는 모든 명령을 표시 하거나 명령의 하위 집합만 표시 하도록 구성할 수 있습니다. 이 기능에 대 한 자세한 내용은 참조 [CMFCMenuBar 클래스](../../mfc/reference/cmfcmenubar-class.md)합니다.  
  
 `IsShowAllCommands`알려이 기능에 대 한 구성 방식에서 `CMFCMenuBar` 개체입니다. 메뉴 명령을 표시를 제어 하려면 메서드를 사용 하 여 [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) 및 [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)합니다.  
  
##  <a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay  
 나타냅니다 여부는 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체는 짧은 지연 후 모든 명령을 표시 합니다.  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 모음 약간의 지연 후 모든 메뉴를 표시 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 최근에 사용한 표시 항목에는 메뉴 모음을 구성할 때 두 가지 방법 중 하나에 전체 메뉴를 표시 하는 메뉴 모음:  
  
-   사용자 커서를 놓으면 메뉴의 아래쪽 화살표 위에 프로그래밍 된 지연 후 전체 메뉴를 표시 합니다.  
  
-   사용자가 메뉴 맨 아래에 있는 화살표를 클릭 한 후에 전체 메뉴를 표시 합니다.  
  
 기본적으로 모든 `CMFCMenuBar` 개체는 짧은 지연 후 전체 메뉴를 표시 하는 옵션을 사용 합니다. 이 옵션을 프로그래밍 방식으로 변경할 수 없습니다.는 `CMFCMenuBar` 클래스입니다. 그러나 사용자 동작을 변경할 수는 도구 모음 사용자 지정 하는 동안 사용 하 여는 **사용자 지정** 대화 상자...  
  
##  <a name="loadstate"></a>CMFCMenuBar::LoadState  
 Windows 레지스트리에서 메뉴 표시줄의 상태를 로드합니다.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 Windows 레지스트리 키의 경로 포함 하는 문자열입니다.  
  
 [in] `nIndex`  
 메뉴 모음에 대 한 컨트롤 ID입니다.  
  
 [in] `uiID`  
 예약 된 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CMFCMenuBar::SaveState](#savestate) 레지스트리에 메뉴 표시줄의 상태를 저장 하는 방법입니다. 저장 된 정보는 메뉴 항목, 도킹 상태 메뉴 표시줄의 위치를 포함 합니다.  
  
 대부분의 경우에서에 응용 프로그램 호출 하지 않습니다 `LoadState`합니다. 작업 영역을 초기화 하는 경우이 메서드를 호출 하는 프레임 워크입니다.  
  
##  <a name="onchangehot"></a>CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iHot`  
  
### <a name="remarks"></a>주의  
  
##  <a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded  
 프레임 워크는 리소스 파일에서 메뉴 리소스를 로드할 때이 메서드를 호출 합니다.  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenu`  
 메뉴에 대 한 핸들에 연결 된 `CMFCMenuBar` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 프레임 워크는 메뉴 리소스는 리소스 파일에서 로드 된 후 사용자 지정 코드를 실행 하려면이 함수를 재정의 합니다.  
  
##  <a name="onsendcommand"></a>CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnSetDefaultButtonText  
 메뉴 모음에서 항목의 텍스트를 변경할 때이 메서드를 호출 하는 프레임 워크입니다.  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 에 대 한 포인터는 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) 사용자 지정 하는 사용자가 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 워크 메뉴 모음;에 사용자 변경 내용을 적용 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현에서는 사용자가 제공 하는 텍스트에는 단추의 텍스트를 변경 합니다.  
  
##  <a name="ontoolhittest"></a>CMFCMenuBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="pretranslatemessage"></a>CMFCMenuBar::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMsg`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="restoreoriginalstate"></a>CMFCMenuBar::RestoreOriginalstate  
 사용자가 선택 된 프레임 워크에서 호출 **재설정** 에서 **사용자 지정** 대화 상자입니다.  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용자가 선택 **재설정** 사용자 지정 메뉴에서 합니다. 수동으로 메뉴 표시줄의 상태를 프로그래밍 방식으로 다시 설정 하려면이 메서드를 호출할 수 있습니다. 이 메서드는 리소스 파일에서 원래 상태를 로드합니다.  
  
 사용자가 선택 될 때 한 처리를 수행 하려는 경우이 메서드를 재정의 **재설정** 옵션입니다.  
  
##  <a name="savestate"></a>CMFCMenuBar::SaveState  
 상태를 저장 된 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Windows 레지스트리에 개체입니다.  
  
```  
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 Windows 레지스트리 키의 경로 포함 하는 문자열입니다.  
  
 [in] `nIndex`  
 메뉴 모음에 대 한 컨트롤 ID입니다.  
  
 [in] `uiID`  
 예약 된 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`성공 하면 그렇지 않으면 `FALSE`;  
  
### <a name="remarks"></a>주의  
 일반적으로 응용 프로그램 호출 하지 않습니다 `SaveState`합니다. 작업 영역을 serialize 할 때이 메서드를 호출 하는 프레임 워크입니다. 자세한 내용은 참조 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)합니다.  
  
 저장 된 정보는 메뉴 항목, 도킹 상태 메뉴 표시줄의 위치를 포함 합니다.  
  
##  <a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId  
 설정에 대 한 기본 메뉴는 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 리소스 ID를 기반으로 개체  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiResId`  
 새 기본 메뉴에 대 한 리소스 ID입니다.  
  
### <a name="remarks"></a>주의  
 [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) 메서드는 리소스 파일에서 기본 메뉴에 복원 합니다.  
  
 사용 된 [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) 복원 되지 않고 기본 메뉴를 검색 하는 메서드입니다.  
  
##  <a name="setforcedownarrows"></a>CMFCMenuBar::SetForceDownArrows  

  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bValue`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setmaximizemode"></a>CMFCMenuBar::SetMaximizeMode  
 프레임 워크의 디스플레이 모드를 변경 하는 MDI 하 고 메뉴 모음을 업데이트 해야 하는 경우이 메서드를 호출 합니다.  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bMax`  
 모드를 지정 하는 부울입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 [in] `pWnd`  
 변경 되 고 있는 MDI 자식 창에 대 한 포인터입니다.  
  
 [in] `bRecalcLayout`  
 메뉴 표시줄의 레이아웃 즉시 계산 수 있는지 여부를 지정 하는 부울입니다.  
  
### <a name="remarks"></a>주의  
 MDI 주 프레임 창에 연결 하는 메뉴 모음 MDI 자식 창을 최대화 되 면 시스템 메뉴를 표시 및 **최소화**, **최대화** 및 **닫기** 단추입니다. 경우 `bMax` 는 `TRUE` 및 `pWnd` 없는 `NULL`MDI 자식 창을 최대화 하 고 메뉴 모음 추가 컨트롤을 통합 해야 합니다. 그렇지 않으면 메뉴 모음 일반 상태로 돌아갑니다.  
  
##  <a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC  
 프레임 워크에는 사용자가 메뉴 단추를 만들 때 사용 하는 런타임 클래스 정보를 설정 합니다.  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuButtonRTC`  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 에서 파생 된 클래스에 대 한 정보는 [CMFCMenuButton 클래스](../../mfc/reference/cmfcmenubutton-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 메뉴 모음에 새 단추를 추가 하는 사용자, 프레임 워크 단추 동적으로 만듭니다. 기본적으로 생성 됩니다. `CMFCMenuButton` 개체입니다. 프레임 워크를 만들고 단추 개체의 형식을 변경 하려면이 메서드를 재정의 합니다.  
  
##  <a name="setmenufont"></a>CMFCMenuBar::SetMenuFont  
 응용 프로그램에서 모든 메뉴 모음에 대 한 글꼴을 설정합니다.  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpLogFont`  
 에 대 한 포인터는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327) 글꼴 집합을 정의 하는 구조입니다.  
  
 [in] `bHorz`  
 TRUE 이면는 `lpLogFont` 가로 글꼴에 대 한 사용 하려는 경우 세로 방향 글꼴, FALSE에 사용할 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 두 개의 글꼴은 모든 사용 `CMFCMenuBar` 개체입니다. 이러한 별도 글꼴 가로 및 세로 메뉴 모음에 사용 됩니다.  
  
 글꼴 설정을 전역 변수 및 모든 적용 `CMFCMenuBar` 개체입니다.  
  
##  <a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsedMenus  
 메뉴 명령에 사용 되는 메뉴 모음의 최근에 표시 되는지 여부를 제어 합니다.  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bOn`  
 최근에 사용한 메뉴 명령이 표시 되는지 여부를 제어 하는 부울입니다.  
  
##  <a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllCommands  
 사용 가능한 모든 명령을 메뉴에 표시 되는지 여부를 제어 합니다.  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShowAllCommands`  
 팝업 메뉴에 메뉴 명령을 모두 표시 되는지 여부를 지정 하는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 메뉴에 메뉴 명령을 모두 표시 되지 않으면, 자주 사용 되지 않는 명령 숨깁니다. 메뉴 명령을 표시 하는 방법에 대 한 자세한 내용은 참조 [CMFCMenuBar 클래스](../../mfc/reference/cmfcmenubar-class.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)

