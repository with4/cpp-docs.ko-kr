---
title: "CMFCColorButton Class | Microsoft Docs"
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
  - "CMFCColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorButton class"
  - "CMFCColorButton::m_bAltColorDlg data member"
  - "CMFCColorButton::m_bAutoSetFocus data member"
  - "CMFCColorButton::m_Color data member"
  - "CMFCColorButton::m_ColorAutomatic data member"
  - "CMFCColorButton::m_lstDocColors data member"
  - "CMFCColorButton::m_nColumns data member"
  - "CMFCColorButton::m_pPalette data member"
  - "CMFCColorButton::m_pPopup data member"
  - "CMFCColorButton::m_strAutoColorText data member"
  - "CMFCColorButton::m_strDocColorsText data member"
  - "CMFCColorButton::m_strOtherText data member"
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorButton` 및 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md) 클래스는 함께 사용 하는 색상 선택기 컨트롤을 구현 합니다.  
  
## 구문  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorButton::CMFCColorButton](../Topic/CMFCColorButton::CMFCColorButton.md)|새 `CMFCColorButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorButton::EnableAutomaticButton](../Topic/CMFCColorButton::EnableAutomaticButton.md)|수 있으며 일반 색 단추 위에 배치 되는 "자동" 단추를 사용할 수 없습니다.  \(표준 시스템 자동 단추인  **자동**.\)|  
|[CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)|수 있으며 일반 색 단추 아래에 배치 되는 "기타" 단추를 사용할 수 없습니다.  \("기타" 단추는 표시 된 표준 시스템  **다른 색...**.\)|  
|[CMFCColorButton::GetAutomaticColor](../Topic/CMFCColorButton::GetAutomaticColor.md)|현재 자동 색을 검색합니다.|  
|[CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md)|단추의 색을 검색합니다.|  
|[CMFCColorButton::SetColor](../Topic/CMFCColorButton::SetColor.md)|버튼의 색상을 설정합니다.|  
|[CMFCColorButton::SetColorName](../Topic/CMFCColorButton::SetColorName.md)|색 이름으로 설정합니다.|  
|[CMFCColorButton::SetColumnsNumber](../Topic/CMFCColorButton::SetColumnsNumber.md)|색 선택 대화 상자에서 열 개수를 설정합니다.|  
|[CMFCColorButton::SetDocumentColors](../Topic/CMFCColorButton::SetDocumentColors.md)|색 선택 대화 상자에 표시 되는 문서 관련 색 목록을 지정 합니다.|  
|[CMFCColorButton::SetPalette](../Topic/CMFCColorButton::SetPalette.md)|표준 디스플레이 색상 팔레트를 지정합니다.|  
|[CMFCColorButton::SizeToContent](../Topic/CMFCColorButton::SizeToContent.md)|텍스트 및 이미지 크기에 따라 단추 컨트롤의 크기를 변경합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorButton::IsDrawXPTheme](../Topic/CMFCColorButton::IsDrawXPTheme.md)|Windows xp 비주얼 스타일에서 \[현재 색상\] 단추를 표시할지 여부를 나타냅니다.|  
|[CMFCColorButton::OnDraw](../Topic/CMFCColorButton::OnDraw.md)|단추의 이미지를 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::OnDrawBorder](../Topic/CMFCColorButton::OnDrawBorder.md)|단추의 테두리를 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::OnDrawFocusRect](../Topic/CMFCColorButton::OnDrawFocusRect.md)|단추에 포커스가 있는 경우 포커스 사각형을 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)|색 선택 대화 상자가 표시 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCColorButton::RebuildPalette](../Topic/CMFCColorButton::RebuildPalette.md)|초기화는 `m_pPalette` 데이터 멤버를 지정 된 팔레트 또는 기본 시스템 색상표를 보호 합니다.|  
|[CMFCColorButton::UpdateColor](../Topic/CMFCColorButton::UpdateColor.md)|사용자 색 색상표에서 색 선택 대화 상자를 선택 하면 프레임 워크에서 호출 됩니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|`m_bAltColorDlg`|부울 값입니다.  경우 `TRUE`, 프레임 워크를 표시는  [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 색 대화 상자는 경우는  *다른* 단추를 클릭 하거나 `FALSE`, 시스템 색 대화 상자.  기본값은 `TRUE`입니다.  자세한 내용은 [CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)를 참조하십시오.|  
|`m_bAutoSetFocus`|부울 값입니다.  경우 `TRUE`, 메뉴가 표시 될 때 또는 경우 포커스 \[색상\] 메뉴에서 프레임 워크를 설정 `FALSE`, 포커스가 변경 되지 않습니다.  기본값은 `TRUE`입니다.|  
|[CMFCColorButton::m\_bEnabledInCustomizeMode](../Topic/CMFCColorButton::m_bEnabledInCustomizeMode.md)|사용자 지정 모드 색 단추를 사용할 수 있는지 여부를 나타냅니다.|  
|`m_Color`|A  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  현재 선택한 색을 포함합니다.|  
|`m_ColorAutomatic`|A  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  현재 선택한 기본 색상을 포함 합니다.|  
|`m_Colors`|A  [CArray](../../mfc/reference/carray-class.md) 의  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  현재 사용할 수 있는 색을 있습니다.|  
|`m_lstDocColors`|A  [CList](../../mfc/reference/clist-class.md) 의  [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  현재 문서의 색을 있습니다.|  
|`m_nColumns`|정수입니다.  눈금의 색상 색상 선택 메뉴에 표시할 열 수를 포함 합니다.|  
|`m_pPalette`|에 대 한 포인터는  [CPalette](../../mfc/reference/cpalette-class.md).  현재 색상 선택 메뉴에서 사용할 수 있는 색을 있습니다.|  
|`m_pPopup`|에 대 한 포인터는 [CMFCColorPopupMenu Class](../../mfc/reference/cmfccolorpopupmenu-class.md) 개체입니다.  색 단추를 클릭 하면 나타나는 색상 선택 메뉴입니다.|  
|`m_strAutoColorText`|문자열  색상 선택 메뉴에서 "자동" 단추 레이블.|  
|`m_strDocColorsText`|문자열  문서 색상 표시, 색상 선택 메뉴에서 단추 레이블.|  
|`m_strOtherText`|문자열  색상 선택 메뉴의 "기타" 단추 레이블.|  
  
## 설명  
 기본적으로 `CMFCColorButton` 클래스는 색 선택 대화 상자를 엽니다 누름식 버튼으로 동작 합니다.  색 선택 대화 상자는 소형 컬러 단추 및 사용자 지정 색상을 표시 하는 "기타" 단추 배열을 포함 합니다.  \("기타" 단추는 표시 된 표준 시스템  **다른 색...**.\) 새로운 색을 선택할 때의 `CMFCColorButton` 개체 변경 내용을 반영 하 고 선택한 색을 표시 합니다.  
  
 색 단추 컨트롤 또는 코드에서 직접 사용 하 여 만들는  **클래스 마법사** 도구 및 대화 상자 템플릿에.  색 단추 컨트롤을 직접 만드는 경우 추가 `CMFCColorButton` 변수를 응용 프로그램 및 다음 생성자를 호출 하 고 `Create` 메서드를의 `CMFCColorButton` 개체.  사용 하는 경우는  **클래스 마법사**, 추가 `CButton` 변수를 응용 프로그램을 다음에서 변수의 형식을 변경 하 고 `CButton` 에 `CMFCColorButton`.  
  
 색 선택 대화 상자 \([CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)\)에 표시 되는 [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) 메서드는 프레임 워크에서 호출 되는 `OnLButtonDown` 이벤트 처리기.  [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) 메서드를 재정의 사용자 지정 색 선택 옵션을 지원 합니다.  
  
 `CMFCColorButton` 개체에 게 알립니다 전송 하 여 색을 변경 하 고 부모는 `WM_COMMAND | BN_CLICKED` 알림.  부모를 사용 하는 [CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md) 메서드는 현재 색을 검색 합니다.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하 여 색 단추를 구성 하는 방법의 `CMFCColorButton` 클래스입니다.  색 색 단추 및 해당 열 개수를 설정 방법과 자동 및 다른 단추를 사용 합니다.  이 이때의 일부인의  [상태 표시줄 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_2.cpp)]  
  
## 요구 사항  
 **헤더:** afxcolorbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)