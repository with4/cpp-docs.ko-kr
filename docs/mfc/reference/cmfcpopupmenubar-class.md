---
title: "CMFCPopupMenuBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenuBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCPopupMenuBar class
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
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
ms.openlocfilehash: 46f86035fecc16c45e01a1c70cdde610093d377b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar 클래스
팝업 메뉴에 포함된 메뉴 모음입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|즉시 창의 레이아웃을 다시 계산 합니다. (재정의 [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|지정 된 메뉴 리소스에서 팝업 메뉴 항목을 로드합니다.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|지연 된 팝업 메뉴 단추를 닫습니다.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|팝업 메뉴 단추에서 메뉴를 만듭니다.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|지정된 된 지점에 있는 도구 모음을 찾습니다.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|메뉴 단추 이미지의 크기를 나타냅니다.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|기본 메뉴 항목의 식별자를 반환합니다.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|가장 최근에 호출 메뉴 명령의 인덱스를 가져옵니다.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|팝업 메뉴 표시줄의 행 오프셋을 가져옵니다.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|지정 된 메뉴에서 팝업 메뉴 단추를 가져옵니다.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|팝업 메뉴 모음 드롭 다운 목록 모드 인지 여부를 나타냅니다.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|팝업 메뉴 모음 팔레트 모드 인지 여부를 나타냅니다.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|리본 패널 인지를 나타냅니다 ( `FALSE` 기본적으로).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|일반 모드에서 리본 패널 인지를 나타냅니다 ( `FALSE` 기본적으로).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|보관 된 메뉴를 로드합니다.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|팝업 메뉴 모음을 닫기 위한 지연 된 메뉴 단추를 복원 합니다.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|지정된 된 인덱스에서 도구 모음 단추 스타일을 설정합니다. (재정의 [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|팝업 메뉴 표시줄의 행 오프셋을 설정합니다.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|지정 된 지연 된 팝업 메뉴 단추에 대 한 타이머를 시작 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|응용 프로그램에 Windows XP 모양을 회색 세로 막대를 표시할지 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCPopupMenuBar` 은 같은 시간에 생성 한 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 와 그 안에 포함 된 합니다. `CMFCPopupMenuBar` 의 전체 클라이언트 영역에서 `CMFCPopupMenu` 개체입니다. 키보드 및 마우스 입력을 지원 합니다. 또한 입력이 있는 통신은 `CMFCPopupMenu` 및 최상위 프레임 창에 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 초기화 하는 방법을 한 `CMFCPopupMenuBar` 에서 개체는 `CMFCPopupMenu` 개체입니다. 이 코드 조각은의 일부인는 [그리기 클라이언트 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DrawClient #&7;](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpopupmenubar.h  
  
##  <a name="a-nameadjustsizeimmediatea--cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate  
 팝업 메뉴 표시줄 창의 레이아웃을 즉시 다시 계산 합니다. (재정의 [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)합니다.  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bRecalcLayout`  
 `TRUE`팝업 메뉴 표시줄 창;의 레이아웃을 자동으로 다시 계산 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namebuildorigitemsa--cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems  
 지정 된 메뉴 리소스에서 팝업 메뉴 항목을 로드합니다.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiMenuResID`  
 로드 하는 메뉴 리소스의 메뉴 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 성공 하는 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameclosedelayedsubmenua--cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu  
 연기 된 팝업 메뉴 단추를 닫습니다.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameexporttomenua--cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu  
 팝업 메뉴 단추에서 메뉴를 만듭니다.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 새로 만들기 메뉴에 대 한 핸들을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namefinddestintationtoolbara--cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar  
 지정된 된 지점에 있는 도구 모음을 찾습니다.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 화면에 있는 지점입니다.  
  
### <a name="return-value"></a>반환 값  
 핸들을 반환 도구 모음에 있는 정책은, therei 하나인 경우, 또는 `NULL` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcurrentmenuimagesizea--cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImageSize  
 메뉴 단추 이미지의 크기를 나타냅니다.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음에서 메뉴 단추 이미지의 크기를 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetdefaultmenuida--cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId  
 기본 메뉴 항목의 식별자를 반환합니다.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 팝업 메뉴 모음에서의 기본 메뉴 항목의 식별자를 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetlastcommandindexa--cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex  
 가장 최근에 호출 메뉴 명령의 인덱스를 가져옵니다.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>반환 값  
 호출 된 마지막 메뉴 명령의 인덱스를 반환 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetoffseta--cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>CMFCPopupMenuBar::GetOffset  
 팝업 메뉴 표시줄의 행 오프셋을 가져옵니다.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>반환 값  
 팝업 메뉴 표시줄의 행 오프셋을 반환합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여이 값은 설정 [CMFCPopupMenuBar::SetOffset](#setoffset)합니다.  
  
##  <a name="a-nameimportfrommenua--cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>CMFCPopupMenuBar::ImportFromMenu  
 지정 된 메뉴에서 팝업 메뉴 단추를 가져옵니다.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenu`  
 가져올 팝업 메뉴 단추 메뉴입니다.  
  
 [in] `bShowAllCommands`  
 `TRUE`메뉴에 있는 모든 명령을 가져올 경우 또는 `FALSE` 경우 거의 사용된 되지 않는 것에 숨겨져 있을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 메뉴 단추 메뉴에서 성공적으로 가져오면 되지 않은 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisdropdownlistmodea--cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode  
 팝업 메뉴 모음 드롭 다운 목록 모드 인지 여부를 나타냅니다.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 팝업 메뉴 모음 드롭 다운 목록 모드인 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameispalettemodea--cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode  
 팝업 메뉴 모음 팔레트 모드 인지 여부를 나타냅니다.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 팔레트 모드를 사용 하는 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 메뉴 모음 팔레트 모드로 설정 되 면 여러 열과 행 수가 제한에 메뉴 항목 표시 합니다.  
  
##  <a name="a-nameisribbonpanela--cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel  
 리본 패널 인지를 나타냅니다 ( `FALSE` 기본적으로).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `FALSE` 기본적으로이 아님을 나타내는 리본 패널입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisribbonpanelinregularmodea--cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 일반 모드에서 리본 패널 인지를 나타냅니다 ( `FALSE` 기본적으로).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `FALSE` 이 아님을 나타내는 리본 패널 일반 모드에서 기본적으로 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameloadfromhasha--cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash  
 보관 된 메뉴를 로드합니다.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenu`  
 로드 하 고 보관 된 메뉴에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 메뉴 성공적으로 로드 되는 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namembdisablesidebarinxpmodea--cmfcpopupmenubarmbdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Windows XP 모양의 되었을 경우, 응용 프로그램에 회색 세로 막대에 있는지 여부를 나타내는 부울 매개 변수입니다.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수로 설정 된 경우 `FALSE` 및 응용 프로그램에 Windows XP 모양을, 프레임 워크는 응용 프로그램에서 회색 세로 막대를 그립니다.  
  
 기본값은 `FALSE`입니다.  
  
##  <a name="a-namerestoredelayedsubmenua--cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu  
 팝업 메뉴 모음을 닫기 위한 지연 된 메뉴 단추를 복원 합니다.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetbuttonstylea--cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle  
 지정된 된 인덱스에서 도구 모음 단추 스타일을 설정합니다. (재정의 [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 스타일 설정 되어야 하는 도구 모음 단추의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `nStyle`  
 단추 스타일입니다. 참조 [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md) 목록은 사용 가능한 도구 모음 단추 스타일입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetoffseta--cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>CMFCPopupMenuBar::SetOffset  
 팝업 메뉴 표시줄의 행 오프셋을 설정합니다.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iOffset`  
 팝업 메뉴 모음 오프셋 되는 행의 수입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namestartpopupmenutimera--cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenuTimer  
 지정 된 지연 된 팝업 메뉴 단추에 대 한 타이머를 시작 합니다.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenuButton`  
 지연 타이머를 설정할 수 있는 메뉴 단추에 대 한 포인터입니다.  
  
 [in] `nDelayFactor`  
 지연 인수, 같지 하려면 최소한 하나, 표준 메뉴 지연 시간 (일반적으로&0;.5 초 사이 및&5; 초)를 곱하십시오.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md)

