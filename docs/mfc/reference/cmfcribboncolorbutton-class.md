---
title: "CMFCRibbonColorButton 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8da5a7a05f1765fea840c579c91ddd9b3ef672b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton 클래스
`CMFCRibbonColorButton` 클래스는 리본 표시줄에 추가할 수 있는 색 단추를 구현합니다. 리본 색 단추는 하나 이상의 색상표가 포함된 드롭다운 메뉴를 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|일반 색 영역에 색 그룹을 추가합니다.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|**자동** 단추를 사용할지 여부를 지정합니다.|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|**기타** 단추를 사용하도록 설정합니다.|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|현재 선택된 색을 반환합니다.|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|색 막대에 표시되는 색 요소의 크기를 반환합니다.|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|팝업 색상표에서 현재 선택된 요소의 색을 반환합니다.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|일반 색 영역에서 모든 색 그룹을 제거합니다.|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|일반 색 영역에서 색을 선택합니다.|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|색 막대에 표시되는 모든 색 요소의 크기를 설정합니다.|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|문서 색 영역에 표시할 RGB 값의 목록을 지정합니다.|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>설명  
 리본 색 단추는 사용자가 누를 때 색 막대를 표시합니다. 기본적으로 이 색 막대에는 일반 색 영역이라는 색 선택 색상표가 포함되어 있습니다. 필요에 따라 색 막대에 기본 색을 선택할 수 있는 **자동** 단추와 추가 색이 포함된 팝업 색상표를 표시하는 **기타** 단추가 표시될 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `CMFCRibbonColorButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 `CMFCRibbonColorButton` 개체 생성, 큰 이미지 설정, **자동** 단추 사용, **기타** 단추 사용, 열 수 설정, 색 막대에 표시되는 모든 색 요소의 크기 설정, 일반 색 영역에 색 그룹 추가, 문서 색 영역에 표시할 RGB 값 목록 지정 등을 수행하는 방법을 보여 줍니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>CMFCRibbonColorButton::AddColorsGroup  
 일반 색 영역에 색 그룹을 추가합니다.  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 그룹 이름입니다.  
  
 [in] `lstColors`  
 색 목록입니다.  
  
 [in] `bContiguousColumns`  
 색 항목 그룹에 표시 되는 방식을 제어 합니다. 경우 `TRUE`, 해당 색 항목 세로 간격 없이 그려집니다. 경우 `FALSE`, 해당 색 항목 세로 간격으로 그려집니다.  
  
### <a name="remarks"></a>설명  
 이 팝업 색으로 기능을 사용 하 여 색의 여러 그룹을 표시 합니다. 색이 그룹에 표시 되는 방식을 제어할 수 있습니다.  
  
##  <a name="cmfcribboncolorbutton"></a>CMFCRibbonColorButton::CMFCRibbonColorButton  
 `CMFCRibbonColorButton` 개체를 생성합니다.  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 단추를 클릭할 때 실행할 명령의 명령 ID를 지정 합니다.  
  
 [in] `lpszText`  
 단추에 표시할 텍스트를 지정 합니다.  
  
 [in] `nSmallImageIndex`  
 단추에 표시할 작은 이미지의 0부터 시작 하는 인덱스입니다.  
  
 [in] `color`  
 (기본값은 검정) 단추의 색입니다.  
  
 [in] `bSimpleButtonLook`  
 경우 `TRUE`, 단추 간단한 사각형으로 그려집니다.  
  
 [in] `nLargeImageIndex`  
 큰 단추에 표시할 이미지의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="enableautomaticbutton"></a>CMFCRibbonColorButton::EnableAutomaticButton  
 **자동** 단추를 사용할지 여부를 지정합니다.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 에 대 한 레이블은 **자동** 단추입니다.  
  
 [in] `colorAutomatic`  
 RGB 값을 지정 하는 **자동** 버튼의 기본 색입니다.  
  
 [in] `bEnable`  
 `TRUE`경우는 **자동** 단추를 사용할 수 있습니다. `FALSE` 해제 된 경우.  
  
 [in] `lpszToolTip`  
 도구 설명에서 **자동** 단추입니다.  
  
 [in] `bOnTop`  
 지정 여부는 **자동** 색상표 전에 맨 위에 있는 단추는 합니다.  
  
 [in] `bDrawBorder`  
 `TRUE`이면 응용 프로그램 리본 색 단추 색 막대 주위에 테두리를 가져옵니다. 색 막대는 현재 선택한 색을 표시합니다. `FALSE`응용 프로그램에 테두리를 그리지 않습니다 하는 경우  
  
##  <a name="enableotherbutton"></a>CMFCRibbonColorButton::EnableOtherButton  
 **기타** 단추를 사용하도록 설정합니다.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszLabel`  
 단추의 레이블입니다.  
  
 `lpszToolTip`  
 에 대 한 도구 설명 텍스트는 **다른** 단추입니다.  
  
### <a name="remarks"></a>설명  
 **다른** 단추가 색의 그룹 아래에 표시 된 단추입니다. 사용자가 클릭할 때는 **다른** 단추, 색 대화 상자를 표시 합니다.  
  
##  <a name="getautomaticcolor"></a>CMFCRibbonColorButton::GetAutomaticColor  
 현재 자동 단추의 색을 검색합니다.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 자동 단추의 색을 나타내는 RGB 색상 값입니다.  
  
### <a name="remarks"></a>설명  
 자동 단추의 색으로 설정 됩니다는 `colorAutomatic` 에 전달 된 매개 변수는 `CMFCRibbonColorButton::EnableAutomaticButton` 메서드.  
  
##  <a name="getcolor"></a>CMFCRibbonColorButton::GetColor  
 현재 선택된 색을 반환합니다.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추를 클릭 하면 선택한 색입니다.  
  
##  <a name="getcolorboxsize"></a>CMFCRibbonColorButton::GetColorBoxSize  
 색 막대에 표시되는 색 요소의 크기를 반환합니다.  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 드롭 다운 색상표의 색 단추의 크기입니다.  
  
##  <a name="getcolumns"></a>CMFCRibbonColorButton::GetColumns  
 리본 색 단추는 갤러리 디스플레이의 행의 항목 수를 가져옵니다.  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>반환 값  
 각 행의 아이콘 수를 반환합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="gethighlightedcolor"></a>CMFCRibbonColorButton::GetHighlightedColor  
 팝업 색상표에서 현재 선택 된 요소의 색을 반환합니다.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 팝업 색상표에서 현재 선택 된 요소의 색입니다.  
  
##  <a name="removeallcolorgroups"></a>CMFCRibbonColorButton::RemoveAllColorGroups  
 일반 색 영역에서 모든 색 그룹을 제거합니다.  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>CMFCRibbonColorButton::SetColor  
 일반 색 영역에서 색을 선택합니다.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 설정 하는 색입니다.  
  
##  <a name="setcolorboxsize"></a>CMFCRibbonColorButton::SetColorBoxSize  
 색 막대에 표시되는 모든 색 요소의 크기를 설정합니다.  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `sizeBox`  
 색상표의 색 단추의 새 크기입니다.  
  
##  <a name="setcolorname"></a>CMFCRibbonColorButton::SetColorName  
 지정 된 색에 대 한 새 이름을 설정합니다.  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 색의 RGB 값입니다.  
  
 [in] `strName`  
 지정된 된 색에 대 한 새 이름입니다.  
  
### <a name="remarks"></a>설명  
 호출 하므로 `CMFCColorBar::SetColorName`,이 메서드는 모든 페이지에서 지정된 된 색의 이름 변경 `CMFCColorBar` 응용 프로그램의 개체입니다.  
  
##  <a name="setcolumns"></a>CMFCRibbonColorButton::SetColumns  
 사용자의 색 선택 프로세스 중 사용자에 게 제공 되는 색의 테이블에 표시 되는 열의 수를 설정 합니다.  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nColumns`  
 각 행에 표시 하려면 색 아이콘의 수입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setdocumentcolors"></a>CMFCRibbonColorButton::SetDocumentColors  
 문서 색 영역에 표시할 RGB 값의 목록을 지정합니다.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 문서 색으로 표시 될 텍스트입니다.  
  
 [in] `lstColors`  
 RGB 값 목록에 대 한 참조입니다.  
  
##  <a name="setpalette"></a>CMFCRibbonColorButton::SetPalette  
 색 단추를 표시 하는 색 테이블에 표시할 표준 색을 지정 합니다.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pPalette`  
 색상표에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="updatecolor"></a>CMFCRibbonColorButton::UpdateColor  
 색 단추를 클릭할 때 표시 되는 색상표에서 색을 선택할 때 프레임 워크에서 호출 됩니다.  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 사용자가 선택한 색입니다.  
  
### <a name="remarks"></a>설명  
 `CMFCRibbonColorButton::UpdateColor` 메서드 현재 선택 된 단추의 색을 변경 하 고 전송 하 여 해당 부모에 게 알리는 `WM_COMMAND` 메시지는 `BN_CLICKED` 표준 알림. 사용 하 여는 [CMFCRibbonColorButton::GetColor](#getcolor) 선택한 색을 검색 하는 메서드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery 클래스](../../mfc/reference/cmfcribbongallery-class.md)
