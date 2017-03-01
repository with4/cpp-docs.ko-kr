---
title: "CMFCBaseVisualManager 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- CMFCBaseVisualManager.~CMFCBaseVisualManager
- ~CMFCBaseVisualManager
- CMFCBaseVisualManager::~CMFCBaseVisualManager
dev_langs:
- C++
helpviewer_keywords:
- ~CMFCBaseVisualManager destructor
- CMFCBaseVisualManager class, destructor
- CMFCBaseVisualManager class
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7c726fe71b7dcf26353fe0ce3a6b383eb5b578b9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager 클래스
파생된 비주얼 관리자와 Windows 테마 API 사이의 계층입니다.  
  
 `CMFCBaseVisualManager`사용 가능한 경우 UxTheme.dll, 로드 하 고 Windows 테마 API 메서드에 대 한 액세스를 관리 합니다.  
  
 이 클래스는 내부적 으로만 사용 하는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` 개체를 생성하고 초기화합니다.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|현재 Windows 테마를 사용 하 여 확인란 컨트롤을 그립니다.|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|현재 Windows 테마를 사용 하 여 콤보 상자 테두리를 그립니다.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|현재 Windows 테마를 사용 하 여 콤보 상자 드롭다운 단추를 그립니다.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|현재 Windows 테마를 사용 하 여 푸시 단추를 그립니다.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|현재 Windows 테마를 사용 하 여 라디오 단추 컨트롤을 그립니다.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|상태 표시줄 컨트롤에 진행률 표시줄을 그립니다 ( [CMFCStatusBar 클래스](../../mfc/reference/cmfcstatusbar-class.md))은 현재 Windows 테마를 사용 합니다.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Rebar 컨트롤의 배경을 현재 Windows 테마를 사용 하 여 채웁니다.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|현재 Windows 테마를 가져옵니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|호출 `CloseThemeData` 에서 얻은 모든 핸들에 대 한 `UpdateSystemColors`합니다.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|호출 `OpenThemeData` 다양 한 컨트롤 그리기에 대 한 핸들을 가져오는 데: 창, 도구 모음, 단추 및 등입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스의 개체를 직접 인스턴스화할 필요가 없습니다.  
  
 모든 비주얼 관리자에 대 한 기본 클래스는 이기 때문에 호출 [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)포인터에는 현재 비주얼 관리자를 구하여 액세스에 대 한 메서드 `CMFCBaseVisualManager` 해당 포인터를 사용 하 여 합니다. 그러나 현재 Windows 테마를 사용 하 여 컨트롤을 표시 해야 할 경우 그 사용 하는 것은 `CMFCVisualManagerWindows` 인터페이스입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxvisualmanager.h  
  
##  <a name="a-namecleanupthemesa--cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a>CMFCBaseVisualManager::CleanUpThemes  
 호출 `CloseThemeData` 에서 얻은 모든 핸들에 대 한 `UpdateSystemColors`합니다.  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>주의  
 내부 전용입니다.  
  
##  <a name="a-namecmfcbasevisualmanagera--cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a>CMFCBaseVisualManager::CMFCBaseVisualManager  
 `CMFCBaseVisualManager` 개체를 생성하고 초기화합니다.  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="a-namedrawcheckboxa--cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a>CMFCBaseVisualManager::DrawCheckBox  
 현재 Windows 테마를 사용 하 여 확인란 컨트롤을 그립니다.  
  
```  
virtual BOOL DrawCheckBox(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    int nState,   
    BOOL bEnabled,   
    BOOL bPressed);

);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대 한 포인터  
  
 [in] `rect`  
 확인란의 경계 사각형입니다.  
  
 [in] `bHighlighted`  
 확인란을 강조 표시 되어 있는지 여부를 지정 합니다.  
  
 [in] `nState`  
 0 선택 된 표준에 대 한 옵션을 선택 취소 1에 대 한  
  
 보통의 혼합&2;입니다.  
  
 [in] `bEnabled`  
 확인란 사용 되는지 여부를 지정 합니다.  
  
 [in] `bPressed`  
 확인란을 눌렀는지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 값 `nState` 다음 확인란 스타일에 해당 합니다.  
  
|nState|확인란 스타일|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="a-namedrawcombobordera--cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder  
 현재 Windows 테마를 사용 하 여 콤보 상자 테두리를 그립니다.  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rect`  
 콤보 상자 테두리의 경계 사각형입니다.  
  
 [in] `bDisabled`  
 콤보 상자 테두리 되지 않는지 여부를 지정 합니다.  
  
 [in] `bIsDropped`  
 테두리 콤보 상자를 삭제할지 여부를 지정 합니다.  
  
 [in] `bIsHighlighted`  
 콤보 상자 테두리에 강조 표시 되어 있는지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namedrawcombodropbuttona--cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton  
 현재 Windows 테마를 사용 하 여 콤보 상자 드롭다운 단추를 그립니다.  
  
```  
virtual BOOL DrawComboDropButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pDC`|장치 컨텍스트에 대한 포인터입니다.|  
|[in] `rect`|콤보 상자 드롭다운 단추의 경계 사각형입니다.|  
|[in] `bDisabled`|콤보 상자 드롭다운 단추 되지 않는지 여부를 지정 합니다.|  
|[in] `bIsDropped`|콤보 상자 드롭다운 단추를 삭제할지 여부를 지정 합니다.|  
|[in] `bIsHighlighted`|콤보 상자 드롭다운 단추 강조 표시 되어 있는지 여부를 지정 합니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namedrawpushbuttona--cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a>CMFCBaseVisualManager::DrawPushButton  
 현재 Windows 테마를 사용 하 여 푸시 단추를 그립니다.  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rect`  
 푸시 단추의 경계 사각형입니다.  
  
 [in] `pButton`  
 에 대 한 포인터는 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md) 그릴 개체입니다.  
  
 [in] `uiState`  
 무시됩니다. 상태에서 가져온 것 `pButton`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namedrawradiobuttona--cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a>CMFCBaseVisualManager::DrawRadioButton  
 현재 Windows 테마를 사용 하 여 라디오 단추 컨트롤을 그립니다.  
  
```  
virtual BOOL DrawRadioButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    BOOL bChecked,   
    BOOL bEnabled,   
    BOOL bPressed);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rect`  
 라디오 단추의 경계 사각형입니다.  
  
 [in] `bHighlighted`  
 라디오 단추가 강조 표시 하는지 여부를 지정 합니다.  
  
 [in] `bChecked`  
 라디오 단추가 선택 되었는지 여부를 지정 합니다.  
  
 [in] `bEnabled`  
 라디오 단추를 사용할 수 있는지 여부를 지정 합니다.  
  
 [in] `bPressed`  
 라디오 단추를 눌렀는지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namedrawstatusbarprogressa--cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a>CMFCBaseVisualManager::DrawStatusBarProgress  
 상태 표시줄 컨트롤에 진행률 표시줄을 그립니다 ( [CMFCStatusBar 클래스](../../mfc/reference/cmfcstatusbar-class.md))은 현재 Windows 테마를 사용 합니다.  
  
```  
virtual BOOL DrawStatusBarProgress(
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
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `pStatusBar`  
 상태 표시줄에 대 한 포인터입니다. 이 값은 무시됩니다.  
  
 [in] `rectProgress`  
 진행률 표시줄의 경계 사각형 `pDC` 좌표입니다.  
  
 [in] `nProgressTotal`  
 총 진행률 값입니다.  
  
 [in] `nProgressCurr`  
 현재 진행률 값입니다.  
  
 [in] `clrBar`  
 시작 색입니다. `CMFCBaseVisualManager`이 무시합니다. 파생된 클래스에 색 그라데이션을 사용할 수 있습니다.  
  
 [in] `clrProgressBarDest`  
 마지막 색입니다. `CMFCBaseVisualManager`이 무시합니다. 파생된 클래스에 색 그라데이션을 사용할 수 있습니다.  
  
 [in] `clrProgressText`  
 진행률 텍스트 색입니다. `CMFCBaseVisualManager`이 무시합니다. 텍스트 색 정의한 `afxGlobalData.clrBtnText`합니다.  
  
 [in] `bProgressText`  
 진행률 텍스트를 표시할지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namefillrebarpanea--cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a>CMFCBaseVisualManager::FillReBarPane  
 Rebar 컨트롤의 배경을 현재 Windows 테마를 사용 하 여 채웁니다.  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `pBar`  
 해당 배경 그리 창에 대 한 포인터입니다.  
  
 [in] `rectClient`  
 채울 영역의 경계 사각형입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마 API를 사용 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namegetstandardwindowsthemea--cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme  
 현재 Windows 테마를 가져옵니다.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 Windows 테마 색입니다. 다음 열거형된 값 중 하나일 수 있습니다.  
  
- `WinXpTheme_None`-는 테마를 사용할 수 없음.  
  
- `WinXpTheme_NonStandard`-(테마 선택 되어 있지만 아래 목록에서 없음을 의미) 비표준 테마를 선택 합니다.  
  
- `WinXpTheme_Blue`-파란색 테마 (Luna).  
  
- `WinXpTheme_Olive`-올리브색 테마입니다.  
  
- `WinXpTheme_Silver`-silver 테마입니다.  
  
##  <a name="a-nameupdatesystemcolorsa--cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a>CMFCBaseVisualManager::UpdateSystemColors  
 호출 `OpenThemeData` 다양 한 컨트롤 그리기에 대 한 핸들을 가져오는 데: 창, 도구 모음, 단추 및 등입니다.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>주의  
 내부 전용입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

