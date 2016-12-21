---
title: "CMFCColorBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorBar class"
  - "CMFCColorBar::m_bInternal data member"
  - "CMFCColorBar::m_bIsEnabled data member"
  - "CMFCColorBar::m_bIsTearOff data member"
  - "CMFCColorBar::m_BoxSize data member"
  - "CMFCColorBar::m_bShowDocColorsWhenDocked data member"
  - "CMFCColorBar::m_bStdColorDlg data member"
  - "CMFCColorBar::m_ColorAutomatic data member"
  - "CMFCColorBar::m_ColorNames data member"
  - "CMFCColorBar::m_colors data member"
  - "CMFCColorBar::m_ColorSelected data member"
  - "CMFCColorBar::m_lstDocColors data member"
  - "CMFCColorBar::m_nCommandID data member"
  - "CMFCColorBar::m_nHorzMargin data member"
  - "CMFCColorBar::m_nHorzOffset data member"
  - "CMFCColorBar::m_nNumColumns data member"
  - "CMFCColorBar::m_nNumColumnsVert data member"
  - "CMFCColorBar::m_nNumRowsHorz data member"
  - "CMFCColorBar::m_nRowHeight data member"
  - "CMFCColorBar::m_nVertMargin data member"
  - "CMFCColorBar::m_nVertOffset data member"
  - "CMFCColorBar::m_Palette data member"
  - "CMFCColorBar::m_pParentBtn data member"
  - "CMFCColorBar::m_pParentRibbonBtn data member"
  - "CMFCColorBar::m_pWndPropList data member"
  - "CMFCColorBar::m_strAutoColor data member"
  - "CMFCColorBar::m_strDocColors data member"
  - "CMFCColorBar::m_strOtherColor data member"
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorBar` 도킹 컨트롤 막대 색 문서나 응용 프로그램에 선택할 수 있는 클래스를 나타냅니다.  
  
## 구문  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorBar::CMFCColorBar](../Topic/CMFCColorBar::CMFCColorBar.md)|`CMFCColorBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorBar::ContextToSize](../Topic/CMFCColorBar::ContextToSize.md)|색상 막대 컨트롤에 있는 단추를 포함 하는 데 필요한 하 고이 단추 들의 위치를 조정 하는 세로 및 가로 여백을 계산 합니다.|  
|[CMFCColorBar::CreateControl](../Topic/CMFCColorBar::CreateControl.md)|색상 막대 컨트롤 창 작성, 첨부 하는 `CMFCColorBar` 개체와 지정 된 색상표의 색을 포함 하는 컨트롤의 크기를 조정 합니다.|  
|[CMFCColorBar::Create](../Topic/CMFCColorBar::Create.md)|색상 막대 컨트롤 창 만들고 연결 하는 `CMFCColorBar` 개체입니다.|  
|[CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)|표시 하거나 \[자동\] 단추를 숨깁니다.|  
|[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)|사용 하거나 다른 색을 선택할 수 있습니다 대화 상자를 표시 하지 않도록 설정 합니다.|  
|[CMFCColorBar::GetColor](../Topic/CMFCColorBar::GetColor.md)|현재 선택한 색을 검색합니다.|  
|[CMFCColorBar::GetCommandID](../Topic/CMFCColorBar::GetCommandID.md)|현재 색상 막대 컨트롤의 명령 ID를 검색합니다.|  
|[CMFCColorBar::GetHighlightedColor](../Topic/CMFCColorBar::GetHighlightedColor.md)|색 단추에 포커스가 있음을 나타냅니다. 색을 검색 합니다. 즉, 단추는  *핫*.|  
|[CMFCColorBar::GetHorzMargin](../Topic/CMFCColorBar::GetHorzMargin.md)|가로 여백 왼쪽 또는 오른쪽 색 셀 클라이언트 영역 경계 사이의 공간을 검색 합니다.|  
|[CMFCColorBar::GetVertMargin](../Topic/CMFCColorBar::GetVertMargin.md)|세로 여백, 위쪽 또는 아래쪽 색 셀 클라이언트 영역 경계 사이의 공간을 검색 합니다.|  
|[CMFCColorBar::IsTearOff](../Topic/CMFCColorBar::IsTearOff.md)|색 현재 막대 도킹 가능한 지 여부를 나타냅니다.|  
|[CMFCColorBar::SetColor](../Topic/CMFCColorBar::SetColor.md)|현재 선택 된 색을 설정 합니다.|  
|[CMFCColorBar::SetColorName](../Topic/CMFCColorBar::SetColorName.md)|지정 된 색의 새 이름을 설정합니다.|  
|[CMFCColorBar::SetCommandID](../Topic/CMFCColorBar::SetCommandID.md)|색상 막대 컨트롤에 대해 새 명령 ID를 설정합니다.|  
|[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)|현재 문서에서 목록에 사용 되는 색을 설정 합니다.|  
|[CMFCColorBar::SetHorzMargin](../Topic/CMFCColorBar::SetHorzMargin.md)|왼쪽 또는 오른쪽 색 셀 클라이언트 영역 경계 사이의 공간이 가로 여백을 설정 합니다.|  
|[CMFCColorBar::SetVertMargin](../Topic/CMFCColorBar::SetVertMargin.md)|클라이언트 영역 경계 위쪽 또는 아래쪽 색 셀 사이의 공간이 세로 여백을 설정 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorBar::AdjustLocations](../Topic/CMFCColorBar::AdjustLocations.md)|색 단추 색상 막대 컨트롤의 위치를 조정합니다.|  
|[CMFCColorBar::AllowChangeTextLabels](../Topic/CMFCColorBar::AllowChangeTextLabels.md)|텍스트 레이블을 단추 색을 변경할 수 있는지 여부를 나타냅니다.|  
|[CMFCColorBar::AllowShowOnList](../Topic/CMFCColorBar::AllowShowOnList.md)|색상 막대 컨트롤은 도구 모음 목록에서 사용자 지정 과정 중 표시할 수 있는지 나타냅니다.|  
|[CMFCColorBar::CalcSize](../Topic/CMFCColorBar::CalcSize.md)|프레임 워크는 레이아웃 계산 프로세스의 일부로 호출 됩니다.|  
|[CMFCColorBar::CreatePalette](../Topic/CMFCColorBar::CreatePalette.md)|색상표의 색으로 색상이 지정 된 배열 Initalizes.|  
|[CMFCColorBar::GetColorGridSize](../Topic/CMFCColorBar::GetColorGridSize.md)|색상 막대 컨트롤의 모눈의 행 및 열 개수를 계산합니다.|  
|[CMFCColorBar::GetExtraHeight](../Topic/CMFCColorBar::GetExtraHeight.md)|현재 색상 막대 같은 기타 사용자 인터페이스 요소를 표시 하는 데 필요한 추가 높이가 계산의  **기타** 단추 및 문서 색상.|  
|[CMFCColorBar::InitColors](../Topic/CMFCColorBar::InitColors.md)|색상 팔레트를 지정된 하거나 기본 시스템 색상표에서 색상을 배열을 초기화합니다.|  
|[CMFCColorBar::OnKey](../Topic/CMFCColorBar::OnKey.md)|키보드 단추를 누를 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCColorBar::OnSendCommand](../Topic/CMFCColorBar::OnSendCommand.md)|팝업 컨트롤의 계층 구조를 닫으려면 프레임 워크에서 호출 됩니다.|  
|[CMFCColorBar::OnUpdateCmdUI](../Topic/CMFCColorBar::OnUpdateCmdUI.md)|항목에 표시 되기 전에 색상 막대 컨트롤의 사용자 인터페이스 항목을 사용할지 여부는 프레임 워크에서 호출 됩니다.|  
|[CMFCColorBar::OpenColorDialog](../Topic/CMFCColorBar::OpenColorDialog.md)|색 대화 상자를 엽니다.|  
|[CMFCColorBar::Rebuild](../Topic/CMFCColorBar::Rebuild.md)|색상 막대 컨트롤을 완전히 다시 그립니다.|  
|[CMFCColorBar::SelectPalette](../Topic/CMFCColorBar::SelectPalette.md)|지정 된 디바이스 컨텍스트의 논리 색상표 색상표 단추 현재 색상 막대 컨트롤의 부모를 설정합니다.|  
|[CMFCColorBar::SetPropList](../Topic/CMFCColorBar::SetPropList.md)|세트는 `m_pWndPropList` 지정 된 속성 표 컨트롤에 포인터를 데이터 구성원을 보호 합니다.|  
|[CMFCColorBar::ShowCommandMessageString](../Topic/CMFCColorBar::ShowCommandMessageString.md)|색상 막대 컨트롤 업데이트 상태 표시줄의 메시지 줄 수를 소유 하는 프레임 창을 요청 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|`m_bInternal`|마우스 이벤트를 처리 하는지 여부를 결정 하는 부울 필드입니다.  이 필드가 있을 때 마우스 이벤트가 처리 되는 일반적으로 `TRUE` 및 사용자 지정 모드 `FALSE`.|  
|`m_bIsEnabled`|컨트롤의 활성화 여부를 나타내는 부울입니다.|  
|`m_bIsTearOff`|색상 막대 컨트롤 도킹을 지원 하는지 여부를 나타내는 부울입니다.|  
|`m_BoxSize`|A  [CSize](../../atl-mfc-shared/reference/csize-class.md) 색상 막대 눈금에서 셀의 크기를 지정 하는 개체입니다.|  
|`m_bShowDocColorsWhenDocked`|색상 막대를 도킹할 때 문서 색상을 표시할지 여부를 나타내는 부울입니다.  자세한 내용은 [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)를 참조하십시오.|  
|`m_bStdColorDlg`|표준 시스템 색 대화 상자를 표시할지 여부를 나타내는 부울 값 또는  [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자.  자세한 내용은 [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)를 참조하십시오.|  
|`m_ColorAutomatic`|A  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 는 현재 자동 색을 저장 합니다.  자세한 내용은 [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)를 참조하십시오.|  
|`m_ColorNames`|[CMap](../../mfc/reference/cmap-class.md) 집합의 RGB 연결 개체 색 이름을 사용 합니다.|  
|`m_colors`|A  [CArray](../../mfc/reference/carray-class.md) 의  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 색상 막대 컨트롤에 표시 되는 색을 포함 하는 값입니다.|  
|`m_ColorSelected`|A  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값이 색 색상 막대 컨트롤에서 현재 사용자를 선택 합니다.|  
|`m_lstDocColors`|A  [CList](../../mfc/reference/clist-class.md) 의  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 현재 문서에서 사용 되는 색을 포함 하는 값입니다.|  
|`m_nCommandID`|색 단추 명령 ID입니다 부호 없는 정수입니다.|  
|`m_nHorzMargin`|가로 여백 색 색상표가 단추 사이의 정수입니다.|  
|`m_nHorzOffset`|가로 오프셋 색 단추를 나타내는 정수.  이 값은 텍스트 또는 이미지 색상 외에도 단추를 표시 하는 경우 상당한입니다.|  
|`m_nNumColumns`|색상의 색상 막대 컨트롤 표의 열 수를 나타내는 정수.|  
|`m_nNumColumnsVert`|열 세로 격자의 색상 수를 나타내는 정수.|  
|`m_nNumRowsHorz`|열 가로 방향 격자의 색상 수를 나타내는 정수.|  
|`m_nRowHeight`|색 색상표가 단추는 행의 높이 나타내는 정수.|  
|`m_nVertMargin`|세로 여백 색 색상표가 단추 사이의 정수입니다.|  
|`m_nVertOffset`|세로 오프셋 색 단추를 나타내는 정수.  이 값은 텍스트 또는 이미지 색상 외에도 단추를 표시 하는 경우 상당한입니다.|  
|`m_Palette`|A  [CPalette](../../mfc/reference/cpalette-class.md) 색상 막대 컨트롤에 사용 되는 색입니다.|  
|`m_pParentBtn`|에 대 한 포인터는  [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) 현재 단추의 부모 개체입니다.  색 단추 도구 모음 컨트롤 계층 구조에서 속성 표 컨트롤에서 색 이면이 값이 중요 합니다.|  
|`m_pParentRibbonBtn`|에 대 한 포인터는  [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) 리본 메뉴 이며 현재 단추의 부모 단추 개체.  색 단추 도구 모음 컨트롤 계층 구조에서 속성 표 컨트롤에서 색 이면이 값이 중요 합니다.|  
|`m_pWndPropList`|에 대 한 포인터는  [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체입니다.|  
|`m_strAutoColor`|A  [CString](../../atl-mfc-shared/reference/cstringt-class.md) 에 표시 되는 텍스트 즉는  **자동** 단추.  자세한 내용은 [CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)를 참조하십시오.|  
|`m_strDocColors`|A  [CString](../../atl-mfc-shared/reference/cstringt-class.md) 문서 색 단추에 표시 되는 텍스트입니다.  자세한 내용은 [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)를 참조하십시오.|  
|`m_strOtherColor`|A  [CString](../../atl-mfc-shared/reference/cstringt-class.md) 에 표시 되는 텍스트 즉는  *기타* 단추.  자세한 내용은 [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)를 참조하십시오.|  
  
## 설명  
 일반적으로 만들지 하지는 `CMFCColorBar` 직접 개체입니다.  대신에 [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(메뉴 및 도구 모음에 사용\) 또는 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md) 만듭니다는 `CMFCColorBar` 개체.  
  
 `CMFCColorBar` 클래스는 다음과 같은 기능을 제공 합니다.  
  
-   문서 색상 목록이 자동으로 조정합니다.  
  
-   저장 및 문서 상태와 해당 상태를 복원 합니다.  
  
-   "자동" 단추를 관리합니다.  
  
-   사용 하는 [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md) 컨트롤을 사용자 지정 색을 선택 합니다.  
  
-   "분리" 상태 지원 \(사용 하 여 만들어진 경우는 [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md)\).  
  
 통합 하 여 `CMFCColorBar` 응용 프로그램에 기능:  
  
1.  일반 메뉴 단추를 만들고 ID, 예를 들어 ID\_CHAR\_COLOR를 할당 합니다.  
  
2.  프레임 창 클래스를 재정의 하 여 [CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md) 메서드 및 일반 메뉴 바꾸기 단추를 [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) 개체 \(호출 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)\).  
  
3.  모든 스타일을 설정 하 고 사용 하거나 기능을 해제는 `CMFCColorBar` 개체 중 [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) 생성 합니다.  `CMFCColorMenuButton` 개체를 동적으로 생성의 `CMFCColorBar` framework 호출 후에 개체의 `CreatePopupMenu` 메서드.  
  
 색상 막대 컨트롤 단추를 클릭할 때 프레임 워크를 사용 하 여 `ON_COMMAND` 색상 막대 컨트롤의 부모에 게 알리려면 매크로.  매크로에서 명령 ID 매개 변수 색상 막대 컨트롤 단추 \(ID\_CHAR\_COLOR\)이이 예제에서는 1 단계에서 할당 된 값입니다.  For more information, see the [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md), and [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) classes.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하 여 색상 막대를 구성 하는 방법의 `CMFCColorBar` 클래스입니다.  메서드 가로 세로 여백 설정, 다른 단추를 사용, 색상 막대 컨트롤 창의 만들 및 현재 선택한 색상을 설정 합니다.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/CPP/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/CPP/cmfccolorbar-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## 요구 사항  
 **헤더:** afxcolorbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)