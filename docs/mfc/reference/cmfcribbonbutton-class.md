---
title: "CMFCRibbonButton Class | Microsoft Docs"
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
  - "CMFCRibbonButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonButton class"
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonButton` 클래스는 패널, 빠른 실행 도구 모음 및 팝업 메뉴와 같은 리본 막대 요소에 배치할 수 있는 단추를 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonButton::CMFCRibbonButton](../Topic/CMFCRibbonButton::CMFCRibbonButton.md)|리본 단추 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonButton::AddSubItem](../Topic/CMFCRibbonButton::AddSubItem.md)|단추와 연결되는 메뉴 항목을 팝업 메뉴에 추가합니다.|  
|[CMFCRibbonButton::CanBeStretched](../Topic/CMFCRibbonButton::CanBeStretched.md)|\([CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::CleanUpSizes](../Topic/CMFCRibbonButton::CleanUpSizes.md)|\([CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::ClosePopupMenu](../Topic/CMFCRibbonButton::ClosePopupMenu.md)|\([CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::DrawBottomText](../Topic/CMFCRibbonButton::DrawBottomText.md)||  
|[CMFCRibbonButton::DrawImage](../Topic/CMFCRibbonButton::DrawImage.md)|\([CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::DrawRibbonText](../Topic/CMFCRibbonButton::DrawRibbonText.md)||  
|[CMFCRibbonButton::FindSubItemIndexByID](../Topic/CMFCRibbonButton::FindSubItemIndexByID.md)|지정된 명령 ID와 연결된 팝업 메뉴 항목의 인덱스를 반환합니다.|  
|[CMFCRibbonButton::GetCommandRect](../Topic/CMFCRibbonButton::GetCommandRect.md)||  
|[CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md)|리본 요소의 압축 크기를 반환합니다.  \([CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::GetIcon](../Topic/CMFCRibbonButton::GetIcon.md)||  
|[CMFCRibbonButton::GetImageIndex](../Topic/CMFCRibbonButton::GetImageIndex.md)|단추와 연결된 이미지의 인덱스를 반환합니다.|  
|[CMFCRibbonButton::GetImageSize](../Topic/CMFCRibbonButton::GetImageSize.md)|리본 요소의 이미지 크기를 반환합니다.  \([CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::GetIntermediateSize](../Topic/CMFCRibbonButton::GetIntermediateSize.md)|중간 상태인 리본 요소의 크기를 반환합니다.  \([CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::GetMenu](../Topic/CMFCRibbonButton::GetMenu.md)|리본 단추에 할당된 Windows 메뉴에 대한 핸들을 반환합니다.|  
|[CMFCRibbonButton::GetMenuRect](../Topic/CMFCRibbonButton::GetMenuRect.md)||  
|[CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md)|리본 요소의 보통 크기를 반환합니다.  \([CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::GetSubItems](../Topic/CMFCRibbonButton::GetSubItems.md)||  
|[CMFCRibbonButton::GetTextRowHeight](../Topic/CMFCRibbonButton::GetTextRowHeight.md)||  
|[CMFCRibbonButton::GetToolTipText](../Topic/CMFCRibbonButton::GetToolTipText.md)|리본 요소의 도구 설명 텍스트를 반환합니다.  \([CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::HasCompactMode](../Topic/CMFCRibbonButton::HasCompactMode.md)|리본 요소에 압축 모드가 있는지 여부를 지정합니다.  \([CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::HasIntermediateMode](../Topic/CMFCRibbonButton::HasIntermediateMode.md)|리본 요소에 중간 모드가 있는지 여부를 지정합니다.  \([CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::HasLargeMode](../Topic/CMFCRibbonButton::HasLargeMode.md)|리본 요소에 큰 모드가 있는지 여부를 결정합니다.  \([CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::HasMenu](../Topic/CMFCRibbonButton::HasMenu.md)|\([CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](../Topic/CMFCRibbonButton::IsAlwaysDrawBorder.md)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](../Topic/CMFCRibbonButton::IsAlwaysLargeImage.md)|\([CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::IsApplicationButton](../Topic/CMFCRibbonButton::IsApplicationButton.md)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](../Topic/CMFCRibbonButton::IsCommandAreaHighlighted.md)||  
|[CMFCRibbonButton::IsDefaultCommand](../Topic/CMFCRibbonButton::IsDefaultCommand.md)|리본 단추에 대한 기본 명령을 사용하도록 설정했는지 여부를 확인합니다.|  
|[CMFCRibbonButton::IsDefaultPanelButton](../Topic/CMFCRibbonButton::IsDefaultPanelButton.md)||  
|[CMFCRibbonButton::IsDrawTooltipImage](../Topic/CMFCRibbonButton::IsDrawTooltipImage.md)||  
|[CMFCRibbonButton::IsLargeImage](../Topic/CMFCRibbonButton::IsLargeImage.md)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](../Topic/CMFCRibbonButton::IsMenuAreaHighlighted.md)||  
|[CMFCRibbonButton::IsMenuOnBottom](../Topic/CMFCRibbonButton::IsMenuOnBottom.md)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](../Topic/CMFCRibbonButton::IsPopupDefaultMenuLook.md)||  
|[CMFCRibbonButton::IsRightAlignMenu](../Topic/CMFCRibbonButton::IsRightAlignMenu.md)|메뉴가 오른쪽 맞춤인지 여부를 확인합니다.|  
|[CMFCRibbonButton::IsSingleLineText](../Topic/CMFCRibbonButton::IsSingleLineText.md)||  
|[CMFCRibbonButton::OnCalcTextSize](../Topic/CMFCRibbonButton::OnCalcTextSize.md)|\([CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::OnDrawBorder](../Topic/CMFCRibbonButton::OnDrawBorder.md)||  
|[CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다.  \([CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::OnFillBackground](../Topic/CMFCRibbonButton::OnFillBackground.md)||  
|[CMFCRibbonButton::RemoveAllSubItems](../Topic/CMFCRibbonButton::RemoveAllSubItems.md)|팝업 메뉴에서 모든 메뉴 항목을 제거합니다.|  
|[CMFCRibbonButton::RemoveSubItem](../Topic/CMFCRibbonButton::RemoveSubItem.md)|팝업 메뉴에서 메뉴 항목을 제거합니다.|  
|[CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md)|\([CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::SetAlwaysLargeImage](../Topic/CMFCRibbonButton::SetAlwaysLargeImage.md)|사용자가 단추를 축소하면 단추가 큰 이미지나 작은 이미지 중 어느 것을 표시하는지를 지정합니다.|  
|[CMFCRibbonButton::SetDefaultCommand](../Topic/CMFCRibbonButton::SetDefaultCommand.md)|리본 단추에 대한 기본 명령을 사용하도록 설정합니다.|  
|[CMFCRibbonButton::SetDescription](../Topic/CMFCRibbonButton::SetDescription.md)|리본 요소에 대한 설명을 설정합니다.  \([CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md)을 재정의합니다.\)|  
|[CMFCRibbonButton::SetImageIndex](../Topic/CMFCRibbonButton::SetImageIndex.md)|단추 이미지에 인덱스를 할당합니다.|  
|[CMFCRibbonButton::SetMenu](../Topic/CMFCRibbonButton::SetMenu.md)|리본 단추에 팝업 메뉴를 할당합니다.|  
|[CMFCRibbonButton::SetParentCategory](../Topic/CMFCRibbonButton::SetParentCategory.md)|\([CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md)를 재정의합니다.\)|  
|[CMFCRibbonButton::SetRightAlignMenu](../Topic/CMFCRibbonButton::SetRightAlignMenu.md)|팝업 메뉴를 단추 오른쪽에 맞춥니다.|  
|[CMFCRibbonButton::SetText](../Topic/CMFCRibbonButton::SetText.md)|리본 요소의 텍스트를 설정합니다.  \([CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md)를 재정의합니다.\)|  
  
### 보호된 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonButton::OnClick](../Topic/CMFCRibbonButton::OnClick.md)|사용자가 단추를 클릭하면 프레임워크에서 호출됩니다.|  
  
## 예제  
 다음 예제에서는 `CMFCRibbonButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다.  예제에서는     `CMFCRibbonButton` 클래스의 개체를 생성하고, 리본 단추에 팝업 메뉴를 할당하고, 단추 설명을 설정하고, 팝업 메뉴에서 메뉴 항목을 제거하고, 팝업 메뉴를 단추 가장자리로 오른쪽 맞춤하는 방법을 설명합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#7](../../mfc/reference/codesnippet/CPP/cmfcribbonbutton-class_1.cpp)]  
  
## 설명  
 응용 프로그램에서 리본 단추를 사용하려면 단추 개체를 생성하여 적절한 리본 메뉴 [패널](../../mfc/reference/cmfcribbonpanel-class.md)에 추가합니다.  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (  
    _T("Clipboard"),                       // Panel name  
    m_PanelIcons.ExtractIcon (0));  // Panel icon  
// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton =   
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);  
// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);  
// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));  
```  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)