---
title: "CMFCColorBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorBar class
- CMFCColorBar::m_ColorAutomatic data member
- CMFCColorBar::m_bInternal data member
- CMFCColorBar::m_bIsEnabled data member
- CMFCColorBar::m_nNumColumnsVert data member
- CMFCColorBar::m_nVertMargin data member
- CMFCColorBar::m_strDocColors data member
- CMFCColorBar::m_BoxSize data member
- CMFCColorBar::m_pParentBtn data member
- CMFCColorBar::m_bIsTearOff data member
- CMFCColorBar::m_nHorzOffset data member
- CMFCColorBar::m_pParentRibbonBtn data member
- CMFCColorBar::m_nNumRowsHorz data member
- CMFCColorBar::m_bStdColorDlg data member
- CMFCColorBar::m_strAutoColor data member
- CMFCColorBar::m_ColorNames data member
- CMFCColorBar::m_strOtherColor data member
- CMFCColorBar::m_lstDocColors data member
- CMFCColorBar::m_pWndPropList data member
- CMFCColorBar::m_ColorSelected data member
- CMFCColorBar::m_nCommandID data member
- CMFCColorBar::m_nHorzMargin data member
- CMFCColorBar::m_nRowHeight data member
- CMFCColorBar::m_Palette data member
- CMFCColorBar::m_colors data member
- CMFCColorBar::m_nVertOffset data member
- CMFCColorBar::m_nNumColumns data member
- CMFCColorBar::m_bShowDocColorsWhenDocked data member
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
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
ms.openlocfilehash: bf4d431a3f3237587dc9f86be91f11b9b5016fe2
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbar-class"></a>CMFCColorBar 클래스
`CMFCColorBar` 클래스에는 문서 또는 응용 프로그램에서 색을 선택할 수 있는 도킹 컨트롤 막대를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|`CMFCColorBar` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|색 막대 컨트롤의 단추에 포함 하는 데 필요한 한 다음 해당 단추의 위치를 조정 하는 세로 및 가로 여백을 계산 합니다.|  
|[CMFCColorBar::CreateControl](#createcontrol)|색 막대 컨트롤 창을 만듭니다에 연결 되는 `CMFCColorBar` 개체 지정된 된 색상표를 포함 하는 컨트롤의 크기를 조정 합니다.|  
|[CMFCColorBar::Create](#create)|색 막대 컨트롤 창을 만들고이에 연결 된 `CMFCColorBar` 개체입니다.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|표시 하거나 자동 단추를 숨깁니다.|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|사용 하거나 더 많은 색을 선택할 수 있도록 하는 대화 상자를 표시 하지 않도록 설정 합니다.|  
|[CMFCColorBar::GetColor](#getcolor)|현재 선택 된 색을 검색 합니다.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|현재 색 막대 컨트롤의 명령 ID를 검색합니다.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|색을 색 단추에는 포커스가 있는지 나타내는 검색 즉, 단추는 *핫*합니다.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|클라이언트 영역 경계 왼쪽 또는 오른쪽 색 셀 사이의 공간 가로 여백를 검색 합니다.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|세로 여백, 위쪽 또는 아래쪽 색 셀과 클라이언트 영역 경계 사이의 공간을 검색 합니다.|  
|[CMFCColorBar::IsTearOff](#istearoff)|현재 색 막대 도킹 가능 여부를 나타냅니다.|  
|[CMFCColorBar::SetColor](#setcolor)|현재 선택 된 색을 설정 합니다.|  
|[CMFCColorBar::SetColorName](#setcolorname)|지정 된 색에 대 한 새 이름을 설정합니다.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|색 막대 컨트롤에 대 한 새 명령 ID를 설정합니다.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|현재 문서에 사용 되는 색 목록을 설정 합니다.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|왼쪽 또는 오른쪽 색 셀과 클라이언트 영역 경계 사이의 공간이 가로 여백을 설정 합니다.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|세로 여백, 위쪽 또는 아래쪽 색 셀과 클라이언트 영역 경계 사이의 공간을 설정 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|색 컨트롤의 단추에는 색 막대의 위치를 조정합니다.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|색 단추의 텍스트 레이블을 변경할 수 있는지 여부를 나타냅니다.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|사용자 지정 프로세스 중 색 막대 컨트롤 개체 도구 모음 목록에 표시 될 수 있는지 여부를 나타냅니다.|  
|[CMFCColorBar::CalcSize](#calcsize)|레이아웃 계산 프로세스의 일환으로 프레임 워크에 의해 호출 됩니다.|  
|[CMFCColorBar::CreatePalette](#createpalette)|색의 지정된 된 배열에 색 팔레트를 초기화 합니다.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|색 막대 컨트롤의 모눈의 행과 열 개수를 계산 합니다.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|현재 색 막대와 같은 기타 사용자 인터페이스 요소를 표시 하는 데 필요한 추가 높이 계산는 **다른** 단추, 문서 색 크며 등등 합니다.|  
|[CMFCColorBar::InitColors](#initcolors)|지정 된 색상표 또는 시스템 기본 색상표의 색과 색의 배열을 초기화합니다.|  
|[CMFCColorBar::OnKey](#onkey)|사용자가 키보드 단추를 누를 때 프레임 워크에서 호출 합니다.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|팝업 컨트롤의 계층 구조를 닫으려면 프레임 워크에 의해 호출 됩니다.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|프레임 워크는 항목 표시 되기 전에 색 막대 컨트롤의 사용자 인터페이스 항목을 사용할지에 의해 호출 됩니다.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|색 대화 상자를 엽니다.|  
|[CMFCColorBar::Rebuild](#rebuild)|색 막대 컨트롤을 완전히 다시 그립니다.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|현재 색 막대 컨트롤의 부모 단추의 팔레트를 지정된 된 장치 컨텍스트에의 논리 색상표를 설정합니다.|  
|[CMFCColorBar::SetPropList](#setproplist)|설정의 `m_pWndPropList` 속성 표 컨트롤에 지정된 된 포인터에 대 한 데이터 멤버를 보호 합니다.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|상태 표시줄에서 메시지 줄을 업데이트 하려면 색 막대 컨트롤을 소유 하는 프레임 창을 요청 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|`m_bInternal`|마우스 이벤트 처리 되는지 여부를 결정 하는 부울 필드입니다. 이 필드에이 때 마우스 이벤트를 처리 하는 일반적으로 `TRUE` 사용자 지정 모드는 `FALSE`합니다.|  
|`m_bIsEnabled`|컨트롤을 사용할 수 있는지 여부를 나타내는 부울입니다.|  
|`m_bIsTearOff`|색 막대 컨트롤 도킹을 지원 하는지 여부를 나타내는 부울입니다.|  
|`m_BoxSize`|A [CSize](../../atl-mfc-shared/reference/csize-class.md) 색 막대 표의 셀의 크기를 지정 하는 개체입니다.|  
|`m_bShowDocColorsWhenDocked`|색 막대 도킹 한 경우 문서 색 표시 여부를 나타내는 부울입니다. 자세한 내용은 참조 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)합니다.|  
|`m_bStdColorDlg`|표준 시스템 색 대화 상자를 표시할지 여부를 나타내는 부울 값 또는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자입니다. 자세한 내용은 참조 [CMFCColorBar::EnableOtherButton](#enableotherbutton)합니다.|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 현재 자동 색을 저장 하는 합니다. 자세한 내용은 참조 [CMFCColorBar::EnableOtherButton](#enableotherbutton)합니다.|  
|`m_ColorNames`|[CMap](../../mfc/reference/cmap-class.md) RGB 집합에 연결 하는 개체 이름으로 색입니다.|  
|`m_colors`|A [CArray](../../mfc/reference/carray-class.md) 의 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 색 막대 컨트롤에 표시 되는 색상을 포함 하는 값입니다.|  
|`m_ColorSelected`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 사용자가 색 막대 컨트롤에서 현재 선택한 색 값입니다.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) 의 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 문서에서 현재 사용 되는 색상을 포함 하는 값입니다.|  
|`m_nCommandID`|색 단추의 명령 ID는 부호 없는 정수입니다.|  
|`m_nHorzMargin`|정수 색상표가 있는 색 단추 사이의 가로 여백입니다.|  
|`m_nHorzOffset`|정수 색 단추의 가운데에 가로 오프셋입니다. 이 값은 단추 텍스트 또는 색 외에도 이미지를 표시 하는 경우에 중요 합니다.|  
|`m_nNumColumns`|정수 색의 색상 막대 컨트롤 표의 열 수입니다.|  
|`m_nNumColumnsVert`|정수 색의 세로 방향의 표의 열 수입니다.|  
|`m_nNumRowsHorz`|정수 색의 가로 방향의 표의 열 수입니다.|  
|`m_nRowHeight`|정수 색상표가 색 단추는 행의 높이입니다.|  
|`m_nVertMargin`|색 눈금에서 색 단추 사이 여백이 있는 정수입니다.|  
|`m_nVertOffset`|정수 색 단추의 가운데에 세로 오프셋입니다. 이 값은 단추 텍스트 또는 색 외에도 이미지를 표시 하는 경우에 중요 합니다.|  
|`m_Palette`|A [CPalette](../../mfc/reference/cpalette-class.md) 색 막대 컨트롤에 사용 되는 색입니다.|  
|`m_pParentBtn`|에 대 한 포인터는 [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) 개체는 현재 단추의 부모입니다. 이 값은 중요 한 색 단추는 도구 모음 컨트롤 계층 또는 색 속성 표 컨트롤입니다.|  
|`m_pParentRibbonBtn`|에 대 한 포인터는 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) 개체를 리본 메뉴에는 현재 단추의 부모 단추입니다. 이 값은 중요 한 색 단추는 도구 모음 컨트롤 계층 또는 색 속성 표 컨트롤입니다.|  
|`m_pWndPropList`|에 대 한 포인터는 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체입니다.|  
|`m_strAutoColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 에 표시 되는 텍스트 즉는 **자동** 단추입니다. 자세한 내용은 참조 [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)합니다.|  
|`m_strDocColors`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 문서 색 단추에 표시 되는 텍스트입니다. 자세한 내용은 참조 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)합니다.|  
|`m_strOtherColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 에 표시 되는 텍스트 즉는 *다른* 단추입니다. 자세한 내용은 참조 [CMFCColorBar::EnableOtherButton](#enableotherbutton)합니다.|  
  
## <a name="remarks"></a>주의  
 일반적으로 만들지 않는 한 `CMFCColorBar` 개체에 직접. 대신,는 [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md) (메뉴 및 도구 모음에 사용) 또는 [CMFCColorButton 클래스](../../mfc/reference/cmfccolorbutton-class.md) 만듭니다는 `CMFCColorBar` 개체입니다.  
  
 `CMFCColorBar` 클래스는 다음과 같은 기능을 제공 합니다.  
  
-   문서 색 목록이 자동으로 조정 합니다.  
  
-   저장 한 문서 상태와 함께 해당 상태를 복원 합니다.  
  
-   "자동" 단추를 관리합니다.  
  
-   사용 하는 [CMFCColorPickerCtrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md) 컨트롤을 사용자 지정 색을 선택 합니다.  
  
-   "분리" 상태를 지원 (사용 하 여 만들어진 경우는 [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 통합 하는 `CMFCColorBar` 응용 프로그램에 기능을 합니다.  
  
1.  일반 메뉴 단추를 만드는 예를 들어 ID_CHAR_COLOR ID를 할당 합니다.  
  
2.  프레임 창 클래스에서 재정의 된 [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) 메서드와 바꾸기 일반 메뉴와 단추는 [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md) 개체 (호출 하 여 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  모든 스타일을 설정 하 고 사용 하도록 설정 하거나의 기능을 사용 하지 않도록 설정 된 `CMFCColorBar` 하는 동안 개체 [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md) 생성 합니다. `CMFCColorMenuButton` 개체를 동적으로 만듭니다는 `CMFCColorBar` 프레임 워크 호출 후 개체는 `CreatePopupMenu` 메서드.  
  
 색 막대 컨트롤 단추를 클릭할 때 프레임 워크에서는 `ON_COMMAND` 색 막대 컨트롤의 부모에 알리기 위해 매크로입니다. 매크로 명령 ID 매개 변수 (이 예제의 ID_CHAR_COLOR) 1 단계에서 색 막대 컨트롤 단추에 할당 된 값을입니다. 자세한 내용은 참조는 [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton 클래스](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md), 및 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md) 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 다양 한 메서드를 사용 하 여 색 막대를 구성 하는 방법의 `CMFCColorBar` 클래스입니다. 메서드 가로 및 세로 여백 설정, 다른 단추를 사용 하도록 설정, 색 막대 컨트롤 창을 만들 및 현재 선택 된 색을 설정 합니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&1;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&2;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcolorbar.h  
  
##  <a name="adjustlocations"></a>CMFCColorBar::AdjustLocations  
 색 컨트롤의 단추에는 색 막대의 위치를 조정합니다.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 프레임 워크 중 `WM_SIZE` 메시지를 처리 합니다.  
  
##  <a name="allowchangetextlabels"></a>CMFCColorBar::AllowChangeTextLabels  
 색 단추의 텍스트 레이블을 변경할 수 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 항상 반환 `FALSE`, 즉 텍스트 레이블을 수정할 수 없습니다. 수정 하 고 텍스트 레이블을 사용 하려면이 메서드를 재정의 합니다.  
  
##  <a name="allowshowonlist"></a>CMFCColorBar::AllowShowOnList  
 사용자 지정 프로세스 중 색 막대 컨트롤 개체 도구 모음 목록에 표시 될 수 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 항상 반환 `TRUE`, 프레임 워크를 의미 하는 과정에서 사용자 지정 색 막대 컨트롤을 표시할 수 있습니다. 다른 동작을 구현 하려면이 메서드를 재정의 합니다.  
  
##  <a name="calcsize"></a>CMFCColorBar::CalcSize  
 레이아웃 계산 프로세스의 일환으로 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bVertDock`  
 `TRUE`색 막대 컨트롤이 세로로; 도킹 되 지정 하려면 `FALSE` 색 막대 컨트롤이 가로로 도킹 되 지정할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 색 막대 컨트롤의 색 단추는 배열의 크기입니다.  
  
##  <a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar  
 `CMFCColorBar` 개체를 생성합니다.  
  
```  
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    int nRowsDockHorz,  
    int nColDockVert,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCColorButton* pParentBtn);

 
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCRibbonColorButton* pParentRibbonBtn);

 
CMFCColorBar(
    CMFCColorBar& src,  
    UINT uiCommandID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `colors`  
 색 막대 컨트롤에 프레임 워크가 표시 하는 색의 배열입니다.  
  
 [in] `color`  
 처음에 선택한 색입니다.  
  
 [in] `lpszAutoColor`  
 텍스트 레이블을 *자동* (기본값) 색 단추 또는 `NULL`합니다.  
  
 자동 단추에 대 한 표준 레이블은 **자동**합니다.  
  
 [in] `lpszOtherColor`  
 텍스트 레이블을 *다른* 단추를 다른 색 선택 표시, 또는 `NULL`합니다.  
  
 다른 단추에 대 한 표준 레이블은 **다른 색... **.  
  
 [in] `lpszDocColors`  
 문서 색 단추의 텍스트 레이블입니다. 색상표를 문서는 현재 문서에 사용 된 모든 색을 나열 합니다.  
  
 [in] `lstDocColors`  
 현재 문서에 사용 된 색의 목록이 됩니다.  
  
 [in] `nColumns`  
 색의 배열에 있는 열의 수입니다.  
  
 [in] `nRowsDockHorz`  
 가로 방향으로 도킹 한 경우 색 막대에 있는 행의 수입니다.  
  
 [in] `nColDockVert`  
 세로로 도킹 한 경우 색 막대에 있는 열의 수입니다.  
  
 [in] `colorAutomatic`  
 자동 단추를 클릭할 때 프레임 워크 적용 되는 기본 색입니다.  
  
 [in] `nCommandID`  
 색 막대 제어 명령 id입니다.  
  
 [in] `pParentBtn`  
 부모 단추에 대 한 포인터입니다.  
  
 [in] `src`  
 기존 `CMFCColorBar` 새 복사할 개체 `CMFCColorBar` 개체입니다.  
  
 [in] `uiCommandID`  
 명령 ID입니다.  
  
##  <a name="contexttosize"></a>CMFCColorBar::ContextToSize  
 색 막대 컨트롤의 단추에 포함 해야 하며 해당 단추의 위치를 조정 하는 세로 및 가로 여백을 계산 합니다.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `bSquareButtons`|`TRUE`색 막대 컨트롤에 있는 단추의 모양을 사각형; 임을 지정 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.|  
|[in] `bCenterButtons`|`TRUE`색 막대 컨트롤 단추 모양의 콘텐츠; 가운데로 정렬 됨을 지정 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.|  
  
### <a name="remarks"></a>주의  
  
##  <a name="create"></a>CMFCColorBar::Create  
 색 막대 컨트롤 창을 만들고이에 연결 된 `CMFCColorBar` 개체입니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle,  
    UINT nID,  
    CPalette* pPalette=NULL,  
    int nColumns=0,  
    int nRowsDockHorz=0,  
    int nColDockVert=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 부모 창에 대 한 포인터입니다.  
  
 [in] `dwStyle`  
 비트 조합 (OR) [창 스타일](../../mfc/reference/window-styles.md)합니다.  
  
 [in] `nID`  
 명령 ID입니다.  
  
 [in] `pPalette`  
 색의 팔레트에 대 한 포인터입니다. 기본값은 `NULL`입니다.  
  
 [in] `nColumns`  
 색 막대 컨트롤에서 열 수입니다. 기본값은 0입니다.  
  
 [in] `nRowsDockHorz`  
 가로 방향으로 도킹 한 경우 색 막대 컨트롤의 행 수입니다. 기본값은 0입니다.  
  
 [in] `nColDockVert`  
 세로로 도킹 한 경우 색 막대 컨트롤에서 열 수입니다. 기본값은 0입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 생성 하는 `CMFCColorBar` 개체, 클래스 생성자는 다음이 메서드를 호출 합니다. `Create` 메서드는 Windows 컨트롤을 만들고 색 목록을 초기화 합니다.  
  
##  <a name="createcontrol"></a>CMFCColorBar::CreateControl  
 색 막대 컨트롤 창을 만듭니다에 연결 되는 `CMFCColorBar` 개체 지정된 된 색상표를 포함 하도록 컨트롤 창의 크기를 조정 합니다.  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 부모 창에 대 한 포인터입니다. 안 `NULL`합니다.  
  
 [in] `rect`  
 색 막대 컨트롤을 그릴 위치를 지정 하는 경계 사각형.  
  
 [in] `nID`  
 컨트롤 id입니다.  
  
 [in] `nColumns`  
 이상적인 색 막대 컨트롤의 열 수 있습니다. 이 메서드는 지정 된 색상표에 맞게 해당 번호를 수정 합니다. 기본값은-1로,이 매개 변수는 지정 되지 않았음을 나타냅니다.  
  
 [in] `pPalette`  
 색의 팔레트에 대 한 포인터 또는 `NULL`합니다. 이 매개 변수가 `NULL`,이 메서드는 20 색 지정 하는 경우 색 막대 컨트롤의 크기를 계산 합니다. 기본값은 `NULL`입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용 된 `rect`, `nColumns`, 및 `pPalette` 적절 한 수 또는 행과 열 색 막대 컨트롤을 한 다음 호출을 계산 하는 매개 변수는 [CMFCColorBar::Create](#create) 메서드.  
  
##  <a name="createpalette"></a>CMFCColorBar::CreatePalette  
 색의 지정된 된 배열에 색 팔레트를 초기화합니다.  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `arColors`|색의 배열입니다.|  
|[in] `palette`|색의 팔레트입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorBar::EnableAutomaticButton  
 표시 하거나 자동 단추를 숨깁니다.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 텍스트 레이블을 *자동* (기본값) 색 단추 또는 `NULL`합니다.  
  
 자동 단추에 대 한 표준 레이블은 **자동**합니다.  
  
 [in] `colorAutomatic`  
 자동 단추를 클릭할 때 프레임 워크 적용 되는 기본 색입니다.  
  
 [in] `bEnable`  
 `TRUE`자동 단추;를 사용 하도록 설정 하려면 `FALSE` 자동 단추를 사용 하지 않도록 설정 하려면. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 자동 단추의 텍스트 레이블을 삭제 되는 `lpszLabel` 매개 변수는 `NULL` 또는 `bEnable` 매개 변수는 `FALSE`합니다.  
  
##  <a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton  
 사용 하거나 더 많은 색을 선택할 수 있도록 하는 대화 상자를 표시 하지 않도록 설정 합니다.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 텍스트 레이블을 *다른* 단추를 다른 색 선택 표시, 또는 `NULL`합니다.  
  
 이 단추에 대 한 표준 레이블은 **다른 색... **.  
  
 [in] `bAltColorDlg`  
 `TRUE`표시 하는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자입니다. `FALSE` 표준 표시 하려면 [CColorDialog](../../mfc/reference/ccolordialog-class.md) 대화 상자입니다. 기본값은 `TRUE`입니다.  
  
 [in] `bEnable`  
 `TRUE`단추를 사용 하도록 설정 하려면 `FALSE` 단추를 비활성화 하려면. 기본값은 `TRUE`입니다.  
  
##  <a name="getcolor"></a>CMFCColorBar::GetColor  
 현재 선택 된 색을 검색 합니다.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 색입니다.  
  
##  <a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize  
 색 막대 컨트롤의 모눈의 행과 열 개수를 계산 합니다.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `bVertDock`|`TRUE`색 막대를 세로로 도킹 된 컨트롤;에 대 한 계산을 수행 하려면 그렇지 않은 경우 가로로 도킹된 된 컨트롤에 대 한 계산을 수행 합니다.|  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체 `cx` 열과 해당 수를 포함 하는 구성 요소 `cy` 구성 요소에는 행 수가 포함 되어 있습니다.  
  
##  <a name="getcommandid"></a>CMFCColorBar::GetCommandID  
 현재 색 막대 컨트롤의 명령 ID를 검색합니다.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 명령 id입니다.  
  
### <a name="remarks"></a>주의  
 사용자가 새 색을 선택 하면 프레임 워크는 보냅니다 명령 ID는 `WM_COMMAND` 의 부모에 알리기 위해 메시지는 `CMFCColorBar` 개체입니다.  
  
##  <a name="getextraheight"></a>CMFCColorBar::GetExtraHeight  
 현재 색 막대와 같은 기타 사용자 인터페이스 요소를 표시 하는 데 필요한 추가 높이 계산 된 **다른** 단추 또는 문서 색입니다.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `nNumColumns`|색 막대 컨트롤이 포함 되어 있으면 문서 색, 문서 색 눈금에 표시할 열의 수 있습니다. 그렇지 않으면이 값은 사용 되지 않습니다.|  
  
### <a name="return-value"></a>반환 값  
 필요한 계산된 추가 높이입니다.  
  
##  <a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor  
 색을 색 단추에는 포커스가 있는지 나타내는 검색 즉, 단추는 *핫*합니다.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 값입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin  
 클라이언트 영역 경계 왼쪽 또는 오른쪽 색 셀 사이의 공간 가로 여백를 검색 합니다.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>반환 값  
 가로 여백입니다.  
  
##  <a name="getvertmargin"></a>CMFCColorBar::GetVertMargin  
 세로 여백, 위쪽 또는 아래쪽 색 셀과 클라이언트 영역 경계 사이의 공간을 검색 합니다.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>반환 값  
 세로 여백입니다.  
  
##  <a name="initcolors"></a>CMFCColorBar::InitColors  
 지정 된 색상표에서 색 또는 시스템 기본 색상표 색의 배열을 초기화합니다.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pPalette`|색상표 개체에 대 한 포인터 또는 `NULL`합니다. 이 매개 변수가 `NULL`,이 메서드는 운영 체제의 기본 색상표를 사용 합니다.|  
|[in] `arColors`|색의 배열입니다.|  
  
### <a name="return-value"></a>반환 값  
 색 배열에 있는 요소의 수입니다.  
  
##  <a name="istearoff"></a>CMFCColorBar::IsTearOff  
 현재 색 막대 도킹 가능 여부를 나타냅니다.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`현재 색 막대 컨트롤을 도킹 가능한; 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 색 막대 컨트롤 도킹 가능한 경우, 컨트롤 막대를 분리 하 고 다른 위치에 도킹 될 수 있습니다.  
  
##  <a name="onkey"></a>CMFCColorBar::OnKey  
 사용자가 키보드 단추를 누를 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nChar`  
 사용자가 누른 키에 대 한 가상 키 코드입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 지정된 된 키를 처리 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="onsendcommand"></a>CMFCColorBar::OnSendCommand  
 프레임 워크에 닫으려면 팝업 컨트롤 계층에서 호출 됩니다.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pButton`|도구 모음에 있는 컨트롤에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
##  <a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI  
 프레임 워크는 항목 표시 되기 전에 색 막대 컨트롤의 사용자 인터페이스 항목을 사용할지에 의해 호출 됩니다.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTarget`  
 업데이트할 사용자 인터페이스 항목을 포함 하는 창에 대 한 포인터입니다.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`메시지 맵;에 정의 되어 있는 경우 처리기는 사용자 인터페이스 항목을 비활성화 하려면 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 항목으로 사용 하도록 설정 표시할 해야 하는지 여부를 알고 있어야 응용 프로그램의 사용자가 사용자 인터페이스 항목을 클릭할 때 또는 사용 하지 않도록 설정 합니다. 구현 하 여이 정보를 제공 하는 명령 메시지의 대상은 `ON_UPDATE_COMMAND_UI` 명령 처리기입니다. 이 메서드를 사용 하 여 명령을 처리 하는 데 도움이 됩니다. 자세한 내용은 참조 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)합니다.  
  
##  <a name="opencolordialog"></a>CMFCColorBar::OpenColorDialog  
 색 대화 상자를 엽니다.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `colorDefault`  
 색 대화 상자를 열면 기본적으로 선택 된 색입니다.  
  
 [out] `colorRes`  
 사용자가 선택한 색입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`사용자가 선택한 색; 경우 `FALSE` 색 대화 상자에서 취소 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="rebuild"></a>CMFCColorBar::Rebuild  
 색 막대 컨트롤을 완전히 다시 그립니다.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>CMFCColorBar::SelectPalette  
 현재 색 막대 컨트롤의 부모 단추의 팔레트를 지정된 된 장치 컨텍스트에의 논리 색상표를 설정합니다.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pDC`|현재 색 막대 컨트롤의 부모 단추는 장치 컨텍스트에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 현재 색 막대 컨트롤의 부모 단추의 색상표에 따라 대체 팔레트에 대 한 포인터입니다.  
  
##  <a name="setcolor"></a>CMFCColorBar::SetColor  
 현재 선택 된 색을 설정 합니다.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 RGB 색상 값입니다.  
  
##  <a name="setcolorname"></a>CMFCColorBar::SetColorName  
 지정 된 색에 대 한 새 이름을 설정합니다.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 색의 RGB 값입니다.  
  
 [in] `strName`  
 지정 된 색에 대 한 새 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 모든 페이지에서 지정된 된 색의 이름을 변경 `CMFCColorBar` 응용 프로그램의 개체입니다.  
  
##  <a name="setcommandid"></a>CMFCColorBar::SetCommandID  
 색 막대 컨트롤에 대 한 새 명령 ID를 설정합니다.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCommandID`  
 명령 id입니다.  
  
### <a name="remarks"></a>주의  
 색 막대 컨트롤의 명령 ID를 수정 하 고 ID가 변경 하는 컨트롤의 부모 창에 알리기 위해이 메서드를 호출 합니다.  
  
##  <a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors  
 현재 문서에 사용 되는 색 목록을 설정 합니다.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszCaption`  
 색 막대 컨트롤 잠기지 않은 경우 표시 되는 캡션.  
  
 [in] `lstDocColors`  
 현재 문서 색을 대체 하는 색의 목록입니다.  
  
 [in] `bShowWhenDocked`  
 `TRUE`색 막대 컨트롤이 도킹 되 고 때 문서 색을 표시 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 *문서 색* 문서에서 현재 사용 되는 색입니다. 프레임 워크에는 자동으로 문서 색 목록을 유지 관리 하지만 목록을 수정 하려면이 메서드를 사용할 수 있습니다.  
  
##  <a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin  
 클라이언트 영역 경계 왼쪽 또는 오른쪽 색 셀 사이의 공간의 가로 여백을 설정 합니다.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHorzMargin`  
 가로 여백 (픽셀)입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로는 [CMFCColorBar::CMFCColorBar](#cmfccolorbar) 생성자 가로 여백을 설정 하는 4 픽셀입니다.  
  
##  <a name="setproplist"></a>CMFCColorBar::SetPropList  
 설정의 `m_pWndPropList` 속성 표 컨트롤에 지정된 된 포인터에 대 한 데이터 멤버를 보호 합니다.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pWndList`|속성 표 컨트롤 개체에 대 한 포인터입니다.|  
  
##  <a name="setvertmargin"></a>CMFCColorBar::SetVertMargin  
 세로 여백, 위쪽 또는 아래쪽 색 셀과 클라이언트 영역 경계 사이의 공간을 설정 합니다.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nVertMargin`  
 픽셀에서 수직 여백입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로는 [CMFCColorBar::CMFCColorBar](#cmfccolorbar) 4 픽셀 수직 여백을 설정 하는 생성자입니다.  
  
##  <a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString  
 상태 표시줄에서 메시지 줄을 업데이트 하려면 색 막대 컨트롤을 소유 하는 프레임 창을 요청 합니다.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdId`  
 명령 id입니다. (이 매개 변수가 무시 됩니다.)  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 `WM_SETMESSAGESTRING` 색 막대 컨트롤의 소유자에 게는 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

