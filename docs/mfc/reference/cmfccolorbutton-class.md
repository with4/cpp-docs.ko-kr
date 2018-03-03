---
title: "CMFCColorButton 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e49cec1c34af066d6f30cf70003252f28e2bb8dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton 클래스
`CMFCColorButton` 및 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 클래스는 색 선택 컨트롤을 구현 하는 데 함께 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|새 `CMFCColorButton` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|사용 하도록 설정 하 고 일반 색 단추 위에 배치 되는 "자동" 단추를 해제 합니다. (표준 시스템 자동 단추인 **자동**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|사용 하도록 설정 하 고 일반 색 단추 아래에 배치 되는 "기타" 단추를 해제 합니다. ("기타" 단추인 표준 시스템 **다른 색**.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|현재 자동 색을 검색 합니다.|  
|[CMFCColorButton::GetColor](#getcolor)|단추의 색을 검색 합니다.|  
|[CMFCColorButton::SetColor](#setcolor)|단추의 색을 설정합니다.|  
|[CMFCColorButton::SetColorName](#setcolorname)|색 이름을 설정합니다.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|색 선택 대화 상자에서 열 수를 설정합니다.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|색 선택 대화 상자에 표시 되는 문서별 색 목록을 지정 합니다.|  
|[CMFCColorButton::SetPalette](#setpalette)|표준 디스플레이 색의 팔레트를 지정합니다.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|텍스트 및 이미지 크기에 따라 단추 컨트롤의 크기를 변경 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Windows xp 시각적 스타일에 현재 색 단추가 표시 되는지 여부를 나타냅니다.|  
|[CMFCColorButton::OnDraw](#ondraw)|단추의 이미지 표시 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|단추의 테두리를 표시 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|단추 포커스가 있을 때 포커스 영역을 표시 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|색 선택 대화 상자를 표시 하려고 할 때 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|초기화는 `m_pPalette` 지정된 색상표 또는 기본 시스템 팔레트에 대 한 데이터 멤버를 보호 합니다.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|색 선택 대화 상자 팔레트에서 색을 선택할 때 프레임 워크에서 호출 됩니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|`m_bAltColorDlg`|부울입니다. 경우 `TRUE`, 프레임 워크가 표시는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 색 대화 상자는 *다른* 단추를 클릭할 경우 `FALSE`, 시스템 색 대화 상자. 기본값은 `TRUE`입니다. 자세한 내용은 참조 [CMFCColorButton::EnableOtherButton](#enableotherbutton)합니다.|  
|`m_bAutoSetFocus`|부울입니다. 경우 `TRUE`, 프레임 워크는 메뉴가 표시 되 면 또는 경우 색상 메뉴에 포커스를 설정 `FALSE`, 포커스 변경 되지 않습니다. 기본값은 `TRUE`입니다.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|색 단추에 대 한 사용자 지정 모드를 사용 하는지 여부를 나타냅니다.|  
|`m_Color`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다. 현재 선택한 색을 포함합니다.|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다. 현재 선택 된 기본 색을 포함합니다.|  
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md) 의 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다. 현재 사용할 수 있는 색이 포함 되어 있습니다.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) 의 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다. 현재 문서 색을 포함합니다.|  
|`m_nColumns`|정수입니다. 색 선택 메뉴에 색 눈금에 표시할 열의 수를 포함 합니다.|  
|`m_pPalette`|에 대 한 포인터는 [CPalette](../../mfc/reference/cpalette-class.md)합니다. 현재 색 선택 메뉴에서 사용할 수 있는 색이 포함 되어 있습니다.|  
|`m_pPopup`|에 대 한 포인터는 [CMFCColorPopupMenu 클래스](../../mfc/reference/cmfccolorpopupmenu-class.md) 개체입니다. 색 단추를 클릭할 때 표시 되는 색 선택 메뉴.|  
|`m_strAutoColorText`|문자열 색 선택 메뉴에 "자동" 단추의 레이블.|  
|`m_strDocColorsText`|문자열 문서 색을 표시 하는 색 선택 메뉴에 있는 단추의 레이블.|  
|`m_strOtherText`|문자열 색 선택 메뉴에 있는 "기타" 단추의 레이블.|  
  
## <a name="remarks"></a>설명  
 기본적으로는 `CMFCColorButton` 클래스를 색 선택 대화 상자를 여는 누름 단추 처럼 동작 합니다. 색 선택 대화 상자에는 작은 색 단추와 사용자 지정 색 선택기를 표시 하는 "기타" 단추가의 배열이 포함 됩니다. ("기타" 단추인 표준 시스템 **다른 색**.) 사용자가 새 색을 선택할 때의 `CMFCColorButton` 개체 변경 내용이 반영 하 고 선택한 색을 표시 합니다.  
  
 사용자 코드에서 직접 또는 사용 하 여 색 단추 컨트롤을 만들기는 **클래스 마법사** 도구 및 대화 상자 템플릿에 합니다. 색 단추 컨트롤을 직접 만들 경우 추가 `CMFCColorButton` 변수를 응용 프로그램 및 생성자 호출 및 `Create` 의 메서드는 `CMFCColorButton` 개체입니다. 사용 하는 경우는 **클래스 마법사**, 추가 `CButton` 응용 프로그램 변수에서 변수의 형식을 변경 합니다 `CButton` 를 `CMFCColorButton`합니다.  
  
 색 선택 대화 상자 ( [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md))에 표시 되는 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) 프레임 워크에서 호출 하는 경우 메서드는 `OnLButtonDown` 이벤트 처리기입니다. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) 사용자 지정 색 선택을 지원 하도록 메서드를 재정의할 수 있습니다.  
  
 `CMFCColorButton` 개체 알립니다 전송 하 여 색을 변경 하 고 있는 해당 부모는 `WM_COMMAND | BN_CLICKED` 알림입니다. 사용 하 여 부모는 [CMFCColorButton::GetColor](#getcolor) 현재 색을 검색 하는 메서드입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 색 단추에서 다양 한 메서드를 사용 하 여 구성 하는 방법의 `CMFCColorButton` 클래스입니다. 색 단추와 해당 열 수의 색을 설정 하 고 자동 및 기타 단추를 사용 하도록 설정 하는 메서드. 이 예제는의 일부는 [상태 표시줄 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton  
 새 `CMFCColorButton` 개체를 생성합니다.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton  
 설정 또는 색 선택 컨트롤의 "자동" 단추를 사용 하지 않도록 설정 하 고 자동 (기본) 색을 설정 합니다.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 자동 단추의 텍스트를 지정합니다.  
  
 [in] `colorAutomatic`  
 자동 버튼의 기본 색을 지정 하는 RGB 값입니다.  
  
 [in] `bEnable`  
 자동 단추 사용 되는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton  
 일반 색 단추 아래에 표시 "기타" 단추를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 단추의 텍스트를 지정합니다.  
  
 [in] `bAltColorDlg`  
 지정 여부는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자 또는 시스템 색 대화 상자 단추를 클릭할 때 열리는 합니다.  
  
 [in] `bEnable`  
 "기타" 단추 사용 되는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 색 대화 상자를 표시 하려면 "기타" 단추를 클릭 합니다. 경우는 *bAltColorDlg* 매개 변수는 `TRUE`, [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md) 표시 됩니다. 그렇지 않으면, 시스템 색 대화 상자 표시 됩니다.  
  
##  <a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor  
 현재 자동 (기본) 색을 검색 합니다.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 자동 색을 나타내는 RGB 값입니다.  
  
### <a name="remarks"></a>설명  
 현재 자동 색으로 설정 됩니다는 [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) 메서드.  
  
##  <a name="getcolor"></a>CMFCColorButton::GetColor  
 현재 선택 된 색을 검색 합니다.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme  
 Windows xp 시각적 스타일에 현재 색 단추가 표시 되는지 여부를 나타냅니다.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`비주얼 스타일은 지원 및 Windows XP;의 비주얼 스타일에 현재 색 단추가 표시 되는지를 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode  
 사용자 지정 모드를 색 단추를 설정합니다.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>설명  
 설정 하 여 색 단추는 사용자 지정 대화 상자 페이지를 추가 합니다 (또는 사용자가 사용자 지정 하는 동안 다른 색 옵션을 선택 하도록 허용) 해야 할 경우 활성화 단추는 `m_bEnabledInCustomizeMode` 멤버 `TRUE`합니다. 기본적으로이 멤버 설정 `FALSE`합니다.  
  
##  <a name="ondraw"></a>CMFCColorButton::OnDraw  
 단추의 이미지를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추의 이미지를 렌더링 하는 데 사용 되는 장치 컨텍스트를 가리킵니다.  
  
 [in] `rect`  
 단추 경계를 지정 하는 사각형입니다.  
  
 [in] `uiState`  
 단추의 표시 상태를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 렌더링 프로세스를 사용자 지정 하려면이 메서드를 재정의 합니다.  
  
##  <a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder  
 단추의 테두리를 표시 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 테두리를 그리는 데 사용 되는 장치 컨텍스트를 가리킵니다.  
  
 [in] `rectClient`  
 지정 된 장치 컨텍스트의 사각형의는 `pDC` 을 그릴 수 있도록 단추 경계를 정의 하는 매개 변수입니다.  
  
 [in] `uiState`  
 단추의 표시 상태를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 색 단추의 테두리 모양을 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect  
 단추에 포커스가 있을 때 포커스 영역을 표시 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 포커스 사각형을 그리는 데 사용 되는 장치 컨텍스트를 가리킵니다.  
  
 [in] `rectClient`  
 로 지정 된 장치 컨텍스트의 사각형은 `pDC` 단추 경계를 정의 하는 매개 변수입니다.  
  
### <a name="remarks"></a>설명  
 포커스 사각형의 모양을 사용자 지정 하려면이 메서드를 재정의 합니다.  
  
##  <a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup  
 팝업 색 막대에 표시 되기 전에 호출 됩니다.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette  
 초기화는 `m_pPalette` 지정된 색상표 또는 기본 시스템 팔레트에 대 한 데이터 멤버를 보호 합니다.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pPal`|논리 팔레트에 대 한 포인터 또는 `NULL`합니다. 경우 `NULL`, 기본 시스템 색상표가 사용 됩니다.|  
  
##  <a name="setcolor"></a>CMFCColorButton::SetColor  
 단추의 색을 지정합니다.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 RGB 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcolorname"></a>CMFCColorButton::SetColorName  
 색의 이름을 지정합니다.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 색의 RGB 값입니다.  
  
 [in] `strName`  
 색의 이름입니다.  
  
### <a name="remarks"></a>설명  
 색 이름 중 목록은 응용 프로그램당 공통 됩니다. 이 메서드 매개 변수를 이동 하는 따라서 [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)합니다.  
  
##  <a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber  
 사용자의 색 선택 프로세스 중 사용자에 게 제공 되는 색의 테이블에 표시 되는 열 수를 정의 합니다.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nColumns`  
 열의 수를 지정합니다.  
  
### <a name="remarks"></a>설명  
 사용자는 미리 정의 된 색의 표를 표시 하는 팝업 색 막대에서 색을 선택할 수 있습니다. 이 메서드를 사용 하 여 테이블의 열 수를 정의 합니다.  
  
##  <a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors  
 색 및 해당 집합의 이름 집합을 지정합니다. 사용 하 여 일련의 색이 표시는 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 개체입니다.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 문서 색의 집합으로 표시할 레이블을 지정 합니다.  
  
 [in] `lstColors`  
 RGB 값 목록에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 A `CMFCColorButton` 개체에 전송 되는 RGB 값의 목록을 유지 관리는 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 개체입니다. 이러한 색 레이블을 지정 하는 특별 한 섹션에 표시 됩니다 색 막대를 표시할 때는 `lpszLabel` 매개 변수입니다.  
  
##  <a name="setpalette"></a>CMFCColorButton::SetPalette  
 팝업 색 막대에 표시할 표준 색을 지정 합니다.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pPalette`  
 색상표에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="sizetocontent"></a>CMFCColorButton::SizeToContent  
 단추 컨트롤의 텍스트 및 이미지에 맞게 크기가 조정 됩니다.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bCalcOnly`  
 0이 아니면 단추 컨트롤의 새 크기 계산 되지만 실제 크기는 변경 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 A `CSize` 새 단추 컨트롤 크기를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="updatecolor"></a>CMFCColorButton::UpdateColor  
 사용자가 색 단추를 클릭할 때 표시 하는 색 막대에서 색을 선택할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 사용자가 선택한 색입니다.  
  
### <a name="remarks"></a>설명  
 `UpdateColor` 함수 현재 선택 된 단추의 색을 변경 하 고 해당 부모 전송 하 여 한 `WM_COMMAND` 메시지는 `BN_CLICKED` 표준 알림. 사용 하 여는 [CMFCColorButton::GetColor](#getcolor) 선택한 색을 검색 하는 메서드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette 클래스](../../mfc/reference/cpalette-class.md)   
 [CArray 클래스](../../mfc/reference/carray-class.md)   
 [CList 클래스](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)
